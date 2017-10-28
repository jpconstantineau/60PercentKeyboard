# How to build firmware with QMK

Here are the instructions for Windows 10. If you use MAC or linux, what needs to be done will be different.

## Clone/download the GIT Repository
### If you have GIT for windows
- Navigate to the root folder where you want to clone the QMK repository
- "Right-Click" in the root folder and select "GIT GUI Here"
- Select "Clone"
- In Source Location, type in the GIT url (https://github.com/qmk/qmk_firmware.git)
- in Destination Folder, type in the windows folder you want to create

### If you don't have GIT
- Download the zip file of the [repository](https://github.com/qmk/qmk_firmware)
- unzip to where you want your folder to be. Rename as needed.

## Install Build Tools
Follow the Install Build Tools instructions from the [QMK documentation](https://docs.qmk.fm/getting_started_build_tools.html)
- Install msys2 by downloading and following the instructions here: http://www.msys2.org
- Open the "MSYS2 MingGW 64-bit" shortcut
- Navigate to your qmk checkout. For example, if it's in the root of your c drive:
- $ cd /c/qmk_firmware
- Run util/msys2_install.sh and follow the prompts

## Run a test build to build everything
Detailed instructions [here](https://docs.qmk.fm/getting_started_make_guide.html)

For Wiondows 10, this works:
- Open the "MSYS2 MingGW 64-bit" shortcut
- Navigate to your qmk checkout. For example, if it's in the root of your c drive:
- $ cd /d/GIT/qmk_firmware
- Make fron the qmk_firmware folder - not the keyboard folder. This one will build everything
- $ make all:all
- This make will only build one firmware.
- $ make xd60:default


## Flashing QMK to XD60
For flashing the default QMK firmware for the XD60 board, run through these commands:

- $ dfu-programmer atmega32u4 erase
- $ dfu-programmer atmega32u4 flash xd60_default.hex
- $ dfu-programmer atmega32u4 launch

Prior to running these commands, you need to put the keyboard in "bootloader" mode.  Do so by pressing the reset button as you connect the keyboard.  The first command erases the flash memory. The second flashes the firmware while the last reboots the keyboard. On restart, the keyboard will connect bact to the computer as a keyboard.  The default firmware will turn on PCB backlight on.


[Keymap FAQ](https://docs.qmk.fm/faq_keymap.html)