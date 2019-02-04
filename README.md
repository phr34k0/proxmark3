Proxmark3 RDV4.0 Dedicated Github
===============
This repo is based on iceman fork for proxmark3. It is dedicated to bringing the most out of the new features for proxmark3 RDV4.0 new hardware and design.

[![Latest release](https://img.shields.io/github/release/RfidResearchGroup/proxmark3.svg)](https://github.com/RfidResearchGroup/proxmark3/releases/latest)

<a href="http://www.youtube.com/watch?feature=player_embedded&v=uyJ-y0kSWfc
" target="_blank"><img src="https://github.com/5w0rdfish/proxmark3/blob/master/prox.png" 
alt="Yuotube" width="100%" height="auto" border="10" /></a>


# Donations
Nothing says thank you as much as a donation,  https://www.patreon.com/iceman1001

---

# PROXMARK INSTALLATION AND OVERVIEW


| FAQ's & Updates     | Installation        | Use of the Proxmark |
| ------------- |:-------------:| -----:|
|[Whats changed?](#whats-changed)  | [Setup and build for ArchLinux](/Installation_Instructions/Arch-Linux-Installation-Instructions.md) | [Validating proxmark client functionality](/Use_of_Proxmark/1_Validation.md)|
|[Development](#development) | [Setup and build for UBUNTU](/Installation_Instructions/Ubuntu-Installation-Instructions.md)  | [Verification and Configuration](/Use_of_Proxmark/2_Configuration-and-Verification.md) |
| [Why don't you add this or that functionality?](#why-dont-you-add-this-or-that-functionality)  | [Homebrew (Mac OS X) & Upgrading HomeBrew Tap Forumula](/Installation_Instructions/Mac-OS-X-Homebrew-Installation-Instructions.md) | [Commands & Features](/Use_of_Proxmark/3_Commands-and-Features)|
|[Why didn't you based it on offical PM3 Master?](#why-didnt-you-based-it-on-offical-pm3-master) |[ParrotOS (Debian) Installation ](/Installation_Instructions/Parrot-OS-Proxmark3-RDV4-installation.md)|
|[Notices](#notices)|[Setup and build for Windows](/Installation_Instructions/Windows-Installation-Instructions.md)|[PM3 GUI](#pm3-gui)|
|[Issues](#issues)|[Coverity Scan Config & Run](/Installation_Instructions/Coverity-Scan-Config-%26-Run.md)||
|||

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

## the end

`iceman at host iuse.se`
`July 2018, Sweden`
`revamped for Jan 2019 @5w0rdfish`
