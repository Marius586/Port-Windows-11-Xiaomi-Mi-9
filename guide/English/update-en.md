<img align="right" src="https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/blob/main/cepheus.png" width="425">


# Running Windows on the Xiaomi Mi 9

## Updating Drivers

### Prerequisites


- [Windows on ARM image](https://uupdump.net/)
- [UEFI image](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/releases/download/1.1/samsung.img)
- [Drivers](https://github.com/woacepheus/XiaoMi9-Drivers)

#### Start recovery through the PC with the command

```cmd
fastboot boot <recovery.img>
```


#### Enter to mass storage mode
1. Flash and boot UEFI
2. Select
   `Enter Simple init`
3. Select Mass storage

### Assign letters to disks

#### Start the Windows disk manager

> Once the Mi 9 is detected as a disk

```cmd
diskpart
```


### Assign `X` to Windows volume

#### Select the Windows volume of the phone
> Use `list volume` to find it, it's the one named "WINCEPHEUS"

```diskpart
select volume <number>
```

#### Assign the letter X
```diskpart
assign letter=x
```

#### Exit diskpart
```diskpart
exit
```


### Install Drivers

> You can download Drivers [here](https://github.com/woacepheus/XiaoMi9-Drivers)

```cmd
 DriverUpdater.exe -d "<path to extracted drivers>\definitions\Desktop\ARM64\Internal\cepheus.txt" -r "<path to extracted drivers>" -p <The window drive letter of your phone>:\
```


### Boot with Windows bootable UEFI image

```
fastboot flash boot <uefi.img>
```

## Finished!
