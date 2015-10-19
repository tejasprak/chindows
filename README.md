# chindows
all of the chromebook on windows stuff
Step 1 Chrome OS stuff:

(developer mode will wipe everything on your chromebook)Put chromebook in Developer mode 

by pressing ESC + REFRESH + POWER, pressing CTRL-D at the first prompt, and then pressing 

CTRL-D at the next prompt. 

Step 2 Removing the write protect screw

Remove the bottom panel of the laptop by removing the 12 visible screws and another one 

underneath the warranty sticker.

Separate the plastic starting at the back.

Remove completely the write-protect screw from the motherboard, which is labelled as #7 in this 

picture: http://www.chromium.org/_/rsrc/1381990807648/chromium-os/developer-information-
for-chrome-os-devices/acer-c720-chromebook/c720-chromebook-annotated-innards.png

Step 3 Flashing new BIOS:

We're flashing custom coolStar BIOS. 

Download https://johnlewis.ie/Chromebook-ROMs/utils/flashrom.

Press CTRL-ALT-T in a browser to open the crosh shell.

Type in shell, then cd to the folder with flashrom.

When that's done, type in "sudo flashrom -r originalbios.bin"

This will backup your stock bios. Put that into your gdrive, dropbox, or a flash drive (anything). 

Keep it in case you need stock at any time. 

Download System, a google extension. That will tell you which CPU you have. 

Depending on that, please download the given ROM.

Celeron 2955U

https://dl.dropboxusercontent.com/u/59964215/chromebook/ROM/coreboot-seabios-
peppy-20151010-coolstar-2955u.rom

Celeron 2957U

https://dl.dropboxusercontent.com/u/59964215/chromebook/ROM/coreboot-seabios-
peppy-20151010-coolstar-2957u.rom

i3-4005U

https://dl.dropboxusercontent.com/u/59964215/chromebook/ROM/coreboot-seabios-
peppy-20151010-coolstar-i3.rom

Download it and put it in the same folder as the flashrom executable.

Do flashrom -w <ROM> and wait. DO NOT INTERRUPT OR ELSE YOU'LL HAVE A 200 DOLLAR 

BRICK.

Create your Windows 10 installer. Use a USB drive and the program Rufus. Choose MBR.

You will need an external keyboard and mouse, as the drivers will not be working for the trackpad 

and keyboard.

Step 4

Install Windows:

Restart your Chromebook.

Since the BIOS is custom, you can press ESC and choose your USB.

At the second screen, press Repair, and open up your command line. type in diskpart, list disk, 

select disk 0 (or whichever the 16GB SSD is), and clean. Then exit twice. Restart and install 

normally. Make sure when it restarts it boots into the SSD, not your USB. Windows will boot up 

and you can just wait. When it is done and you are in Windows, open up an elevated command 

prompt. Type in bcdedit -TESTSIGNING on. Reboot.

Step 5: Keyboard driver

When you are done, restart and there should be three "unknown devices" in Device Manager. 

Right click on the first one, press properties, then the third tab and change it to Hardware ID. 

Keep going through them until you find one with Hardware ID: ACPI\GGL0303. That's the 

keyboard.

I found croskeyboard2 won't work right, so download croskeyboard3: https://

dl.dropboxusercontent.com/u/59964215/chromebook/x64/croskeyboard3.1.zip

Unzip and put it in a folder. Right click on the keyboard in device manager and press update 

drivers. Find your drivers and install. 

Step 6: Trackpad driver

Find an unknown device with the ID ACPI\VEN_CYAP&DEV_0000” or “ACPI\CYAP0000.

If you do not have that device, find “ACPI\VEN_ELAN&DEV_0000” or “ACPI\ELAN0000”. 

For the first one, download https://dl.dropboxusercontent.com/u/59964215/chromebook/x64/

crostrackpad2.6.zip

For the second, download https://dl.dropboxusercontent.com/u/59964215/chromebook/x64/

crostrackpad2.0-elan.zip

Either way, right click on the device, click update drivers, and install your respective drivers.

Step 7: Audio/Chipset drivers

Run both of these installers

http://global-download.acer.com/GDFiles/Driver/Audio/

Audio_Realtek_6.0.1.7300_W81x64_A.zip?

acerid=635738343347305573&Step1=NOTEBOOK&Step2=ASPIRE&Step3=ASPIRE

%20E5-571&OS=81P1&LC=en&BC=ACER&SC=PA_6

http://global-download.acer.com/GDFiles/Driver/Chipset/

Chipset_Intel_9.4.0.1026_W81x64_A.zip?

acerid=635230454499383810&Step1=NOTEBOOK&Step2=ASPIRE&Step3=ASPIRE

%20E1-532&OS=81P1&LC=en&BC=ACER&SC=PA_6

Step 8: Graphics Card drivers:

much harder and doesn't really work.