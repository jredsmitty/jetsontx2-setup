# Compiling OpenCV 3 with GStreamer support on Nvidia Jetson
**ON JETSON IN TERMINAL**

### First
```
sudo nvpmodel -m 0
sudo ./jetson_clocks.sh
```

## 1. Remove OpenCV4Tegra by running:
```
sudo apt-get purge libopencv4tegra-dev libopencv4tegra
sudo apt-get purge libopencv4tegra-repo
sudo apt-get update
```
## 2. Download Jetson Hacks’ Jetson TX2 OpenCV installer:
```
git clone https://github.com/jetsonhacks/buildOpenCVTX2.git
cd buildOpenCVTX2
```
## 3. Build OpenCV by running the install script. This will take some time.
```
./buildOpenCV.sh
```
```
cd /home/opencv/build
make
```
This should ensure that everything has been built.

After this, you can install the new build:
```
cd $HOME/opencv/build
sudo make install
```
