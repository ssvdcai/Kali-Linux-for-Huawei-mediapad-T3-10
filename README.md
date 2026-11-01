# Kali Linux for Huawei MediaPad T3 10 (agassi)



Linux port built using the postmarketOS kernel (v7.1.x) with custom patches for the **Huawei MediaPad T3 10 (agassi)**.



> [!NOTE]

> I am not an official developer doing this kind of thing, I am a 15-year-old... so please keep that in mind if something doesn't work. If you'd like, report any issues on XDA, but also consider that I have school and other responsibilities... I do this as a hobby!



---


<img width="650" height="300" alt="ok_edit" src="https://github.com/user-attachments/assets/2c77623c-54b7-4644-991a-68832e107c9e" />

## 🛠️ Features & Status



* **Audio:** Working sound (not perfect, but it works). Check `/usr/local/bin` for audio scripts if you want to improve them.

* **Volume Issues:** FreeTube audio can sound weird (crackling like a radio); use **VacuumTube** instead, which comes pre-installed.

* **Kernel & USB:** Uses postmarketOS kernel 7.1 with Ralink modules and added support for **RTL8812AU**. The `.dtb` is configured for USB host mode (adapters work).

* **USB Networking:** Due to the USB host mode modifications, USB networking does not work.

* **Wi-Fi:** If Wi-Fi doesn't start, check the `cust` partition on your tablet to locate the necessary `.ko.zst` files.

* **Compatibility:** Tested exclusively on **AGS-W09** (2 GB RAM / 16 GB storage). **Not tested** on AGS-L09.

* **Touchscreen:** Occasionally, the touch module doesn't load at boot. Simply reboot the tablet holding the power button to fix it.

* **Screen Rotation:** In the top-right corner of the panel, you'll find an icon named **Rotate**—it rotates both the screen and the touch axes simultaneously.

* **Gestures:** Configured `touchegg` as a background service: touching the screen with two fingers acts as a right-click.

* **V-RAM / Swap:** Uses a 1 GB file for V-RAM (`/swapfile`). It is strongly recommended to leave it enabled, though you can delete it if storage is critically low (the system will run less smoothly).

* **GPU & Rendering:** The GPU acts strangely in Firefox and overall UI. Everything currently runs on **software rendering**. If you can fix this or provide a patch/report, contributions are very welcome!



---



## ⚠️ Important Warnings & Partitioning



* **EDL Backup (Mandatory Precaution):** Before making any changes or flashing, always create a full EDL backup using:

  ```bash

  edl rl . --loader=firehose.mbn

  ```

* **Storage Optimization (Risky / Optional):** A strongly recommended (but risky) tweak is to shrink the system partition to free up space (setting it to 1 MB and mapping its starting point correctly in the partition layout). Proceed only if you know what you are doing!



---



## 📥 Download & Installation



* **USER PASSWORD:** `kali`

* **USERDATA IMAGE:** [Download from Mega.nz](https://mega.nz/file/THBjwJYb#saguvIMVdS_VmLFzrKHUHLAPEDQCPdP45WMJ5iUP_9s)



### Flash Instructions:

1. Download `userdata_sparse` from the link above.

2. Flash it via fastboot to the `userdata` partition so `lk2nd` can recognize it:

   ```bash

   fastboot flash userdata userdata_sparse.img

   ```

3. Flash the boot image (**this only works after flashing lk2nd**):

   ```bash

   fastboot flash boot lk2nd_agassi.img

   ```

   *(Note: If the tablet fails to boot, try flashing `lk2nd` into the recovery partition as well).*



---



*Sorry for my bad English, I am from Romania...*
