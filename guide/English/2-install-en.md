<img align="right" src="https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/blob/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">


# Running Windows on the Xiaomi Mi 9

## Installation

## Installing Windows

### Prerequisites
- [Windows on ARM image](https://uupdump.net/)
- [UEFI image](https://github.com/qaz6750/XiaoMi9-Drivers/releases)
- [Drivers](https://github.com/woacepheus/XiaoMi9-Drivers)
- Root (for backup boot image) or Recovery

### Boot recovery back to start installing Windows
```cmd
fastboot boot <recovery.img>
```
#### Execute the msc script
> If it asks you to run it once again, do so
```cmd
adb shell msc
```
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

### Create Windows bootloader files for the EFI

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

### Install Drivers

> You can download Drivers [here](https://github.com/woacepheus/XiaoMi9-Drivers)

> When you downloaded drivers, go to the tools folder

```cmd
 DriverUpdater.exe -d "<path to extracted drivers>\definitions\Desktop\ARM64\Internal\cepheus.txt" -r "<path to extracted drivers>" -p <The window drive letter of your phone>:\
```
> Enable test mode
```
cd <ESP partition>:\EFI\Microsoft\Boot
bcdedit /store BCD /set "{default}" testsigning on
bcdedit /store BCD /set "{default}" nointegritychecks on
bcdedit /store BCD /set "{default}" recoveryenabled no
```


### Boot back into Android
> Use your backup boot image and flash from fastboot

```cmd
fastboot flash boot boot.img
```

### Make a backup of your existing boot image

```cmd
adb shell "dd if=/dev/block/by-name/boot of=/tmp/boot.img"
```

### Pull backup to computer

```cmd
adb pull /tmp/boot.img
```

### Remove phantom drive letters (if they are not removed automatically)
> Run theese commands as admin to remove letter
```cmd
mountvol x: /d
mountvol y: /d
```
## Finished!

### [Last step: Setup Dualboot](dualboot-en.md)
