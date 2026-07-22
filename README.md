# 🐍 ViperOS Remastered & Optimized | Samsung Galaxy Tab E 9.6 (SM-T560)

> **A heavily debloated, highly optimized custom build of ViperOS (Android 7.1.2) specifically tailored to maximize RAM and breathe new life into the Wi-Fi only Galaxy Tab E 9.6.**

⚠️ **CRITICAL DEVICE WARNING:** ⚠️ 
**THIS ROM IS STRICTLY FOR THE SM-T560 (Wi-Fi ONLY) MODEL. DO NOT FLASH THIS ON THE SM-T561 (3G/Cellular) OR YOU WILL BRICK YOUR MODEM/RADIO.**

### Disclaimer & Credits

**I take ZERO credit for the original ROM base, the OS framework, or the custom kernel.** 
99% of the heavy lifting and critical development was done by the incredibly talented original ViperOS porters for this device, and the custom Kernel Developer **A404_**. 

* **Original ViperOS Port Thread:** [View on XDA-Developers](https://xdaforums.com/t/discontinued-port-rom-7-1-2-t-560-t-561-viperos-v5-1-for-galaxy-tab-e.4030325/)
* **Custom Overclocked Kernel Thread:** [View on XDA-Developers](https://xdaforums.com/t/kernel-lineageos-_3-10-108-for-stock-dotos-viperos-on-sm-t561.4729465/)

I simply took their amazing foundation, fixed some lingering bugs, completely overhauled the file system for extreme memory efficiency, and tailored it for my own personal use. I am uploading it here purely to help anyone else out there who still wants to use this tablet. All respect and credit go to the original devs.

---

## Extreme Optimization Features

This final version has been gutted, rewritten, and optimized at the file-system level to run incredibly smoothly on the T560's limited hardware. 

* **Integrated Kernel & Fixes:** The overclocked custom kernel by **A404_** and the `fix-battery.zip` patch are already baked directly into the ROM. There is no need to flash them separately. 
* **Massive Memory Savings:** Reduced the ROM zip size by **~100MB** and dropped background RAM usage by over **100MB**. The tablet now idles around **500MB - 650MB of RAM usage** (even with the Google Play Store installed).
* **Modern Web Rendering:** Updated the core Android System WebView to v117.0.5938.60. Modern websites no longer crash, SSL certificates work perfectly, and web-formatting layout issues are fixed.
* **UI & Keyboard Overhaul:** 
  * Adjusted the `build.prop` LCD Density to `213`. This completely fixes the microscopic tablet UI elements and properly scales the interface.
  * Replaced the laggy default AOSP keyboard with a custom, lightweight keyboard that is much faster and more comfortable to type on.
* **Deep File-System Debloat:**
  * Completely removed all RIL, telephony, SIM, and modem code. (This is a Wi-Fi tablet; the OS no longer wastes CPU cycles looking for a SIM card).
  * Purged heavy developer tools, SSH binaries, useless trace files, and orphaned dummy `.rc` scripts to free up system space.
* **Advanced `build.prop` Tweaks:**
  * Fixed the screen-off Wi-Fi disconnect bug by adjusting power collapse and sleep policy states.
  * Applied targeted hardware acceleration UI tweaks, GPU compositor forces, and memory dynamics overhauls. 
  * Spoofed the Android Security Patch to the latest available date to trick modern apps into installing and maintaining compatibility.
  * Disabled the redundant Android Setup Wizard network check to speed up the first boot.
* **Aesthetic Tweaks:** Replaced the heavy, laggy default boot animation with the sleek, lightweight Google Pixel dots animation.

---

## ⚠️ Limitations & Known Changes ⚠️

To achieve these extreme memory savings, some native Android features had to be sacrificed. Please read these before flashing:

* **Language Support:** **English Only.** All other system languages, fallback fonts, and hyphenation dictionaries were stripped to save memory.
* **No Wallpaper Chooser:** The native Android wallpaper picker app was removed because it consumed too much background RAM and storage. **Workaround:** Simply download a picture from Google/Chrome, open your Gallery, and select "Set as Wallpaper."
* **Limited Audio Profiles:** I removed the massive system audio library. There is now only **1 ringtone, 1 notification tone, and 1 UI sound** available out of the box. 
* **Live Wallpapers Disabled:** The XML framework allowing Live Wallpapers was removed to prevent accidental CPU drain.

---

## Installation Instructions

1. Boot into TWRP Recovery.
2. **CRITICAL:** Perform a **Clean Wipe** (Dalvik, Cache, System, and Data). *Do not dirty flash or you will get a Wi-Fi Authentication Error on boot!*
3. Flash the ROM zip.
4. Flash your preferred GApps package (Pico or Nano recommended).
5. Reboot and enjoy! (First boot may take 3-5 minutes).
