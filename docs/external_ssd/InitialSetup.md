# SSD Install for Jetson TX2
## Hardware
We will be using a SanDisk 240GB SSD Plus and the Jetson TX2 Developer Edition

- Power down Jetson and unplug form power cable. 
- Unpack the SSD and use the male to femal connector to plug the SSD into the SATA connector on the left side of the developer board. Once this has been done you can plug the Jetson back into power and boot up the board using the power button. 


Once you are back into the Linux environment on the Jetson search for the **Disks** utility from the main menu. 

Following the [JetsonHacks](http://www.jetsonhacks.com/2017/03/31/install-samsung-ssd-nvidia-jetson-tx2/) turtorial is trivial. 

Once this is complete you will have your new SSD ready for use and storage. 

## Root Directory on SSD
This will allow the jetson to use the SSD as the root directory. 

Open up a terminal and run this command. 
```
sudo cp -ax / <path to jetson ssd> && sync
```
The path for my jetson SSD is 
```
'/media/nvidia/JetsonSSD1'
```
The `&& sync` is so everything in memory on the Jetson gets copied over to the SSD. 
