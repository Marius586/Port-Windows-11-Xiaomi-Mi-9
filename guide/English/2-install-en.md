<img align="right" src="https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/blob/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">


# Running Windows on the Xiaomi Mi 9

## Installation

## Installing Windows

### Prerequisites
- [Windows on ARM image](https://uupdump.net/)
- [UEFI image](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/releases/download/1.1/samsung.img)
- [Drivers](https://github.com/woacepheus/XiaoMi9-Drivers)
- Root (for backup boot image) or Recovery

### Make a backup of your existing boot image

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

### Pull backup to computer

```cmd
adb pull /tmp/boot.img
```

### Boot UEFI to start installing Windows

```cmd
fastboot boot <uefi.img>
```

#### Enter to mass storage mode
1. Flash and boot UEFI
2. Select
   `Enter Simple init`
3. Select Mass storage
   
### Assign letters to disks
  

#### Start the Windows disk manager

> Once the Xiaomi Mi 9 is detected as a disk

```cmd
diskpart
```


#### Assign `X` to Windows volume

#### Select the Windows volume of the phone
> Use `list volume` to find it, it's the one named "WINCEPHEUS"

```diskpart
select volume <number>
```

#### Assign the letter X
```diskpart
assign letter=x
```

### Assign `Y` to ESP volume

#### Select the esp volume of the phone
> Use `list volume` to find it, it's the one named "ESPCEPHEUS"

```diskpart
select volume <number>
```

#### Assign the letter Y

```diskpart
assign letter=y
```

#### Exit diskpart
```diskpart
exit
```



### Install

> Replace `<path/to/install.wim>` with the actual install.wim path,

> `install.wim` is located in sources folder inside your ISO
> You can get it either by mounting or extracting it

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

### Install Drivers

> You can download Drivers [here](https://github.com/woacepheus/XiaoMi9-Drivers)

> When it ask you "Enter Drive letter..." type X:

```cmd
 Open folder with Drivers and run OfflineUpdater.cmd
```

### Create Windows bootloader files for the EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```



### Boot back into Android
> Use your backup boot image and flash from fastboot

```cmd
fastboot flash boot boot.img
```
### Remove phantom drive letters (if they are not removed automatically)
> Run theese commands as admin to remove letter
```cmd
mountvol x: /d
mountvol y: /d
```
## Finished!

### [Last step: Setup Dualboot](dualboot-en.md)
