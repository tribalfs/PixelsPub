# Pixels - Smart Resolution and DPI Changer
* [Google Play Store](https://play.google.com/store/apps/details?id=com.tribalfs.pixels)

Pixels needs **WRITE_SECURE_SETTINGS** permission in order to work (this is NOT rooting). 

----------------------
### TLDR

 * Execute `adb shell pm grant com.tribalfs.pixels android.permission.WRITE_SECURE_SETTINGS`

----------------------
[VIDEO GUIDE](https://youtu.be/hKxc8wqanxA)
----------------------
### 1. Enable developer mode in phone's settings

 * Go to `Settings` > `About phone` > `Software information` and tap `Build number` multiple times until the developer mode is enabled.

![about phone](about_phone2.jpg)

### 2. Enable USB debugging

 * Go to `Settings` > `Developer options` (can be `Settings` > `System` > `Developer options` on older android versions), scroll down and find `USB debugging` option.

![adb](usb_debugging.jpg)

### 3. Download ADB on your computer

 * Download ADB (platform-tools) to your computer:
    for [Windows](https://dl.google.com/android/repository/platform-tools-latest-windows.zip) |
    for [Mac](https://dl.google.com/android/repository/platform-tools-latest-darwin.zip) |
    for [Linux](https://dl.google.com/android/repository/platform-tools-latest-linux.zip)
    
 * Extract the downloaded zip file.

### 4. Navigate to inside of `platform-tools` folder that you extracted on  Windows Explorer or Finder(macOS)


### 5. Opening the command-line interface

#### For Windows: Open up CMD
  
 * Type `cmd` in the address bar and press enter.  This will open Windows Command Prompt.

![opening_cmd](opening_cmd.png)

#### For MacOS: Open up Terminal

 * Search `Terminal` from Launchpad and run it.

 * Run `sudo -s` and type your user password. **The terminal won't display how much characters you type, it'll remain blank.**

 * Run `export PATH=.:$PATH`

 **Without this, you will get `adb: command not found` errors.**


### 6. Connecting your phone to your computer

 * Your phone will prompt `Allow USB debugging` if it's the first time being connected on USB debugging mode.  Tap `OK`.


![adb prompt](usb_debugging_prompt.jpg)

 * Check the connection by entering the following command followed by an enter. It should show your device ID if successfully connected.

 ```adb devices```
 
 ![6](adb_devices.png)
 
For macOS:  ```./adb devices ```
 
  * If your device fails to connect to your computer, try connecting it a different USB port and/or using a different USB data cable. If still not connecting, your computer is possibly missing the USB driver for your phone. Check [here to download OEM USB drivers](https://developer.android.com/studio/run/oem-usb#Drivers). Once installed, reboot your PC and redo step no. 6. 


### 7. Actual granting of WRITE_SECURE_SETTINGS permission to Pixels

 * When successfully connected, enter the following command and press enter. You can copy the command below.  If the command is executed properly, it will return blank.

 ```adb shell pm grant com.tribalfs.pixels android.permission.WRITE_SECURE_SETTINGS```

![6](write_secure_settings.png)

For macOS: ```./adb shell pm grant com.tribalfs.pixels android.permission.WRITE_SECURE_SETTINGS ```

Note: On some MIUI devices you need to enable the option "Disable permission Monitoring" under "Developer options" to be able to grant this permission.  If having a `java.lang.SecurityException` error, it's reported that turning on all debugging options helps.

**That's it!**

### 8. You may now disable the USB debugging settings

 * If you don't need USB debugging,  you may now disable the USB debugging settings to avoid potential unwanted access.

 * Go to `Settings` > `Developer options`, scroll down a page and **disable** `USB debugging` option.
 
 * **Important**: Keep  USB debugging enabled if you want to try exotic screen resolution(s) on your device that may potentially break the device UI. ADB commands to reset screen resolution: `adb shell wm size reset` and `adb shell wm density reset`.


----------------------


You don't have to repeat this process unless you completely uninstall the app and reinstall it.

----------------------
If you need more help or experiencing any issue, please email us at tribalfs@gmail.com .
