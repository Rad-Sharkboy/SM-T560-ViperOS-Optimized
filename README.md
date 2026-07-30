# 🐍 ViperOS Remastered & Optimized | Samsung Galaxy Tab E 9.6 (SM-T560)

> **A heavily debloated, highly optimized custom build of ViperOS (Android 7.1.2) specifically tailored to maximize RAM and breathe new life into the Wi-Fi only Galaxy Tab E 9.6.**

⚠️ **CRITICAL DEVICE WARNING:** 
**THIS ROM IS STRICTLY FOR THE SM-T560 (Wi-Fi ONLY) MODEL. DO NOT FLASH THIS ON THE SM-T561 (3G/Cellular) OR YOU WILL BRICK YOUR MODEM/RADIO.**

### Disclaimer & Credits:

**I take ZERO credit for the original ROM base, the OS framework, or the custom kernel.** 
99% of the heavy lifting and critical development was done by the incredibly talented original ViperOS porters for this device, and the custom Kernel Developer **A404_**. 

* **Original ViperOS Port Thread:** [View on XDA-Developers](https://xdaforums.com/t/discontinued-port-rom-7-1-2-t-560-t-561-viperos-v5-1-for-galaxy-tab-e.4030325/)
* **Custom Overclocked Kernel Thread:** [View on XDA-Developers](https://xdaforums.com/t/kernel-lineageos-_3-10-108-for-stock-dotos-viperos-on-sm-t561.4729465/)

I simply took their amazing foundation, fixed some lingering bugs, completely overhauled the file system for extreme memory efficiency, and tailored it for my own personal use. I am uploading it here purely to help anyone else out there who still wants to use this tablet. All respect and credit go to the original devs.

---

## ⚡ Extreme Optimization Features

This final version has been gutted, rewritten, and optimized at the bare-metal ramdisk level to run incredibly smoothly on the T560's limited legacy hardware. 

* **Master Ramdisk Optimization:** The kernel boot image has been surgically stripped of over 500+ lines of generic AOSP, Qualcomm, and HTC code. I/O block queues are forced to the `deadline` scheduler natively, eMMC entropy generation is disabled, and CPUSets strictly pin background tasks to a single core while giving the UI access to all 4 cores.
* **Massive Memory Savings:** Reduced the ROM zip size by **~100MB** and gutted background OS RAM usage. The tablet now idles around **425MB - 550MB of RAM usage** (even with the Google Play Store installed), leaving a more of the memory for active apps/games.
* **Integrated Kernel & Fixes:** The overclocked custom kernel by **A404_** and the `fix-battery.zip` patch are already baked directly into the ROM. 
* **Complete RIL / Telephony Purge:** Every single trace of cellular code has been wiped from the OS. From Spreadtrum 3G daemons in `ueventd` to `Telecom.apk` in the system framework, the tablet no longer wastes a single CPU cycle looking for a SIM card.
* **UI & Display Scaling Fixes:** 
  * The `build.prop` has been corrected with the exact physical dimensions of the 9.6-inch panel (Width: 207mm, Height: 129mm). LCD Density is set to `200` to properly scale the UI, fixing the microscopic default interface.
  * Replaced the laggy default AOSP keyboard with a custom, lightweight keyboard that is much faster and more comfortable to type on.
  * Fixed the Multi-User soft-reboot trap by completely disabling the Android System Profile engine (`fw.max_users=1`).
* **Advanced `build.prop` Tweaks:**
  * Fixed the screen-off Wi-Fi disconnect bug by adjusting power collapse and sleep policy states. [NEED MORE TESTING]
  * Spoofed the Android Security Patch to the latest available date to trick modern apps into installing.
  * Disabled the redundant Android Setup Wizard network check to speed up the first boot.
* **Modern Web Rendering & Aesthetics:** Updated the core Android System WebView to v117. Modern websites no longer crash, SSL certificates work, and layout issues are fixed. The heavy default boot animation was replaced with a sleek, lightweight Google Pixel dots animation.

---

## 🐛 Known Bugs

While this ROM is highly stable for daily use, there are two lingering bugs carried over from the source base:
1. **Random Restarts Under High Load:** Occasionally, putting the CPU under maximum load may cause a random reboot. This is caused by the custom Overclocked Kernel (by A404_) and is beyond my ability to patch.
2. **Wi-Fi Notification Ping (Screen Off):** Sometimes, when the screen turns off, the tablet will constantly play a notification sound reporting "Wi-Fi connected but no internet" but disappears when screen is turned on. 

---

## ⚠️ Limitations & Known Changes ⚠️

To achieve these extreme memory savings, some native Android features had to be sacrificed. Please read these before flashing:

* **Language Support:** **English Only.** All other system languages, fallback fonts, and hyphenation dictionaries were stripped to save memory.
* **No Wallpaper Chooser:** The native Android wallpaper picker app was removed because it consumed too much background RAM and storage. **Workaround:** Simply download a picture from Google/Chrome, open your Gallery, and select "Set as Wallpaper."
* **System Apps Removed:** To keep the OS RAM footprint tiny, PrintSpooler, ContactsProvider, CalendarProvider, and Live Wallpapers have been permanently removed.
* **Limited Audio Profiles:** I removed the massive system audio library. There is now only **1 ringtone, 1 notification tone, and 1 UI sound** available out of the box. 

---

## 🛠️ Installation Instructions

1. Flash TWRP from http://twrp.me/samsung/gtel3g.html
2. Boot into TWRP Recovery.
3. **CRITICAL:** Perform a **Clean Wipe** (Dalvik, Cache, System, and Data). *Do not dirty flash or you will get a Wi-Fi Authentication Error on boot!*
4. Flash the ROM zip.
5. Flash your preferred GApps package (Pico or Nano recommended).
6. Reboot and enjoy! (First boot may take 3-5 minutes).
