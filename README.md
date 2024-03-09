```
#
# Copyright (C) 2024 The Android Open Source Project
# Copyright (C) 2024 SebaUbuntu's TWRP device tree generator
# Copyright (C) 2024 The LineageOS Project
#
# SPDX-License-Identifier: Apache-2.0
#
```
Device configuration for Lenovo Tab M8 (FHD)
 =========================================

  The Lenovo Tab M8 (FHD) (codenamed "8705F") is a 
budget tablet from Lenovo.

  It was announced and released in September 2019.

  ## Device specifications

  Basic | Spec Sheet
 -------:|:-------------------------
 SoC | Mediatek MT6765 Helio P22T
 CPU | Octa-core 2.3 GHz Cortex-A53
 GPU | PowerVR GE8320
 Memory | 3/4 GB RAM
 Shipped Android Version | 10.0
 Storage | 32/64 GB
 Battery | Non-removable Li-Polymer 5100 mAh battery
 Dimensions | 198.2 x 122.6 x 8.2 mm
 Display | 1200 x 1920 pixels, 16:10 ratio (~283 ppi density)
 Rear camera | 13 MP, AF
 Front camera | 5 MP      


## Flashing Instructions

- Enable developers options by tapping build number 7 times
- After this enable oem unlock option in the developers options
- Install the adb and fastboot drivers on your pc
- Download platform-tools
- Download the blankvbmeta.img and recovery.img from the release section of this repository
- Place these two image files in platform-tools folder and connect your tablet to the pc
- In the platform-tools folder open cmd
- In the cmd type adb devices to make sure that your device is connected and detected
```
adb devices

```
- Now type the commands as follows
```
adb reboot bootloader

```
- Now,
```
fastboot flashing unlock

```
- Now, press the volume up button wait for few seconds to unlock the bootloader of the device after it shows SUCCESS. Then proceed as follows:
```
fastboot flash vbmeta blankvbmeta.img

```
- Now finally flash the recovery
```
fastboot flash recovery recovery.img

```
- Now booting into recovery
```
fastboot reboot recovery

```
- Now wait for few seconds then recovery will open up
- Once the recovery is open if u see 0MB internal storage
- Go to the wipe option and format your data
- Then reboot to the recovery from reboot options
- Now enjoy your flashing !!!

# A tip for the ROMS flashing after the flashing is done
- Once the ROM is flashed
- Go to reboot options from there reboot to the bootloader
- Give this command
```
fastboot format userdata

```
- Then give this command 
```
fastboot reboot

```
