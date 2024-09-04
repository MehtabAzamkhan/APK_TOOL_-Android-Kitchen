# Custom Firmware Project

## Overview
This project involves modifying the firmware of the OnePlus 3T smartphone to customize its UI and features. We have made changes to specific APK files and the boot image to enhance or modify the device's functionality and appearance.

## Project Components
- firmware-res.apk: Edited to customize system resources and UI elements.
- systemui.apk: Modified to alter the system user interface and functionality.
- boot.img: Customized using Android Kitchen to include the changes made in the APKs.
  
## Tools Used
- Android Kitchen: Used for unpacking and repacking the boot image.
- APKTool: Used for decompiling and recompiling APK files.
- Java Development Kit (JDK) 17: Required for working with APK files.

# Steps to Reproduce

## Prepare Your Environment
- Ensure you have Android Kitchen, APKTool, and the JDK installed on your system.
Backup your device data before proceeding

## APK Modification
- Decompile firmware-res.apk and systemui.apk using APKTool:

apktool d firmware-res.apk
apktool d systemui.apk

- Make the desired changes to the decompiled files.
- Recompile the APKs

apktool b firmware-res -o firmware-res.apk
apktool b systemui -o systemui.apk

## Boot Image Modification
- Extract the existing boot.img using Android Kitchen:
./android-kitchen.sh -x

- Replace the modified APKs in the appropriate directories.
- Repack the boot.img

./android-kitchen.sh -o

## Flashing the Modified Firmware

- Flash the modified boot.img to your OnePlus 3T using a custom recovery like TWRP.
- Ensure the new APKs are properly installed and replace the old ones.

# Contact
For any questions or issues, feel free to open an issue in the repository or contact me directly.
