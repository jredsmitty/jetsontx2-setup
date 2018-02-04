# Ubuntu Dual Boot w/ Windows

## Steps
1. If in Windows download [Rufus](https://rufus.akeo.ie) Portable so you do not have to install the full application. 
2. Download [Ubunut 16.04 LTS](http://releases.ubuntu.com/16.04/) desktop image. You can use 14.04, but 16.04 is supported for the Jetson TX2 JetPack software.
3. Open windows disk management and select your windows HDD. Right click and shrink the drive
![Disk Management Image](https://github.com/jredsmitty/jetsontx2-setup/blob/master/docs/dualboot/images/diskmanagement.PNG)
4. You will want to shrink it to give at least 80GB of space for the Ubuntu installation
5. Insert USB drive into Windows machine (8GB or larger).
6. Open Rufus on Windows machine
7. Select USB drive in device list in Rufus
8. Partition scheme should be UEFI (unless on older system)
9. Leave all else default
10. Next to *create a bootable disk image* make sure iso is selected and then browse to your iso image by pressing the image of the cd and drive.
11. Click start and select *make this an iso image*
12. Shut down windows
13. Follow [guide](https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-desktop#0) from Ubuntu for installing from USB (when booting Windows from usb you may have to change your boot selection - typically F12 or F8 at boot) NOTE:When at step 6 in guide you should see an option to install along side Windows. That will be the easiest option. 
14. After install is complete you will see the grub loader on boot. This will allow you to choose ubuntu or windows everytime you boot the machine. 
## Next Steps for Ubuntu
- Boot into Ubuntu from the grub loader at boot
- Go to Unity dash on the top left corner and type in **software and updates**
![Ubuntu Update](https://github.com/jredsmitty/jetsontx2-setup/blob/master/docs/dualboot/images/Ubuntu-Software-Updater.png)
- Go to the other software tab and select the to options for **Canonical Partners**
- Now use the built in sofware updater to update your Ubuntu software
- After that you will want to open up a terminal session and enter these commands one after the other
```
sudo apt-get update
sudo apt-get upgrade
```
- Let each of those complete and reboot if needed
### DONE
