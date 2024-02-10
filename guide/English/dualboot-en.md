<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">

# Running Windows on the Xiaomi Mi 9

## Dualbooting Android and Windows seamlessly
> [!IMPORTANT]
> You have to be rooted to use this guide.

### Prerequisites
- [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)
- [UEFI](https://github.com/qaz6750/XiaoMi9-Drivers/releases)
- [Windows on Android Helper APK (test version)](https://t.me/WinOnMi9/328)
- [StA Installer](https://github.com/woa-vayu/Port-Windows-11-POCO-X3-Pro/releases/dualboot)

#### Application Setup
> [!NOTE]
>
> In order to mount Windows while you're booted in Android, you need to "shut down" Windows properly. To do this, restart Windows and then boot into TWRP as the screen fades to black. From here you can switch back to Android using the backup you made earlier.

- Download the StA Installer and the WOA Helper APK, then install the APK.
- Grant the app root access and any permissions it requests.
- Copy the UEFI image to the UEFI folder in your internal storage. Create this folder if it does not yet exist.
- Press the "BACKUP ANDROID BOOT" button, select "Backup to Android" and then dismiss the pop-up.
- Do the same, but select "Backup to Windows"
- Use the "Mount Windows" button to mount Windows to the Windows folder in your internal storage.
- Copy the StA Installer.exe to the root of this Windows folder.
- Press "Quickboot to Windows"
- After Windows boots, run the StA installer in the C:\ directory
> You may need to disable any antivirus software present, if the installer does not work

#### Booting to Android
  - Run the new shortcut on your desktop as **ADMINISTRATOR**

#### Booting to Windows
- Press the "Quickboot to Windows" button in the app, or use the toggle in your quick settings panel.

> If quickboot does not work, you may have shut down Windows incorrectly. If this happens, use the "Flash UEFI" button and manually reboot your phone.
  
## Finished!
