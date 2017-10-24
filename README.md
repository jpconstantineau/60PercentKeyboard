# 60PercentKeyboard
Designing a Custom 60% Keyboard


Focus of this project is to documents the steps and decisions taken while designing my own 60% keyboard.
It will be based on the XD60/XD64 PCB available on [Aliexpress](https://www.aliexpress.com/item/xd60-xd64-Custom-Mechanical-Keyboard-Kit-up-tp-64-keys-Supports-TKG-TOOLS-Underglow-RGB-PCB/32814945677.html?spm=a2g0s.13010208.99999999.265.hD2Zy9) or on [massdrop](https://www.massdrop.com/buy/xd60-xd64-custom-mechanical-keyboard-kit)

There are a number of decisions to take when designing your own custom 60% Keyboard.

## Design Steps
- [Select Keyboard Layout](https://github.com/jpconstantineau/60PercentKeyboard/blob/master/KeyboardLayout.md)
- [Select keycaps](https://github.com/jpconstantineau/60PercentKeyboard/blob/master/Keycaps.md)
- [Select switches](https://github.com/jpconstantineau/60PercentKeyboard/blob/master/Switches.md)
- [Select Mount Type](https://github.com/jpconstantineau/60PercentKeyboard/blob/master/Switches.md): PCB or Plate
- [Select Case](https://github.com/jpconstantineau/60PercentKeyboard/blob/master/Cases.md)
- Decide on backlight and leds

## Ordering

# Waiting for Items -  Receiving Items
Patiently waiting for everything to arrive. That's the had part!  Depending on shipping meethods, it can easily take 2 months for things to arrive...  

When receiving items, check them out as soon as possible. Depending on where you purchased them, any discrepency should be reported immediately. If the PCB was pre-programmed, you should be able to test it out to make sure it works.  If it wasn't pre-programmed, you need to program it with a basic/default firmware to be able to test out the board.


# Programming
There are lots of options to program a 60% ATMEL ATmega32u4 based keyboard.

## Easy AVR USB Keyboard Firmware and Keymapper
This is what skiwithpete uses and recommends to everyone.  Looks real easy.  Python 3.0 application.  
If your board is on the supported list, (or can find a python config file for it), then this should make it easy to evaluate and test your layers.

- [EasyAVR](https://github.com/dhowland/EasyAVR)
- [Windows Tutorial](https://github.com/dhowland/EasyAVR#windows-user-tutorial)
- [Youtuve how to use video](https://www.youtube.com/watch?v=utjdtSzWz6g)

[Here](https://imgur.com/a/aj3iF) is a good write-up of someone who used EasyAVR as part of their GH60 build.

## TMK Keymap generator
This is the app that some vendors recommend for their boards. You need to install a chrome add-in. Sounds simple enough. 

- [TMK Keymap Generator](https://tkg.io/#)

Vendor instructions for the XD60:
- Install the TKG Chrome App
- Fire up [yang.tkg.io](https://yang.tkg.io/)
- Keyboard is GH60 (RevXD_Mod)
- Choose "Simple" in layer mode, paste the URL of your layout from KLE.
- Click on the "Burn .eep file" dropdown and choose "RawHID", and then click on the actual Burn.eep file".

Sounds easy. [Here](https://imgur.com/a/WfmHW) is a good write-up of someone who used TKG as part of their GH60 build. [Second one](https://dionmunk.com/posts/2017/05/10/gh60-satan.html)


## TMK
[TMK](https://github.com/tmk/tmk_keyboard) is the original firmware.  QMK supports a much longer list of keyboards.

## QMK
If you are a programmer and want full customizability, QMK is it.  You will need to code, compile, build and flash your keyboard.
QMK probably has the longest list of supported boards all within their [repository](http://qmk.fm/keyboards/).  Note that the hex files ready to be uploaded to the AVR are already on the site.  As such, you don't need to compile the firmware if you just need the defaults. 

QMK allows enough programmability to allow to change how it behaves.  For example, [here](https://www.youtube.com/watch?v=I8MjRQazfJc) is a video on how you can modify the code to enable LED backlights to indicate what layers you are in and to show the status of caps lock, num lock and scroll lock.  This is the kind of functionality that makes LEDs useful for something as opposed just to look pretty and be distracting.

QMK is **not** for the noob. 

## Testing Board

Default 2u left shift is http://www.keyboard-layout-editor.com/#/gists/f249c49347e68c8b383a9ca16abd6623
Default 2.25u left shift is http://www.keyboard-layout-editor.com/#/gists/faf77c99388f0c5fbb26

# Building


## Useful Links
- [Keyboard Layout Editor KLE](http://www.keyboard-layout-editor.com/#/)
- [markdown cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
