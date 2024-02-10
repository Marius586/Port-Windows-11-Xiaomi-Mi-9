<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">

# Running Windows on the Xiaomi Mi 9

## Optional post-install stuff

### Disabling USB host mode

### Hiding the D: drive (modem partition)
> [!NOTE]
> This is recommended because this drive should not be modified, while some applications may try to write to it

- Open a command prompt and run ```diskpart```
- Then run ```list volume``` to see all available volumes
- Select the disk that has letter D with ```select volume $```, replacing "$" with the volume number
- Remove the letter with ```remove letter d```
- Now exit diskpart with ```exit```

## Finished!
