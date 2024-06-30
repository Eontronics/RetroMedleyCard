# RetroMedleyCard
Repository containing the RetroMedleyCard hardware design files.

RetroMedleyCard is a buisiness card sized PCB created for the [Hackaday 2024 Business Card Contest](https://hackaday.io/contest/195949-2024-business-card-contest) that aims to run a range of emulators with support for USB controllers, and output to full sized monitors/TVs, while maintaining a thicnkess <=2.0mm.

The Hackaday.io project page for RetroMedleyCard may be found at https://hackaday.io/project/196328-retromedleycard, which includes images of the physical hardware and testing

# Limitations
The current (first) iteration of RetroMedleyCard is severely limited by the ~2MB of onboard RAM, and various other issues:
* It has been successfully tested running Gameboy emulation without audio output, however other emulators often cause the system to crash immediately.
* The connectors are all formed using specially shaped PCB structures in order to maintain a thin form-factor, however these often fail to make reliable contact for audio, USB-C and SD card connections.
* Display output is limited to ~52fps @320x240 in RGB565, due to difficulty moving pixel data from the RP2040 PIO into the frame-buffer while remaining syncronised with commands sent over the same interface

It is intended to run a modified version of [retro-go](https://github.com/ducalex/retro-go), however firmware is not yet provided as it is currently a mess of rushed tweaks in an attempt to get a functional device.

As a result of these limitations I do not see it being worthwhile to improve the firmware for this version of RetroMedleyCard, as future iterations should aim to adress the lack of available memory, for which a more complete firmware can be written.
