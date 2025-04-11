# Pico Guitar & Drum Configuration Manual

## 1. GM Sound Instrument Names List 
### 1-1. File
- SYNTH/MIDIFILE/GM0.TXT  

	Instruments' names in the GM Sound are defined in this file.  The default list is defined.  

### 1-2. Format
This file contains 128 instruments' names.  Only one instrument should be in a line.  ASCII code only.  

```
Acostic Grand Piano  
Bright Acostic Piano  
Electric Grand Piano  
    :  
Gun Shot  
```

## 2. Pico Guitar & Drum Instruments' list
### 2-1. File
- SYNTH/MIDIFILE/instruments.json  

	This JSON file contains instruments' list which can be used in Pico Guitar & Drum.  The default file contains guitar-like instruments.<br/>

### 2-2. Format
A JSON array beginning -1.  After that, list all instruments' GM program numbers.  

```
[-1, 24, 25, 26, 27, 28, 29, 30, 31, 104, 105, 106, 107]  
```

## 3. Drum Instruments' List
### 3-1. File
- SYNTH/MIDIFILE/drums.json  

	A JSON array listed drum instruments used in Pico Guitar & Drum.  

### 3-2. Format
The channel 10 is for playing drums in GM sound.  Each note number is bound to a drum instrument.  Each dictionary data in the JSON array corrensponds to an instrument.  The dictional has "NOTE" (note number) and "NAME" (instrument name).  

```
[  
  {"NOTE": 35, "NAME": "Acoustic Bass Drum"},  
  {"NOTE": 36, "NAME": "Bass Drum 1"},  
         :  
  {"NOTE": 81, "NAME": "Open Triangle"}  
]  
```

## 4. Chord Definitions
### 4-1. File
- SYNTH/MIDIFILE/chords.json  

	A JSON dictionary data contains guitar chord definitions.  

### 4-2. Format
The dictionary has data as below.  

```
{  
  "CHORDS": [Chord signature definitions],  
  "STRING_NOTES": [Note definitions for open-strings],  
  "CHORD_DEFINITIONS": [Fingar position definitions for guitar chords]  
}  
```

#### 4-2-1. Chord Signature Definitions
```
"CHORDS": ["M", "M7", "7", ..., "dim7"]  
```
	List signatures for chords, like m, m7, sus4, and so on.  

#### 4-2-2. Note definitions for open-strings
```
"STRING_NOTES": [16,11, 7, 2, -3, -8]  
```
Define 6 open-string notes on guitar.  The note is a number.  C4 is 0, B3 is -1, C4# is 1, and so on.  So the open-string note for the 1st string is 16(E5), and for the 6th string is -8(E3).  

#### 4-2-3. Fingar Position Definitions for guitar chords
```
"CHORD_DEFINITIONS": {  
  "CM": [[ 0, 1, 0, 2, 3,-1], [ 3, 5, 5, 5, 3,-1]],  
    :                       :  
  "Bdim7"  : [[-1, 3, 1, 3, 2,-1], [-1, 6, 7, 6,-1, 7]]  
}  
```
Define fingar position for each chord.  A chord has two sets of the fingar position, low-chord and high-chord.  Chord names are "CM" (C majar), "C#m7" (C# minor7), and so on.  

```
"CM": [[Low chord definition], [High chord definition]]

```
The low-chord and the high chord have a same data structure' array.  The 1st element in the array is a fret number to be pressed for the 1st string.  The last element is for the 6th string.  

```
 -1: Mute string (not play this string).  
  0: Open string (not press any fret).  
>=1: Fret number to press.  
```

Low chord for C major (CM) is [0,1,0,2,3,-1].  The 1st string is an open-string.  The 2nd string must be pressed at the 1st fret.  The 6th string is a mute string.  

## 5. Initial Chord Selectors Definition
### 5-1. File
- SYNTH/MIDIFILE/switch.json  

	Define initial chords for the Chord Selector Switches.
 
### 5-2. Format
Pico Guitar & Drum has 6 physical Chord Selector switches.  However press the Chord Page switch, another chord set appears.  So there are 12 chords definitions.  Each definition has flowing dictionary data.  

```
"ROOT": A base note number, C is 0, C# is 1, ..., B is 11.  
"CHORD": An array index is the Signature Definitions. 0 is for "M".  
"POSITION": 0 is for Low Chord, 1 is for High Chord.  
"ON_NOTE": A base note number for ON-NOTE chord. -1 means a NOT ON-NOTE chord.  
"SCALE": An ontave number from 1 to 9, normally 4.  
```

## 6. Chord Set Definition
### 6-1. File
- SYNTH/CHORD/CHORD_SET_NAME.json  
- SYNTH/CHORD/list.json  

You can make chord set files for your favorite chord set, like for Rock, for Pops, for Jazz.  You can load the chord set in the configuration mode.  CHORD_SET_NAME is file name as you like.  
List file list.json contains a file list of the chord set files.  
 
### 6-2. Format
#### 6-2-1. Chord Set File
A dictionary data as below.  
```
"NAME": "Chord set name",  
"CHRODS": [12 Chord definitions for the Chord Selectors]  
```
"Chord set name" is just a text data in ASCII code.  
Flowing 12 arrays in the "CHORDS" array.  

```
["Base note", "Chord signature", "Position", "ON-NOTE base note", Octave]  

```

```
"Base note": A base note name like "C", "C#" or "B".  
"Chord signature": A chord signature like "M", "m", "7" or "sus4".  
"Position": "LOW" means a low chord and "HIGH" means a high chord.  
"ON_NOTE": A base note name for ON-NOTE like "C", "C#" or "B".  
Octave: Octave value from 1 to 9.  Normally 4.  
```

#### 6-2-2. List File
list.json contains all chord set file names.  Pico Guitar & Drum can not find out any chord set file not included in this file.  

```
  [  
    ["Canon.json", ""],  
    ["Simple.json", ""],  
    ["Sweet.json", ""],  
    ["Blues.json", ""]  
  ]  
```
The 2nd element in each array must be "".  This is an internal data on Pico Guitar & Drum.  

## 7. Drum Instrument Set Definition
### 7-1. File
- SYNTH/DRUM/DRUM_SET_NAME.json  
- SYNTH/DRUM/list.json  

You can make drum instrument set files for your favorite music, like for Rock, for Pops, for Jazz.  You can load the chord set in the configuration mode.  DRUM_SET_NAME is file name as you like.  
List file list.json contains a file list of the drum instrument set files.  
 
### 7-2. Format
#### 7-2-1. Drum Instrument Set File
A dictionary data as below.  

```
"NAME": "Drum instrument set name",  
"SET": [6 drum instruments]  
```

"Drum instrument set name" is just a text data in ASCII code.  
[6 drum instruments] array defines 6 drum instrument for 6 pads.  The instruments are defined as index for Drum Instruments' List (NOT MIDI note number).  -1 means no instrument is assigned for.  

```
{"NAME": "Drum Set1", "SET": [1, 6, 3, 10, 11, 16]}  
```

#### 7-2-2. List File
list.json contains all drum instrument set file names.  Pico Guitar & Drum can not find out any drum instrument set file not included in this file.  
```
[  
  ["Drum1.json", ""],  
  ["Drum2.json", ""],  
  ["Drum3.json", ""],  
  ["Drum4.json", ""]  
]  
```
The 2nd element in each array must be "".  This is an internal data on Pico Guitar & Drum.  

## 8. MUSIC File
### 8-1. File
- SYNTH/MUSIC/MUSIC_NAME.json  
- SYNTH/MUSIC/list.json  

You can make music files of your favorite musics.  You can load the files in the music play mode.  MUSIC_NAME is file name as you like.  
List file list.json contains a file list of the music files.  
 
### 8-2. Format
#### 8-2-1. MUSIC File
A dictionary data as below.  

```
"NAME": "Music title",  
"MUSIC": [Chord progression]  
```

"Music title" is just a text data in ASCII code.  
[Chord progression] array defines a series of chords in the music.  

```
["Base note", "Chord signature", "Position", "ON-NOTE base note", Octave]  
```


```
"Base note": A base note name like "C", "C#" or "B".  
"Chord signature": A chord signature like "M", "m", "7" or "sus4".  
"Position": "LOW" means a low chord and "HIGH" means a high chord.  
"ON_NOTE": A base note name for ON-NOTE like "C", "C#" or "B".  
Octave: Octave value from 1 to 9.  Normally 4.  
```

You can describe other two elements in the chord array.  The 1st element is for lyrics and the 2nd element is for timings for playing guitar.  

```
["Base note", "Chord signature", "Position", "ON-NOTE base note", Octave, "Lyrics", "Play timing"]  
```

Here is a sample data.  Lyrics in Japanese.  
```
{  
  "NAME": "Sotsugyo Shashin",  
  "MUSIC":[  
    ["C", "M",  "LOW", "",  4, "Kanashi Koto",  
                               "    *   *"],  
    ["C", "M",  "LOW", "D", 4, "ga Aru",  
                               "*  *"],  
    ["G", "M7",	"LOW", "",  4, "to Hira-",  
                               "***"],  
    ["E", "m7",	"LOW", "",  4, "-ku Kawa",  
                               " *  *"],  
                  :  
    ["A", "m7", "LOW", "",  4, "Tokude",  
                               "* *"],  
    ["D", "7",  "LOW", "",  4, "Shikatte",  
                               "*    *"],  
    ["G", "M7", "LOW", "",  4, "...",  
                               "**"],  
    ["G", "7",  "LOW", "B", 4, "...",  
                               "*"]  
}  
```

#### 8-2-2. List File
list.json contains all music file names.  Pico Guitar & Drum can not find out any music file not included in this file.

```
[  
    ["Yasashisa.json", ""],  
    ["Sotsugyo.json", ""],  
    ["Ellie.json", ""]  
]  
```
The 2nd element in each array must be "".  This is an internal data on Pico Guitar & Drum.  
　
## 9. PICO2W Environment Variables Definition File
### 9-1. File
・settings.toml  

	PICO2Wがcircuitpythonから参照する環境変数の設定ファイルです。 
	Environment variables definition file for PICO2W with circuitpython. 

### 9-2. Format
#### 9-2-1. Environment Variables Definition File
A text file which contains environment variables as below.  

```
CIRCUITPY_WIFI_SSID = "Your WiFi SSID"
CIRCUITPY_WIFI_PASSWORD = "Your WiFi Password"
PICO_IP_ADDRESS = "192.168.179.90"
PICO_NET_MASK = "255.255.255.0"
PICO_GATEWAY = "192.168.179.1"
PICO_WEB_PORT = "8080"
```

1) CIRCUITPY\_WIFI\_SSID  

	A SSID of WiFi access point which PICO2W connects to.  

2) CIRCUITPY\_WIFI\_PASSWORD  

	A password for the WiFi access point.   

3) PICO\_IP\_ADDRESS  

	A static IP address for PICO2W.
	It makes easy to connect the configuration web server on PICO2W.  

4) PICO\_NET\_MASK  

	A subnet mask for your local network.   

5) PICO\_GATEWAY  

	A default gateway for  your local network.  

6) PICO\_WEB\_PORT  

	A port number for the configuration web server on PICO2W.   

