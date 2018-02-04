# Ubuntu Dual Boot w/ Windows

## Steps
1. If in Windows download [Rufus](https://rufus.akeo.ie) Portable so you do not have to install the full application. 
2. Download [Ubunut 16.04 LTS](http://releases.ubuntu.com/16.04/) desktop image. You can use 14.04, but 16.04 is supported for the Jetson TX2 JetPack software.
3. Open windows disk management and select your windows HDD. Right click and shrink the drive
4. You will want to shrink it to give at least 80GB of space for the Ubuntu installation
4. Insert USB drive into Windows machine (8GB or larger).
5. Open Rufus on Windows machine
6. Select USB drive in device list in Rufus
7. Partition scheme should be UEFI (unless on older system)
8. Leave all else default
9. Next to *create a bootable disk image* make sure iso is selected and then browse to your iso image by pressing the image of the cd and drive.
10. Click start and select make this an iso image
11. Shut down windows
12. Follow [guide](https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-desktop#0) from Ubuntu for installing from USB (when booting Windows from usb you may have to change your boot selection - typically F12 or F8 at boot) NOTE:When at step 6 in guide you should see an option to install along side Windows. That will be the easiest option. 
13. After install is complete you will see the grub loader on boot. This will allow you to choose ubuntu or windows everytime you boot the machine. 
