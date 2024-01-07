<img align="right" src="https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/blob/main/cepheus.png" width="425">

# Running Windows on the Xiaomi Mi 9

## Uninstallation

### Why is this needed?

If you want to uninstall windows this is used instead of deleting partitions manually to avoid human error + writing a whole dedicated guide to just uninstalling.

If you want to relock your bootloader you'll need your partition table to be stock.

### Prerequisites

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
- [gpt_both0.bin](../../../../releases/tag/1.0)

### Restore GPT
> Replace ```<gpt_both0.bin>``` with the path to the gpt_both0.bin file.

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

### Erase userdata to avoid bootloop and restore FS size
```cmd
fastboot -w
```
