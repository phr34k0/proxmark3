# Building on Windows
You will need to use the Gator96100 Proxspace package to assist in your windows installation.
This can be downloaded from https://github.com/Gator96100/ProxSpace/

## Notes
If you receive gcc errors using v3.1 during build, download and use v2.2. This may help resolve the issue.

- https://github.com/Gator96100/ProxSpace/releases/tag/v3.1   (release v3.1 with gcc v7.3.0 )
- https://github.com/Gator96100/ProxSpace/releases/tag/v2.2   (release v2.2 with gcc v5.3.0 arm-none-eabi-gcc v7.1.0)

---
## Manual Installation
1) Install required drivers for your windows installation.
(This is covered in the video)

2) Install Github for Windows https://desktop.github.com/

3) Download the required proxspace repo. https://github.com/Gator96100/ProxSpace/

4) Extract 'ProxSpace' to a location on drive without spaces. 
For example C:\Proxspace or D:\projects\public\proxmark\proxspace is ok whereas C:\My Documents\My Projects\proxspace is not.

6) Clone fork
```sh
git clone https://github.com/RfidResearchGroup/proxmark3.git
```

7) Copy all the contents from the proxmark3 folder into the proxspace pm3 folder

8) Run runme.bat or runme64.bat depending on your Windows architecture.

Please note you will need to use / as you are using BASH.

9) CLEAN COMPILE
```sh
make clean && make all
```

10) Flash the BOOTROM & FULLIMAGE
```sh
client/flasher.exe comX -b bootrom/obj/bootrom.elf armsrc/obj/fullimage.elf
```
	
11) Change into the client folder
```sh
cd client
```

Assuming you have Proxmark3 Windows drivers installed you can run the Proxmark software where "X" is the com port number assigned to proxmark3 under Windows. 

12) Run the client	
```sh
./proxmark3.exe comX
```

13) Check your firmware revision on the Proxmark III with 
```sh
hw ver
```
For basic help type help. Or for help on a set of sub commands type the command followed by help. For example hf mf help.




