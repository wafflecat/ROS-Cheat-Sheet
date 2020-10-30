# Kinect V2 Instructions
## Install libfreenect
1. Download libfreenect2
```bash
git clone https://github.com/OpenKinect/libfreenect2.git
cd libfreenect2
```
2. Install build tools
```bash
sudo apt-get install build-essential cmake pkg-config
```
3. Install libusb (version >= 1.0.20), TurboJPEG, and OpenGL
```bash
sudo apt-get install libusb-1.0-0-dev
sudo apt-get install libturbojpeg libjpeg-turbo8-dev
sudo apt-get install libglfw3-dev
```
4. Build
```bash
mkdir build && cd build
cmake .. -DENABLE_CXX11=ON -DCMAKE_INSTALL_PREFIX=$HOME/freenect2
make
make install
```
## TEST libfreenect2
Run a test program
```bash
./bin/Protonect
```
You shouldn't need to ```sudo ./bin/Protonect```. If you have to to make it work, be
sure to give the software access to USB devices,
```bash
sudo cp platform/linux/udev/90-kinect2.rules /etc/udev/rules.d/
```

ERROR NOTE: Protonect segmentation fault, freezing error
Selecting nvidia-340 in Additional Drivers solved the problem
https://github.com/OpenKinect/libfreenect2/issues/923
