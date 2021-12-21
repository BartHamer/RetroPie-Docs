***
![atarist](https://cloud.githubusercontent.com/assets/10035308/12189255/60af20aa-b579-11e5-88bc-8b57576dbfad.png)
***
_The Atari ST, STE, TT, and Falcon were a series of personal computers released by Atari starting in 1985._
***

| Emulator | Rom Folder | Extension | BIOS |  Controller Config |
| :---: | :---: | :---: | :---: | :---: |
| [Hatari](http://hatari.tuxfamily.org/) | atarist  | .st .stx .msa .img .rom .raw .ipf .ctr | TOS 1.00, 1.02, 1.04, or 2.06 (ST) <br> TOS 1.xx or 2.xx (STE) <br> TOS 3.0x (TT) <br> TOS 4.0x (Falcon) | hardcoded |
| [lr-hatari](https://github.com/libretro/hatari) | atarist  | .st .stx .msa .img .rom .raw .ipf .ctr .zip .m3u | TOS 1.00, 1.02, 1.04, or 2.06 (ST) <br> TOS 1.xx or 2.xx (STE) <br> TOS 3.0x (TT) <br> TOS 4.0x (Falcon) | Retroarch config|

Much of the emulation for later models, such as the Falcon, is still experimental so some games may be hit and miss.

## Emulator: [lr-hatari](https://github.com/libretro/hatari)

lr-hatari can currently be found under the experimental installs in RetroPie.

### BIOS

TOS (The Operating System; also Tramiel Operating System, from Jack Tramiel, owner of Atari Corp. at the time) is the operating system of the Atari ST range of computers. Atari's TOS was usually run from ROM chips contained in the computer. See <https://en.wikipedia.org/wiki/Atari_TOS>.

To use this core you need a valid TOS ROM image named `tos.img` in BIOS folder:
```
~/RetroPie/BIOS/tos.img
```

Using a Version 1.04 TOS file is also a good choice for general compatibility.

### ROMS

Accepted File Extensions: **.st .stx .msa .img .rom .raw .ipf .ctr .m3u .zip**

Unlike the standalone Hatari, lr-hatari supports `.m3u` files and `.zip` files.

Place your Atari ST/STE/TT/Falcon ROMS in
```
/home/pi/RetroPie/roms/atarist
```

### Disk images

The Atari ST was a disk based computer so you need a disk image of the software you want to use with the emulator.

Accepted File Extensions: **.st .msa .ipf**

When launched with a valid disk image the emulator will automatically launch the program (most of the time) or open the TOS with disk inserted into drive A. In the TOS you need to manually launch the program by opening Drive A (double-click on the drive icon) and finding/selecting a .prg file (double-click on the file icon).

Note that certain global retroarch configurations can cause crashes with the emulator - If this appears to be happening (i.e. The emulator crashes back to emulationstation when loading .st files), try placing a factory-set retroarch.cfg file into the directory below:

```
/opt/retropie/configs/atarist
```

This will over-ride the global retroarch configuration and should allow access to the emulator to configure the controls for the system specifically.

### M3U Support and Disk control

When you have a multi disk game, you can use a m3u file to specify each disk of the game and change them from the RetroArch Disk control interface.

A M3U file is a simple text file with one disk per line (see <https://en.wikipedia.org/wiki/M3U>).

Example:

File: _Simpsons, The - Bart vs. The Space Mutants.m3u_, containing:

```
Simpsons, The - Bart vs. The Space Mutants_Disk1.st
Simpsons, The - Bart vs. The Space Mutants_Disk2.st
```

Path can be absolute or relative to the location of the M3U file.

When a game asks for it, you can change the current disk in the RetroArch 'Disk Control' menu :

    * Eject the current disk with 'Disk Cycle Tray Status'.
    * Select the right disk index.
    * Insert the new disk with 'Disk Cycle Tray Status'.

Note : zip support is provided by RetroArch and is done before passing the game to the core. So, when using a `.m3u` file, the specified disk image must be uncompressed (**.st, .msa, .ipf** file formats).

### Default Controls

lr-hatari uses Retroarch control configuration. The mouse is emulated by the joystick and can be toggled between mouse and joystick modes. The libretro port of Hatari also takes some settings from 

```
/opt/retropie/configs/atarist/hatari.cfg
```

If you are experiencing joystick issues, it may be helpful to check that the joystick setup in hatari.cfg is correct. To do this, launch a ROM with the standard Hatari (non-libretro version), launch the GUI and check that all joystick mappings are correct. Save the configuration settings and then reload lr-Hatari afterwards.

| Button | Command |
| :---: | :---: | 
| Left Joystick | Up, down, left, right |
| L2  | Show/Hide status | 
| R2  | Sound on/off |
| L   | Toggle Num Joy  |
| R  |  Change Mouse speed 1 to 6 (for gui and emu) |
| SEL | Toggle Mouse/Joy mode |
| STR | Show/Hide virtual keyboard |
| A   | Fire/Mouse button A / press key in virtual keyboard |
| B   | Mouse button B |
| X   |   |
| Y   | lr-hatari GUI |

Note that some games (e.g. Gauntlet II) require the simulation of the 'plugging-in' of a joystick. This can be done from the standard hatari gui by selecting 'disabled' followed by 'enabled' in the joysticks tab. However, this type of behaviour is not currently supported in lr-hatari as the retroarch pads are set up permanently at launch.

Furthermore, there is no current mapping of the space bar to a joystick button in lr-hatari as there is in the 'standard' version - this must currently be done using the on-screen keyboard. 

## Emulator: [Hatari](http://hatari.tuxfamily.org/)

### ROMS

Accepted File Extensions: **.st .stx .msa .img .rom .raw .ipf .ctr**

Place your Atari ST/STE/TT/Falcon ROMS in
```
/home/pi/RetroPie/roms/atarist
```
### Controls

While in game press F12 to open the Hatari main menu, to reconfigure controls select either joysticks or keyboards

Default Keyboard Controls:
```
Up: up
Down: down
Left: left
Right: right
Fire: RCTRL
to exit the emulator you can use alt+q or select quit from the F12 menu
```
