<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">

# Запуск Windows 11 на Xiaomi Mi 9

## Установка 

## Установка Windows

### Необходимое
- [ARM-образ Windows](https://worproject.com/esd)
- [UEFI](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/releases/download/1.2/MuCepheusDisableSecureBoot.img)
- [Драйвера](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/releases/download/Drivers/cepheus-drivers.zip)
- [Модифицированное тврп](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/releases/download/1.4/recovery-cepheus.img) (Должно быть уже установленно)



### Перезагрузитесь в модифицированное рекавери

```cmd
fastboot flash recovery путь\к\recovery-cepheus.img reboot recovery
```

#### Выполните скрипт msc

```cmd
adb shell msc
```

### Дайте букву дискам
  

#### Запустите diskpart

> Как только ваш смартфон определится как диск

```cmd
diskpart
```


#### Дайте букву `X` разделу для Windows

#### Выберите раздел для Windows
> Используйте `list volume` чтобы найти его, это будет "WINCEPHEUS"

```diskpart
select volume <number>
```

#### Выделение буквы X
```diskpart
assign letter x
```

### Дайте букву `Y` разделу ESP

#### Выберите ESP раздел
> Используйте `list volume` чтобы найти его, это будет "ESPCEPHEUS"

```diskpart
select volume <number>
```

#### Выделение буквы Y

```diskpart
assign letter y
```

#### Выйдите с  diskpart
```diskpart
exit
```



### Установка Windows 
> Замените `<path/to/install.esd>` на свой путь до install.esd

> Если вы используйте ISO файл, то файл образа находится в ISO. Монтируйте ISO через Windows Explorer, а затем скопируйте путь к нему

> Замените `index:6` на `index:1` если ваш образ не из ссылки которая предоставленна в инструкции

```cmd
dism /apply-image /ImageFile:path\to\install.esd /index:6 /ApplyDir:X:\
```

### Установка драйверов
> Распакуйте драйвера из архива и откройте 'OfflineUpdater.cmd' файл. Впишите букву диска WINCEPHEUS (Должно быть X) и нажмите enter.

### Создание загрузчика для этого EFI
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

### Removing disk letters
> Use diskpart to remove the letters from WINCEPHEUS and ESPCEPHEUS, if they still have letters attached to them

> Use `list volume` to find ESPCEPHEUS, select it with `select volume <number>`, then remove letter Y with `remove letter y`

> Do the same for WINCEPHEUS if it still has a letter attached

## Резерное копирование загрузочных образов

##### Перезагрузитесь в ваше recovery
> Чтобы убрать msc скрипт
- Перезагрузитесь в рекавери через модифицированное рекавери, или запустите
```cmd
adb reboot recovery
```

### Сделайте резерную копию вашего boot из Android
> Используйте функцию резерной копии из TWRP чтобы сделать резерную копию. Назовите эту копию "Android".

### Установите UEFI на свой телефон
> Перетащите MuCepheusSecureBoot.img во внутреннюю память телефона.

### Прошейте UEFI
> Используйте функцию установки из TWRP, чтобы записать образ UEFI в загрузочный раздел. Выберите «Установить IMG», затем найдите образ.ю

### Сделайте резерную копию вашего boot из Windows
> Используйте функцию резерной копии из TWRP чтобы сделать резерную копию. Назовите эту копию "Windows".

### Загрузитесь в Windows
> После того как вы прошили UEFI образ, перезагрузите телефон.

### Уберите фантомные буквы дисков (если они не убрались автоматический)
```cmd
mountvol x: /d
mountvol y: /d
```

## Готово

### [Последний шаг: двойная загрузка](dualboot-ru.md)
