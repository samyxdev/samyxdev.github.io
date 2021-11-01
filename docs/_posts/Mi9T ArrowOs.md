layout: page
title: "Mi9T Custom ROM Installation quick guide (ArrowOS)"
permalink: "quickguides"

# Links
- Download [Plateform Tools](https://developer.android.com/studio/releases/platform-tools)
- Download [Mi Unlocker](https://en.miui.com/unlock/download_en.html)
- Install [ADB & Fastboot drivers](https://forum.xda-developers.com/t/official-tool-windows-adb-fastboot-and-drivers-15-seconds-adb-installer-v1-4-3.2588979/) using XDAtool
- [TWRP for Mi 9t (davinci)](https://eu.dl.twrp.me/davinci/)

# Unlock bootloader
1. Install drivers using the 15 Seconds ADB Installer
2. Enable debugging mode in the device's developper Settings
3. In Developper Settings > Mi Unlock, add your Mi Account by following the procedure
4. Run a CMD in Admin :
`adb reboot bootlooader`
The device should now reboot into Fastboot mode.
5. Run a CMD in Admin :
`fastboot devices`
---
## If there is no devices displayed
- Go in Windows Device Manager
- Right click then click on update the Android device with an exclamation mark
- Select Drivers on your computer then click to choose among a list of already installed drivers
- In this list, select "Android > Android Fastboot drivers" for install
---

6. Now that the device is recognized in Fastboot mode, launch Mi Unlocker tool
7. Sign in your Mi Account in the Mi Unlocker tool
8. Click on the Unlock button for your device
9. If everything goes well, it should reboot several times and may appear as stuck on the MIUI screen for a few minutes, it's normal.

# Flash a custom recovery : TWRP
1. Reboot in fastboot using adb : `adb reboot bootlooader`
2. Check that fastboot recognize the device. For unknown reasons, Windows might lose the driver and you will have to reproduce the steps "If there is no devices displayed".
3. Flash the recovery : `fastboot flash recovery twrp.img`
4. Get ready to press Power + Vol Up after using `fastboot reboot`. If you're not able to boot into TWRP, the device will not let TWRP install and you will have to go back again to 1..
5. In TWRP, wipe data + cache

# Flash the custom ROM
1. Transfer the zip file of the ROM to the root of the device (MTP should work in TWRP)
2. Install the ROM using TWRP
3. Reboot to system and ArrowOS should appear

