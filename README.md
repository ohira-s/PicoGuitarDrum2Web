# Pico Guitar
USB MIDI Guitar UI instrument with Raspberry Pi PICO2W.  This device works as a USB device.  USB MIDI Sound module is needed to use this.<br/>
This device has 6 momentary press switchs and 8 touch sensor pads.  You can assign any guitar chord for each momentary press switch.  6 pads correspond to 6 guitar strings.  The rest two pads are a strumming pad and a pitch bend pad.<br/>
Press a switch to select a chord, then touch the pads to play guitar.  Pico guitar sends MIDI NOTE-ON messages to a USB MIDI sound source module.<br/>
You can assign drum instruments for 6 pads of guitar strings.  So you can play a guitar chord and drums at the same time.<br/>
If you have guitar chord score files, you can play the music only to press "Next Chord" switch.  PICO2W also works as a web server, so you can upload and edit score files via web browser.<br/>
![picoguitar_top_look.png](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/picoguitar_top_look.png)
- Photo<br/>
![pico_guitar.jpg](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/pico_guitar.jpg)

PICO2W is programmed with circuit python.

# User's Manual
[User's Manual in Japanese is here.](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/UsersManual.md)<br/>
[User's Manual in English is here.](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/UsersManual_Eng.md)

# Configuration Manual
[Application Configuration Manual in Japanese is here.](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/ConfigManual.md)<br/>
[Application Configuration Manual in English is here.](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/ConfigManual_Eng.md)<br/>

# Circuit Schematics
[Circuit schematics is here.](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/PICO_Guitar_Circuit.pdf)

# Software Installation
1) Copy circuitpython (v9.2.1) into PICO2W.
2) Copy all files below to PICO2W root.
- usb_midi_instrument.py as code.py.
- settings_TO_BE_EDITED.toml as setting.toml and edit WiFi parameters in this file for your environment.
- font5x8.bin.
- lib folder.
- SYNTH folder.
