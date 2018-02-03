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
