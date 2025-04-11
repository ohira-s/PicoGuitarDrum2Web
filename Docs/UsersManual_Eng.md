# Pico Guitar & Drum User's Manual

![picogd_overview2](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_overview2.jpg)

## 1. Introduction
Pico Guitar & Drum is a MIDI controller which works as a USB MIDI device.  
This device has 6 momentary press switchs and 8 touch pressure sensor pads.  You can assign any guitar chord for each momentary press switch.  6 pads correspond to 6 guitar strings.  The rest two pads are a strumming pad and a pitch bend pad.  
Press a switch to select a chord, then touch the pads to play guitar.  Pico Guitar & Drum sends MIDI NOTE-ON messages with velocity value to a USB MIDI sound source module.  
You can assign drum instruments for 6 pads of guitar strings.  So you can play a guitar chord and drums at the same time.  
If you have guitar chord score files, you can play the music only to press "Next Chord" switch.  

## 2. Appearance
![picogd_labels](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_labels_pads.jpg)  

1) Switches S1-S8  

	8 momentary press switches (S1 to S8) to select a chord playing and to set up parameters.  
	
2) Touch pressure sensor pads P1-P6  

	8 touch sensor pads to play MIDI instrument like guitar.  The pads can get pressure information to control velocity and pitch bend depth.  
	Press strength controls its velocity.  

3) Touch pressure sensor pad for the strumming  

	Play a guitar chord with strumming.  
	Press strength controls its velocity.  

4) Touch pressure sensor pad for the pitch bend  

	Apply pitch bend to all notes playing.  
	Press strength controls its depth.  
	
5) OLED display  

	Show you informations.  
	
6) USB cable    

	Connect to a USB MIDI host device.  

## 3. Notes
A USB MIDI sound source module is needed.  This module must work as a USB HOST and supply power (+5V) to Pico Guitar & Drum via the USB cable.  

## 4. Turn Pico Guitar & Drum on
![picogd_splash](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_splash.jpg)  

1) Prepare a Pico Guitar & Drum.  
2) Prepare a USB MIDI sound source module working as a USB HOST.  
3) Prepare a USB cable.  Micro USB-B for Pico Guitar & Drum side.  
4) Connect Pico Guitar & Drum to the USB MIDI sound souce module with the USB cable.  
5) Turn on the MIDI sound source module.  Then Pico Guitar & Drum turns on by power supply from the sound module.  You will see a splash screen on the OLED display, then a title of "**---GUITAR PLAY---**".  
6) Now you can play Pico Guitar & Drum.  
  
A photo below is a USB MIDI synthesizer I made and a Pico Guitar & Drum.  These devices are connected each other with a USB cable.   
![picogd_connection](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_connections.jpg)
  
## 5. Chord Play Mode
You can play guitar chords in Chord Play Mode.  Just after turning on, Pico Guitar & Drum is under this mode.  

### 5-1. OLED Display
OLED display in this mode is as below.  
![picogd_chrod_settings](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_guitar_play.jpg)  

・Chord to play: C m7-5  H +0  

	This shows you the current chord to play.  "C" is base note, "m7-5" is a chord, "L" is low chord position and "+0" is fret number setting capotasto ("+0" means no capotasto).  
	If the current chord is A/C, high position chord and capotasto is on the 2nd fret, you will see "A M H/C +2".    

・Slash chord： E4（a vertical text）  

	"Cm7-5/E" is a slash chord.  E4 is shown next to the capotasto setting as a vertical text.  

	 　
・Instrument name： Aco GT (nylo  

	An instrument name in GM sounds or "---" if no instrument is selected.  
	　 
・Chord set： Cm7-5 H/E, GM L, ..., Dm L  

	The left-bottom area in the OLED shows you a chord set, which is 6 chords for switches S1-S6.  
	Cm7-5 H/E means Cm7-5, high position chord and slash chord of E.  GM L means G major and low position chord.  
	Press S7 to swap the chord set, the other chords are shown.  
	　
・Notes on the right-top area on OLED    

	You can see 6 note names as vertical texts.
	The most right side note is the 1st string of guitar.  In this case, 1st string note is E6, second is B5 and 3rd is G5.  
	4-6th strings are "xxx".  This means a mute string not to play. These strings do NOT sound if you would press these pads.  
	The most left side note is a slash chord note.  You will see "--" for chord without slash.   

### 5-2. Select a Chord: S1-S7
![picogd_labels_switches](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_labels_switches.jpg)  

1) Switches S1-S6  

	You can select a chord to play with the switches S1-S6.  

2) Switch S7  

	Each switch has two chords, chord-A (chord set 1) and chord-B (chord set 2).  You can swap chord-A or B with the switch S7.  
 
### 5-3. Play a Chord
![picogd_labels_pads](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_labels_pads.jpg)  

1) Touch Pressure Sensors P1-P6  

	After selecting a chord, you can play the chord with 6 pads.  The pad 1 to 6 correspond to 6 string on guitar.  The pad 1 is the highest tone string, and the pad 6 is the lowest tone's.  
	
2) Strumming Pad  

	The strumming pad is for strumming the chord.  
	
3) Pitch Bend Pad  

	The pitch Bend pad is for pitch bend effect.  
	
- All pads detect pressure value.  Pressing stronger, getting loud sound or deep pitch bend effect.  

### 5-4. Mode Change: S8
Press switch S8, switch to Chord Stting Mode.  

## 6. Chord Setting Mode
In this mode, you can assign any chord for each Chord Selector switch S1-S6.  

### 6-1. OLED Display
OLED display in this mode is as below.  
![picoguitar_guitar_settings.jpg](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_chord_settings.jpg)  
  
1) SWITCH: 1  

	A Chord Selector switch number to assign it's chord.    

2) CHORD: C mM7 L/C  

	A chord name to be assigned.  
	The chord is arranged with Root Selector、Chord Selector、Low/High Selector、Slash Chord Selector.  

3) OCTAV: 4  

	An octave value to be assigned.    

4) CD FL: Sweet Princess  

	A Chord Setting name.    

### 6-2. Chord Switch Selector: S1
You can select a chord select switch number to edit its chord.  There are 12 numbers, from 1 to 12.  
Switch number 1 to 6 are for the chord set 1, 7 to 12 are for the chord set 2.  You can swap these chord sets with pressing switch S7 in the Chord Play Mode.  

### 6-3. Root Selector: S2
Select a base note from C, C#, D, ..., A#, B.  Next to B is C.  

### 6-4. Chord Selector: S3
Select a chord type from M(major), M7, 7, 6, ..., dim7.  Next to dim7 is M.  

### 6-5. Low/High Selector: S4
Select a chord position in Low or High.  

### 6-6. Slash Chord Selector: S5
If you make a on-chord, you need to select a on-chord note here.  Blank means that this chord does NOT have any on-chord note.　Select a note for on-chord note from C, C#, D, ..., A#, B.  Next to B is blank.  

### 6-7. Octave Selector: S6
Select a octave from 1 to 9.  Default is 4, chord C makes C4.  Next to 9 is 1.  

### 6-8. Chord Set File Selector: S7
You can assign twelve chords for the Chord Selectors switches by selecting a Chords Setting File.  
You can save many kinds of the files in Rapsberry Pi PICO memory.  Press the switch, you will see a next chords set name.  
 
### 6-9. Play a Chord
![picogd_labels_pads](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_labels_pads.jpg)  

1) Touch Pressure Sensors P1-P6  

	After selecting a chord, you can play the chord with 6 pads.  The pad 1 to 6 correspond to 6 string on guitar.  The pad 1 is the highest tone string, and the pad 6 is the lowest tone's.  
	
2) Strumming Pad  

	The strumming pad is for strumming the chord.  
	
3) Pitch Bend Pad  

	The pitch Bend pad is for pitch bend effect.  
	
- All pads detect pressure value.  Pressing stronger, getting loud sound or deep pitch bend effect.  

### 6-10. Mode Change: S8
Press switch S8, switch to Configuration Mode1.  

## 7. Configuration Mode1
This mode is for setting up the general parameters.  

### 7-1. OLED Display
OLED display in this mode is as below.  
![picoguitar_guitar_config1.jpg](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_configuration1.jpg)  
  
1) VELOC OFFSET: 30  

	The current smallest velocity value.    

2) VELOC CURVE: 2.7  

	The current velocity curve parameter value.    

3) P-BEND RANGE: +2  

	The current pitch bend range value.    
	
4) MODULA LVL01: 80  

	The LSB value for modulation.  
	
5) MODULA LVL02: 20  

	The MSB value for modulation.  
	
6) AFT-TOUCH ON: 1.0  

	The long-press time in second to get the modulation effect.

### 7-2. Velocity Offset: S1
You can select a smallest value of NOTE-ON velocity.  
8 Pads can detect pressure strength.  Pico Guitar & Drum makes NOTE-ON velocity value by the value.  If you think the smallest velocity is too small (can't hear instrument sound), you can change the smallest velocity value.  

### 7-3. Velocity Curve: S2
The pressure strength values detected by the pad are not linear line but log-curve.  You can change the curve shape by Velocity Curve value.  
The value range is from 1.5 to 4.0.  Larger value gets bigger curve.  

### 7-4. Pitch Bend Range: S3
You can select a pitch bend range value from 0 to +12. 1 correspond to half tone.  
Select 0, the pitch bend does NOT work.  

### 7-5. Modulation Level01: S4
You can change the value of modulation level01(LSB).  The modulation effect is applied after long-press of the pad P1-P6 and the strummng pad.

### 7-6. Modulation Level02: S5
You can change the value of modulation level02(MSB).  The modulation effect is applied after long-press of the pad P1-P6 and the strummng pad.

### 7-7. After Touch On: S6
You can change the long-press time in second to get the modulation effect for the pad P1-P6 and the strumming pad.
The after touch does not work on the drum pads.  

### 7-8. Play a Chord
![picogd_labels_pads](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_labels_pads.jpg)  

1) Touch Pressure Sensors P1-P6  

	After selecting a chord, you can play the chord with 6 pads.  The pad 1 to 6 correspond to 6 string on guitar.  The pad 1 is the highest tone string, and the pad 6 is the lowest tone's.  
	
2) Strumming Pad  

	The strumming pad is for strumming the chord.  
	
3) Pitch Bend Pad  

	The pitch Bend pad is for pitch bend effect.  
	
- All pads detect pressure value.  Pressing stronger, getting loud sound or deep pitch bend effect.  

### 7-9. Mode Change: S8
Press switch S8, switch to Configuration Mode2.  

## 8. Configuration Mode2
This mode is for setting up the general parameters.  

### 8-1. Display
OLED display in this mode is as below.  
![picogd_configuration2.jpg](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_configuration2.jpg) 
  
1) MIDI CHANNEL: 1  

	MIDI OUT channel selected.    

2) CAPOTASTO FRET: +0  

	Capotasto fret number selected.  
	
3) INST: Aco GT(nylon)  

	A GM instrument name selected.  
	
4) PLAY DRUM: OFF  

	Assign Pad1-6 for drums(ON) or guitar(OFF).  
	
5) DRUM: Drum Set3  

	A Drum set name selected.    
	
6) DR2=14: Crash Cymbal 1  

	"DRn" means a drum pad number "n" selected.  
	"=x" means a drum instrument ID "x", this ID is an internal code of Pico Guitar & Drum.  
	You can see the drum instrument name selected on the right side.    

### 8-2. MIDI Channel: S1
You can select a MIDI OUT channel to send MIDI messages playing guitar.  
Channel 10 is used for playing drums.  

### 8-3. Capotasto: S2
You can attach a capotasto at a fret.  The Capotasto value is the fret number to attach capotasto.  You can select not only positive value but also negative value.  0 means NO capotasto.  

### 8-4. Instrument Selector: S3
Select an instrument in GM sounds source.  You can see only stringed instruments.  
Select an instrument, Pico Guitar & Drum sends a MIDI program change message immediately.  

### 8-5. Play Drum: S4
You can change the pad P1-P6 for playing drums.  ON is for drums, OFF is for guitar strings.  
The strumming pad and the pitch bend pad is always for playing guitar.  

### 8-6. Drum Set Selector: S5
You can select a drum set from the drum setting files.  You need to edit these file with a text editor.  
MIDI OUT channel 10 is used to send MIDI messages for drums.  

### 8-7. Drum Pad Selector: S6
Select a pad number to change it's drum instrument.  

### 8-8. Drum Selector: S7
Select a drum instrument.  

### 8-9. Play a Chord
![picogd_labels_pads](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_labels_pads.jpg)  

1) Touch Pressure Sensors P1-P6  

	After selecting a chord, you can play the chord with 6 pads.  The pad 1 to 6 correspond to 6 string on guitar.  The pad 1 is the highest tone string, and the pad 6 is the lowest tone's.  
	
2) Strumming Pad  

	The strumming pad is for strumming the chord.  
	
3) Pitch Bend Pad  

	The pitch Bend pad is for pitch bend effect.  
	
- All pads detect pressure value.  Pressing stronger, getting loud sound or deep pitch bend effect.  

### 8-10. Mode Change: S8
Press switch S8, switch to Music Play Mode.  

## 9. Music Play Mode
In this mode, you can play a music by only pressing one switch and 8 Pads.  It's so easy!!  
Select a music file in pre-loaded music files, a series of chords for the music are loaded in Pico Guitar & Drum.  After that, press the NEXT switch and play with 8 Pads, then press the NEXT switch, and so on.  

### 9-1. OLED Display
OLED display in this mode is as below.  
![picoguitar_play_music.jpg](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_guitar_music.jpg)  
  
1) MUSIC: Sotsugyo Shashin  

	A music title selected.    

2) PLAY: 1/42  

	You can see the current chord position and the total number of chords separated by '/'.    

3) CHORD: CM  

	The current chord to play.  

4) 歌詞: Kanashi Koto  

	Lyrics are appeared if the data were defined.  
	
5) 演奏タイミング: *  *  

	Timing for playing are appeared if the data were defined.  

### 9-2. Previous File: S1
Select a previous music file.  

### 9-3. Next File: S2
Select a next music file.  

### 9-4. Previous Chord: S4
Select a previous chord in the loaded music.  

### 9-5. Next Chord: S7
Select a next chord in the loaded music.  

### 9-6. Head of Music: S5
Rewind to the head of the music.  

### 9-7. End of Music: S6
Move to the end of the music.  
 
### 9-8. Play a Chord
![picogd_labels_pads](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_labels_pads.jpg)  

1) Touch Pressure Sensors P1-P6  

	After selecting a chord, you can play the chord with 6 pads.  The pad 1 to 6 correspond to 6 string on guitar.  The pad 1 is the highest tone string, and the pad 6 is the lowest tone's.  
	
2) Strumming Pad  

	The strumming pad is for strumming the chord.  
	
3) Pitch Bend Pad  

	The pitch Bend pad is for pitch bend effect.  
	
- All pads detect pressure value.  Pressing stronger, getting loud sound or deep pitch bend effect.  

### 9-9. Mode Change: S8
Press switch S8, switch to Chord Play Mode.  
