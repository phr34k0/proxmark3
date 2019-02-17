# Building on Windows
You will need to use the Gator96100 Proxspace package to assist in your windows installation.
This can be downloaded from https://github.com/Gator96100/ProxSpace/
## Notes
If you receive gcc errors using v3.1 during build, use and download v2.2. This may assist. 
Please download one of these :
- https://github.com/Gator96100/ProxSpace/releases/tag/v3.1   (release v3.1 with gcc v7.3.0 )
- https://github.com/Gator96100/ProxSpace/releases/tag/v2.2   (release v2.2 with gcc v5.3.0 arm-none-eabi-gcc v7.1.0)

---
## Manual Installation
1) Install required drivers for your windows installation.
You can find out how to do this here: 

2) Install github

3) clone the required proxspace repo. https://github.com/Gator96100/ProxSpace/

4) Extract 'ProxSpace' to a location on drive without spaces. 
For example C:\Proxspace or D:\projects\public\proxmark\proxspace are ok whereas C:\My Documents\My Projects\proxspace is not.

5) Run runme.bat or runme64.bat depending on your Windows architecture.


6) Clone fork
`git clone https://github.com/RfidResearchGroup/proxmark3.git`

7) Copy all the contents of proxmark3 folder into the proxspace pm3 folder

8) return to the runme.bat and change directory into the pm3 folder 
Please note you will need to use the / syntax as you are using BASH.

To build the project type make clean && make all.

In most cases the Proxmark III needs to be flashed with the just compiled firmware for details see Firmware upgrading the Proxmark III.

To run the Proxmark III client type ./client/proxmark3.exe COM1 where COM1 is the USB port of the Proxmark III.

Check your firmware revision on the Proxmark III with hw ver

For basic help type help. Or for help on a set of sub commands type the command followed by help. For example hf mf help.

### Build and run

- Clone fork
`git clone https://github.com/RfidResearchGroup/proxmark3.git`

- Get the latest commits	
`git pull`

- CLEAN COMPILE
`make clean && make all`

Assuming you have Proxmark3 Windows drivers installed you can run the Proxmark software where "X" is the com port number assigned to proxmark3 under Windows. 
	
- Flash the BOOTROM & FULLIMAGE
`client/flasher.exe comX -b bootrom/obj/bootrom.elf armsrc/obj/fullimage.elf`
	
- Change into the client folder
`cd client`
	
- Run the client	
`proxmark3.exe comX`

