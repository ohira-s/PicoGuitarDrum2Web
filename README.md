[日本語版READMEへ / README in Japanese](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/README_Jp.md)  
# Pico Guitar & Drum
USB MIDI Guitar and Drum UI instrument with Raspberry Pi PICO2W.  This device works as a USB device.  USB MIDI Sound module is needed to use this.  
This device has 8 momentary press switches and 8 touch pressure sensor pads.  You can assign any guitar chord for each momentary press switch.  6 pads correspond to 6 guitar strings.  The rest two pads are a strumming pad and a pitch bend pad.  
Press a switch to select a chord, then touch the pads to play guitar.  Pico guitar sends MIDI NOTE-ON messages to a USB MIDI sound source module.  
You can assign drum instruments for 6 pads of guitar strings.  So you can play a guitar chord and drums at the same time.  
If you have guitar chord score files, you can play the music only to press "Next Chord" switch.  PICO2W also works as a web server, so you can upload and edit score files via web browser.  
Your pressing strength can be both velocity and after touch values.  The velocity controls note volume and the after touch do modulation depth.   

Pico Guitar & Drum Overview:  
![picogd_overview2](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_overview2.jpg)  

Functions of the switches and the pads:  
![picogd_overview2](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_labels.jpg)  

PICO2W is programmed with circuit python.  

# User's Manual
[User's Manual in Japanese is here.](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/UsersManual.md)  
[User's Manual in English is here.](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/UsersManual_Eng.md)  

# Web Configulation User's Manual
[Web Configulation User's Manual in Japanese is here.](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/WebConfigManual.md)  
[Web Configulation User's Manual in English is here.](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/WebConfigManual_Eng.md)  

# Application Configuration Manual
[Application Configuration Manual in Japanese is here.](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/ConfigManual.md)  
[Application Configuration Manual in English is here.](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/ConfigManual_Eng.md)  

# Circuit Schematics
[Circuit schematics is here.](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/PICO_Guitar_Circuit.pdf)

# Software Installation
1) Copy circuitpython (v9.2.1) into PICO2W.  
2) Copy all files below to PICO2W root.  

- usb_midi_instrument.py  

	Copy as code.py.  
- settings_TO_BE_EDITED.toml

	Copy as setting.toml and edit WiFi parameters in this file for your environment.  

- font5x8.bin.  
- lib folder.  
- SYNTH folder.  
