# Documentation

## Table of Contents

## NVIDIA Jetson TX2 Setup Guide

### Using Developer Kit

### Using carrier boards
In this project, Connect Tech Inc.'s [Orbitty Carrier](http://connecttech.com/product/orbitty-carrier-for-nvidia-jetson-tx2-tx1/) board is used.

As Kanye West said:

> We're living the future so
> the present is our past.

Steps for Jetson TX2 board (modify accordingly for other Jetson and CTI carrier boards):

[//]: <> (If you want to embed images, this is how you do it:)

[//]: # (![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png))


**L4T r32.2.0**

The CTI-L4T Board Support Package adds support for Connect Tech NVIDIA® Jetson™ Xavier and TX2i/TX2/TX1 carrier boards to Linux4Tegra. It includes any extra files required to use all the features of the carriers. You can click here to download the L4T Board Support Packages from our website. We provide board support packages for your AGX Xavier solutions and TX2i/ TX2/ TX1 solutions.

1. Click to download the Board Support Package and choose the appropriate L4T package for your Jetson TX2.
![Image of Yaktocat](https://github.com/rachit-aggarwal/docs/images/BSPLink_TX2_32_2.jpg)

2. Once you download your board support package, copy the downloaded CTI BSP into the ‘Linux_for_Tegra’ directory as shown in the terminal screenshot.

cp Downloads/CTI-L4t-V126.tgz ~/nvidia/nvidia_sdk/Jetpack_4.2.1_Linux_GA_P3310/Linux_for_Tegra
cd /nvidia/nvidia_sdk/Jetpack_4.2.1_Linux_GA_P3310/Linux_for_Tegra

3. Afterwards, extract the .tgz file to unload the CTI product profiles for flashing. Log in as root user using ‘sudo’ where you will be asked the the password for Ubuntu and run the install script to automatically install the board support package files to the correct locations on the host system.

tar -xzf CTI-L4T-V126.tgz
cd CTI-L4T
sudo install.sh

4. Before installing the board support package, please read the included readme.txt. To switch between different products, the TX2 will need to be re-flashed. Supported CTI product profiles will be listed when running the install.sh file. Once done, change back into the ‘Linux_for_Tegra’ directory . Now you can flash a TX2 using the NVIDIA Development kit or CTI carrier.

cd ..

5. Hold the recover button on the NVIDIA Development kit or CTI carrier, then press the power button. Connect a USB OTG cable from the NVIDIA Development kit or CTI carrier to the host computer. Type ‘lsusb’ to confirm the device is in recovery.

6. You may run an automatic flash script called the cti-flash.sh

./cti-flash.sh

Or you may manually flash the module with the correct profile for your your CTI carrier.
The profiles end with ‘.conf’. when flashing the board do not type the ‘.conf’ extension.

./flash.sh cti/tx2/<CTI Carrier Profile> mmcblk0p1

Here is a Table illustrating the different CTI Carrier profiles that can be flashed on the Jetson TX2.
 	Astro	Elroy	Orbitty	Spacely	Cogswell	Sprocket
TX2	astro-revG+
astro-mpcie
astro-usb3

*Requires
Breakout Board
XBG201 Rev F for
Jetson TX1/TX2	elroy-revF+
elroy-mpcie
elroy-usb3	orbitty	spacely-base
spacely-imx185-3cam
spacely-imx185-6cam
spacely-imx274-3cam
spacely-imx274-6cam	cogswell 	sprocket
sprocket-imx185
sprocket-imx274

7. Once you read the flash is successful prompt, the power can be cycled and the Jetson TX2 can be booted from its internal memory.

If flashed correctly, you should receive an output stating:
*** The target t186ref has been flashed successfully. ***


Sources:

* [CTI-L4T Board Support Package Installation for NVIDIA Jetpack with Connect Tech Jetson™ Carriers](http://connecttech.com/resource-center/flashing-jetson-tx2-tx2i-tx1-xavier/)
* [CTI-L4T NVIDIA® Jetson™ Xavier/TX2/TX1 Board Support Package Release Notes](http://connecttech.com/resource-center/cti-l4t-nvidia-jetson-board-support-package-release-notes/)


## Bonus
### Installing Ubuntu in Dual Boot Mode alongside Windows 10 UEFI
