# Setup and build for UBUNTU
## Notes
GC made updates to allow this to build easily on Ubuntu 14.04.2 LTS, 15.10 or 16.04
See the [Proxmark3 Ubuntu wiki page](https://github.com/Proxmark/proxmark3/wiki/Ubuntu%20Linux)

A nice and cool install script made by @daveio is found here: 
https://github.com/daveio/attacksurface/blob/master/proxmark3/pm3-setup.sh

I have also added this script to the fork.
https://github.com/RfidResearchGroup/proxmark3/blob/master/install.sh

---
## Manual Installation

Run

```sh
sudo apt-get install p7zip git build-essential libreadline5 libreadline-dev libusb-0.1-4 libusb-dev libqt4-dev perl pkg-config wget libncurses5-dev gcc-arm-none-eabi
```

Clone fork

```sh
git clone https://github.com/RfidResearchGroup/proxmark3.git
```

Get the latest commits

```sh
git pull
```

Install the blacklist rules and add user to dialout group. 

```sh
make udev
```

Log in and log out of user ubuntu account to make sure rights have been changed. 

Clean and complete compilation
```sh
make clean && make all
```
	
Check location of proxmark 
```sh
dmesg | grep -i usb
```

Flash the BOOTROM & FULLIMAGE
```sh
client/flasher /dev/ttyACM0 -b bootrom/obj/bootrom.elf armsrc/obj/fullimage.elf
```
	
Change into the client folder
```sh
cd client
```
	
Run the client
```sh
./proxmark3 /dev/ttyACM0
```
