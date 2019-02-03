Proxmark3 RDV40 dedicated repo,  based on iceman fork
===============
[![Latest release](https://img.shields.io/github/release/RfidResearchGroup/proxmark3.svg)](https://github.com/RfidResearchGroup/proxmark3/releases/latest)

## Notice      
This repo is based on iceman fork for proxmark3. It is dedicated to bring the most out of the new features for proxmark3 RDV40 device.

# Donations
Nothing says thank you as much as a donation,  https://www.patreon.com/iceman1001

---

| FAQ's & Updates     | Installation        | Use of the Proxmark |
| ------------- |:-------------:| -----:|
|[Whats changed?]()  | [Setup and build for ArchLinux]() | [Validating proxmark client functionality]()|
|[Development]()     | [Setup and build for UBUNTU]()  | [First things on your RDV40]() |
| [Why don't you add this or that functionality?]()  | [Homebrew (Mac OS X)]() | [Verify sim module firmware version]() |
|[Why didn't you based it on offical PM3 Master?]() |[Upgrading HomeBrew tap formula]()|[Commands & use] ()|
|Notices|[Setup and build for Windows]()|[PM3 GUI]()|
|Issues|[Coverity Scan Config & Run]()||

---
## Whats changed?
	* added flash memory 256kb.
	* added smart card module
	* added FPC connector

## Development
This fork now compiles just fine on 
   - Windows/mingw environment with Qt5.6.1 & GCC 4.8
   - Ubuntu 1404, 1510, 1604, 1804
   - Mac OS X / Homebrew
   - ParrotOS
   - WSL (Windows subsystem linux) on Windows 10
   - Docker container
---	
## Why didn't you based it on offical PM3 Master?
The separation from offical pm3 repo gives us very much freedom to create a firmware/client that suits the RDV40 features. We don't want to mess up the offical pm3 repo with RDV40 specific code.

## Why don't you add this or that functionality?
Give us a hint, and we'll see if we can't merge in the stuff you have. 
	
## PM3 GUI
The official PM3-GUI from Gaucho will not work.
The new universial GUI will work. [Proxmark3 Univerisal GUI](https://github.com/burma69/PM3UniversalGUI) 


## Notices
Kali and ArchLinux users usually must kill their modem manager in order for the proxmark3 to enumerate properly.   
`sudo apt remove modemmanager`
		   
## Issues
Please see the [Proxmark Forum](http://www.proxmark.org/forum/index.php) and see if your issue is listed in the first instance google is your friend :) Questions will be answered via the forum by Iceman and the team.



## Validating proxmark client functionality

If all went well you should get some information about the firmware and memory usage as well as the prompt,  something like this.

>[=] UART Setting serial baudrate 460800
>
>Proxmark3 RFID instrument
>
> [ CLIENT ]
>
> client: iceman build for RDV40 with flashmem; smartcard;
>
> [ ARM ]
>
> bootrom: iceman/master/4517531c-dirty-unclean 2018-12-13 15:42:24
>
>   os: iceman/master/5a34550a-dirty-unclean 2019-01-07 23:04:07
>
> [ FPGA ]
>
> LF image built for 2s30vq100 on 2018/ 9/ 8 at 13:57:51
>
> HF image built for 2s30vq100 on 2018/ 9/ 3 at 21:40:23
>
> [ Hardware ]
>
>--= uC: AT91SAM7S512 Rev B
>
>--= Embedded Processor: ARM7TDMI
>
>--= Nonvolatile Program Memory Size: 512K bytes, Used: 247065 bytes (47%) Free: 277223 bytes (53%)
>
>--= Second Nonvolatile Program Memory Size: None
>
>--= Internal SRAM Size: 64K bytes
>
>--= Architecture Identifier: AT91SAM7Sxx Series
>
>--= Nonvolatile Program Memory Type: Embedded Flash Memory
>
> pm3 -->

### Run the following commands
    pm3 --> hw status
    pm3 --> hw version
    pm3 --> hw tune

You are now ready to use your newly upgraded proxmark3 device.  Many commands uses the **h** parameter to show a help text. The client uses a arcaic command structure which will be hard to grasp at first.  Here are some commands to start off with.

    pm3 --> hf
    pm3 --> hf 14a info
    pm3 --> lf
    pm3 --> lf search

### Quit client
    pm3 --> quit


### First things on your RDV40
You will need to run these commands to make sure your rdv4 is prepared

    pm3 --> mem load f default_keys m
    pm3 --> mem load f default_pwd t
    pm3 --> mem load f default_iclass_keys i
    pm3 --> lf t55xx deviceconfig a 29 b 17 c 15 d 47 e 15 p

### Verify sim module firmware version
To make sure you got the latest sim module firmware.
_Lastest version is v3.10_

    pm3 --> hw status

Find version in the long output,  look for these two lines

    #db# Smart card module (ISO 7816)
    #db#   version.................v2.06

This version is obselete. The following command upgrades your device sim module firmware.
Don't not turn of your device during the execution of this command.

    pm3 --> sc upgrade f ../tools/simmodule/SIM010.BIN 
    
You get the following output,  this is a successful execution.    
    
    [!] WARNING - Smartcard socket firmware upgrade.          
    [!] A dangerous command, do wrong and you will brick the smart card socket          
    [+] Smartcard socket firmware uploading to PM3          
    ..
    [+] Smartcard socket firmware updating,  don't turn off your PM3!          
    #db# FW 0000          
    #db# FW 0080          
    #db# FW 0100          
    #db# FW 0180          
    #db# FW 0200          
    #db# FW 0280          
    [+] Smartcard socket firmware upgraded successful        
    

## the end

`iceman at host iuse.se`
`July 2018, Sweden`
