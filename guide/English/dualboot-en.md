<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">

# Running Windows on the Xiaomi Mi 9

## Dualbooting Android and Windows seamlessly
> [!IMPORTANT]
> You have to be rooted to use this guide.

### Prerequisites
- [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)
- [UEFI](https://github.com/qaz6750/XiaoMi9-Drivers/releases)
- [WOA Helper app)](https://t.me/WinOnMi9/328)
- [StA Installer](https://github.com/woa-vayu/Port-Windows-11-POCO-X3-Pro/releases/dualboot)

## Set up dualboot app

### Setup - Android
> [!NOTE]
> If you are unable to move files to the Windows folder, it means you shut down Windows instead of restarting it. To fix this issue, boot back to Windows and use restart, then as it restarts boot to TWRP and use your `Windows` boot backup to return to Android.

- Download and install the [WOA Helper app](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/woahelper.apk), then open it and grant it root access.
- Download the [UEFI image](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/uefi.img) and place it inside the folder named `UEFI` in your internal storage, if this folder does not exist, create it.
- Return to the WOA Helper app and press the `Back up Android boot` button. Select both the `Windows` and `Android` options.
- Press the `Mount Windows` button, then download and move [StA_Installer_cepheus.exe](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/dualboot/StA_Installer_nabu.exe) to the newly created `Windows` folder in your internal storage.
- Return to the WOA Helper app and press `Quickboot to Windows`.

### Setup - Windows
- Navigate to `C:\StA_Installer_cepheus.exe` and run it. If it doesn't work, make sure that any antivirus software is off, as it will probably not let the app run.

##### Booting to Android
  - Run the new shortcut on your desktop (you can also pin it to your start menu / taskbar for ease of access)

##### Booting to Windows
  - Press `Quickboot to Windows` inside the app, or use the newly created toggle in your quick settings panel
  
## Finished!
