<img align="right" src="https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/blob/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">


# Запуск Windows 11 на Xiaomi Mi 9

## Установка 

## Установка Windows

### Необходимое
- [ARM-образ Windows](https://uupdump.net/)
- [UEFI](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/releases/download/1.1/samsung.img)
- [Драйвера](https://github.com/woacepheus/XiaoMi9-Drivers)
- Root-права (для бекапа boot.img) или рекавери

### Сделайте бекап boot.img

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

### Сохраните бекап на компьютер

```cmd
adb pull /tmp/boot.img
```

### Запустите UEFI для начала установки Windows

```cmd
fastboot boot <uefi.img>
```

#### Перейдите в mass storage mode
1. Прошейте и запустите UEFI
2. Выберите пункт
   `Enter Simple init`
3. Выберите Mass storage
   
### Дайте букву диску
  

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



### Установка
> Замените `<path/to/install.wim>` на свой путь до install.wim,

> `install.wim` находится в ISO, в папке sources.
> Вы можете достать install.wim монтируя ISO на своем компьюетере

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

### Установка драйверов

> Драйвера нужно скачать [тут](https://github.com/woacepheus/XiaoMi9-Drivers)

> Когда появится надпись "Enter Drive letter..." напишите X:

```cmd
 Откройте папку с драйверами и запустите файл OfflineUpdater.cmd
```

### Создание загрузчика для этого EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```



### Загрузитесь назад в Android
> Прошейте boot.img, который вы забекапили в начале

```cmd
fastboot flash boot boot.img
```
## Готово!

### [Последний шаг: двойная загрузка](dualboot-ru.md)
