# Setup and build for ArchLinux

Run
```sh
sudo pacman -Sy base-devel p7zip libusb readline ncurses arm-none-eabi-newlib --needed
```
```sh 
yaourt -S termcap
```

Remove modemmanager
```sh
sudo apt remove modemmanager
```

Clone fork
```sh
git clone https://github.com/RfidResearchGroup/proxmark3.git
```

Get the latest commits
```sh
git pull
```

Install the blacklist rules and  add user to dialout group (if you on a Linux/ubuntu/debian). 
If you do this one, you need to logout and login in again to make sure your rights got changed.
```sh
make udev
```

Clean and complete compilation
```sh
make clean && make all
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
