<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">

# Запуск Windows 11 на Xiaomi Mi 9

## Установка 

## Установка Windows

### Необходимое
- [ARM-образ Windows](https://uupdump.net/)
- [UEFI](https://github.com/qaz6750/XiaoMi9-Drivers/releases/)
- [Драйвера](https://github.com/woacepheus/XiaoMi9-Drivers)
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
assign letter=x
```

### Дайте букву `Y` разделу ESP

#### Выберите ESP раздел
> Используйте `list volume` чтобы найти его, это будет "ESPCEPHEUS"

```diskpart
select volume <number>
```

#### Выделение буквы Y

```diskpart
assign letter=y
```

#### Выйдите с  diskpart
```diskpart
exit
```



### Установка Windows 
> Замените `<path/to/install.wim>` на свой путь до install.wim,

> `install.wim` находится в ISO, в папке sources.
> Вы можете достать install.wim монтируя ISO на своем компьюетере

> Замените `index:6` на `index:1` если ваш образ не из ссылки которая предоставленна в инструкции
s
```cmd
dism /apply-image /ImageFile:path\to\install.esd /index:6 /ApplyDir:X:\
```

### Создание загрузчика для этого EFI
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

### Установка драйверов
> Распакуйте драйвера из архива и откройте 'OfflineUpdater.cmd' файл. Впишите букву диска WINCEPHEUS (Должно быть X) и нажмите enter. 

## Резерное копирование загрузочных образов
> Сделайте это после завершения установки драйверов.

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
