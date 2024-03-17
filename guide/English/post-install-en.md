<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">

# Running Windows on the Xiaomi Mi 9

## Optional post-install stuff

### List of supported apps/games
> This is by no means a comprehensive list, it simply lists apps/games that have been tested by the community
[The link can be found here](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

### Disabling USB host mode
> [!Important]
> If you are using a powered USB hub you should disable USB host mode, or your phone may receive permanent damage

To disable USB host mode, boot into Windows on your Mi 9, then download and execute [restore_default_usb.reg](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/blob/main/guide/tools/restore_default_usb.reg). Then reboot.

To re-enable USB host mode, do the same but with [force_usb_host.reg](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/blob/main/guide/tools/force_usb_host.reg).

## Finished!



### Hiding the D: drive (modem partition)
> [!NOTE]
> This is recommended because this drive should not be modified, while some applications may try to write to it

- Open a command prompt and run ```diskpart```
- Then run ```list volume``` to see all available volumes
- Select the disk that has letter D with ```select volume $```, replacing "$" with the volume number
- Remove the letter with ```remove letter d```
- Now exit diskpart with ```exit```

## Finished!
