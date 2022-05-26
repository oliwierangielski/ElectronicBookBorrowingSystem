# ElectronicBookBorrowingSystem
Application written in Kotlin Desktop and setup for raspberry Pi as electronic system for borrowing books


## 1. Raspberry Pi setting
This project was written and build for raspberry Pi 4b/3b with Rasbian Lite. Other computers and operating systems may not work
First of all you need to download the Raspbian Lite armhf (32bit)

https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2022-04-07/2022-04-04-raspios-bullseye-armhf-lite.img.xz


## 2 Assembling the TFT Screen 

Scheme for Raspberry pi 4b
```
VCC -> DC 3,3V (Pin 0)
GND -> GND (Pin 06)
CS -> CE0_N (Pin 24)
RESET -> IO 25 (Pin 22)
DC -> IO 24 (Pin 18)
MOSI -> MOSI (Pin 19)
SCK -> CLK (Pin 23)
LED -> IO 18 (Pin 12)
MISO -> MISO (Pin 21)

```
Touch Controllers will be added in the future


## 3 Setting up the Rasbian Lite
```
sudo raspi-config
```
-> connect to WIFI

```
sudo rpi-update
reboot
sudo apt install xorg xserver-xorg-video-fbturbo xfonts-cyrillic
```

Then you have to download drivers for fbtft screen.
Guide (https://learn.watterott.com/hats/rpi-display/fbtft-install/)

```
wget -N https://github.com/watterott/RPi-Display/raw/master/rpi-display.sh
$ sudo /bin/bash rpi-display.sh 270

Enable TFT display driver and activate X windows on TFT display? y/n Y
Activate the console on the TFT display? y/n Y
Install fbcp (Framebuffer Copy)? y/n N
Install xinput-calibrator? y/n Y
Install tslib (touchscreen library)? y/n Y
Reboot the system now? y/n Y
Rebooting now...
```

## 4. Installing Application Binaries //TODO
Now you have to clone this repository and copy the arm64 binary file to the  ~/ directory

## 5. Installing and setting qemu //TODO
Note that rasbian os archtecture is 32bit when the application architecture is 64 bit. You can't just run the application. Instead you need to download the qemu virtual machine and run it inside it

## 6. Creating Startup Files //TODO


