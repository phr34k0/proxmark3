
# Parrot OS Installation
First what we want to do is get an update for the system

```sh
sudo apt-get install update
```

grab the build requirements.

```sh
sudo apt-get install p7zip git build-essential libreadline5 libreadline-dev libusb-0.1-4 libusb-dev libqt4-dev perl pkg-config wget libncurses5-dev gcc-arm-none-eabi
```
If you do get any issues during the requirments installation, I have found it can help using the synaptic package manager. You can go one by one and grab all the requirements and dependencies. 

Next thing we want to do is clone the repo. 
```sh
git clone https://github.com/RfidResearchGroup/proxmark3.git
```

Get the latest commits , although its probably up to date.
```sh
git pull
```
Iceman has made the udev script which takes care of the blacklist rules. 
When you look at the Kali linux and Arch install you will see the equivalent and that is the remove modem manager command. 
In addition to this, the make udev command create's an alias for the pm3 under /dev. 

```sh
make udev
```
So log out and logg back in again. And now we are all set to take the next step. 
```sh
Clean and complete compilation make clean && make all
```
Once this is complete run the following comands to make sure the proxmark is being picked up by your computer. 
 ```sh
dmesg | grep -i usb
```
It should show up as a CDC device:
```sh
[10416.555108] usb 2-1.2: Product: PM3
[10416.555111] usb 2-1.2: Manufacturer: proxmark.org
[10416.555871] cdc_acm 2-1.2:1.0: ttyACM0: USB ACM device
```
So there is a online blog post which is great and is for Kali linux installation, during this installation he does mention that you need to press the button whilst pluggin the RDV4 in to your computer and to hold this the whole time the image is being flashed.  

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

or 
 ``` sh 
./proxmark3 /dev/pm  #press tab on the keyboard for it to detect the proxmark
```