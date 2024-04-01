<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">

# Running Windows on the Xiaomi Mi 9

### Partitioning your device

### Prerequisites
- A brain (very important)

- [Modded TWRP](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/releases/download/1.4/recovery-cepheus.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Notes:
> [!Warning]
> All your data will be erased! Backup now if needed.
> 
> These commands have been tested.
> 
> Do not run the same command twice unless specified.
> 
> DO NOT REBOOT YOUR PHONE! If you think you made a mistake, ask for help in the Telegram group.
>
> Do not run all commands at once, execute them in order!
>
> SCRIPTS ONLY WORK ON THE 64GB AND 128GB VERSION


#### Flash and boot into the modded recovery
```cmd
fastboot flash path\to\recovery-cepheus.img reboot recovery
```
##### Run the partitioning script
> If it asks you to run it once again, do so
>
> This is **optional** but you can **set custom sizes using this script**

> To set custom sizes do ```adb shell partition [TARGET WINDOWS SIZE IN GB]```

> Make sure you do not add GB at the end, just the number

> DO NOT TRY ON 12/256 MODEL AKA MI 9 EXPLORER EDITION

```cmd
adb shell partition
```

#### Check if Android still starts
Just restart the phone, and see if Android still works. If it does not boot, reboot to the modded recovery, format all data and then reboot again.


### [Next step: Installing Windows](/guide/English/2-install-en.md)




















