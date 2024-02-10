<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">

# Running Windows on the Xiaomi Mi 9

## Reinstallation

### Reinstalling Windows if something goes wrong

- If you don't like your windows version or you've bricked your windows install, or anything else, you would probably just reinstall Windows. Thankfully this process is very easy.

- If you haven't restored your partition table, you can use this guide with your existing partitions.

### Prerequisites

- Existing Windows and boot partitions (*If not met, [go back and just pretend this guide never existed](/guide/English/1-partition-en.md)*)

- [Recovery Image](../../../../releases/tag/1.1)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Boot recovery to format the Windows and boot partitions

```cmd
fastboot boot <recovery.img>
```
### Format the partitions

```cmd
adb shell format
```




### Install

- Continue the guide from [here](/guide/English/2-install-en.md#install)
