Please download the driver patch, kernel code and gcc tool chain from links below.



Drivers: [Download Link](https://www.dropbox.com/sh/dzn01wte5akuwb1/AACqfpVqQpWfJ5tP4rSE8FFua?dl=0)
Download drivers on both the jetson and host machine. 


------Setup the driver on TX2



1. Download the L4T R28.1 for TX2 from link below and follow the quick start guide to flash the R28.1 image to TX2.
NOTE: go to 2


[Download Link](https://www.dropbox.com/sh/8p3kgws42csrulu/AADYMwGXYE2_qKjtPLVDawgta?dl=0)



Note: You can also download the Jetpack 3.1 (which includes the L4T R28.1) from Nvidia website and install it to TX2 if needed.

If you already flashed the TX2 OS image, you can skip step 1.


2. After boot up, copy Image and zImage (in driver download) to /boot on TX2.

3. copy 4.4.38-tegra-leopard.tgz to /lib/modules on TX2.

   ```
   sudo cp /home/nvidia/Downloads/Binaries/4.4.38-tegra-leopard.tgz /lib/modules

   cd /lib/modules

   sudo tar zxvf 4.4.38-tegra-leopard.tgz
   ```

4. **SKIP THIS STEP** Copy camera_overrides.isp to TX2 /var/nvidia/nvcam/settings (if there is isp file)

   sudo chmod 664 /var/nvidia/nvcam/settings/camera_overrides.isp

   sudo chown root:root /var/nvidia/nvcam/settings/camera_overrides.isp

5. Reboot TX2 and Put your system into "reset recovery mode" again by holding down the RECOVER (S3) button and press the RESET (S1) button once on the EVA board.

6. Connect the TX1 to your host PC with USB cable, and do

   ```
   lsusb
   ```
  NOTE: Make sure there is a device with “NVidia Corp.”

7. **ON HOST (Step 7&8) -** Copy and replace the tegra186-quill-p3310-1000-c03-00-base.dtb under Linux_for_Tegra/kernel/dtb on your host PC.

NOTE: Path to linux for tegra - home/"yourjetpackfolder"/64_TX2/Linux_for_Tegra_tx2/kernel/dtb
      rename current tegra186-quill-p3310-1000-c03-00-base.dtb to tegra186-quill-p3310-1000-c03-00-base.dtb.old with
      a right click and rename. Then copy and past 

8. In termianl
   ```
   cd /home/"yourjetpackfolder"/64_TX2/Linux_for_Tegra_tx2
   sudo ./flash.sh -r -k kernel-dtb jetson-tx2 mmcblk0p1
   ```
5. Reboot the TX2

6. Open a terminal and do "nvgstcapture-1.0”. You can will get live video output.


Note: Please make sure there is a camera on J3.



------Setup Argus software



Download the files from link below.

**ON JETSON**

[Download Link](https://www.dropbox.com/s/0t6388fsiocuvz7/argus_R28.1.tgz?dl=0)


**In Terminal**
1. sudo apt-get update

2. sudo apt-get install cmake

3. sudo apt-get install libgtk-3-dev

4. sudo apt-get install libjpeg-dev

5. sudo apt-get install libgles2-mesa-dev

6. sudo apt-get install libgstreamer1.0-dev

7. Copy the download from downloads folder to Home and then in terminal
   ```
   tar zxvf argus_R28.1.tgz
   ```

8. cd argus

9. mkdir build && cd build

10. cmake ..

11. make

12. sudo make install

13. In terminal
```
"argus_camera --device=0”, “argus_camera --device=1” and “argus_camera --device=2”to get the video output. 
```

