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








    
## Prerequisites
- ADB Installation: Follow the official ADB documentation to install ADB on your system.
- Root Access: Ensure your Android device is rooted to perform system modifications.

## Usage
Replace Boot Animation:

- Pull the current boot animation: adb pull /system/media/bootanimation.zip <local_path>
- Modify the boot animation as needed.
- Push the modified animation: adb push <local_path>/bootanimation.zip /system/media/bootanimation.zip
- Set appropriate permissions: adb shell su -c 'chmod 644 /system/media/bootanimation.zip'
- Reboot your device to see the changes.

Manage Applications:

- List installed packages: adb shell pm list packages
- Uninstall a package: adb shell pm uninstall --user 0 <package_name>
- Reinstall a package: adb install <path_to_apk>

# Contact
For any questions or issues, feel free to open an issue in the repository or contact me directly.
