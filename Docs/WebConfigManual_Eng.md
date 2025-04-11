# Pico Guitar & Drum Web Configuration Manual

## 1. Functions
Pico Guitar & Drum is a MIDI controller which works as a USB MIDI device mode.  This controller has configuration menus.  Moreover you can configure some parameters and files via configuration web server.  
The URL of the web server depends on the IP address of the controller.

	http://<IP ADDRESS>:8080  
	
Sometimes you might get unexpected web page according to lack of web server memory.  In this case, refresh your browser with the URL as above.  

## 2. Change Instrument
![picogd_labels](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/web_instrument.png)  
1) Instrument： Instrument select drop-down list.  

	Chose a instrument on the drop-down list.  
	
2) CHANGE： Instrument change button.  

	Click [CHANGE], then the instrument to play is changed.  
	Pico Guitar & Drum sends a program change MIDI message to the MIDI sound module you connected.  

## 3. Guitar Score Upload
![picogd_labels](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/web_music.png)  
1) Select File： Score files drop-down list.  

	The drop-down list has Guitar score file names in PICO2W.  
	Select a file name to edit, or "NEW" to make new score.  

2) DOWNLOAD： Score download button.  

	Download a file selected in the "Select File" drop-down list, then show you the contents in File Name and Score text boxes.  
	You will see a template data for "NEW" score.  

3) File Name： File name for the score.  

	A file name downloaded.
	You can change it to save as another file.  

4) Score： Score JSON data.  

	JSON format data for the score.  
	Edit this carefully not to destroy JSON format.  

	"NAME": "Music title"  
	"MUSIC": ["Chord root note", "Chord name", "LOW or HIGH", "Slash chord note", "Lyrics", "Markers to play"]  
	
-- ASCII charactors only.  
-- Use double-quote.  Never use single-quote.  
-- More information: [ConfigManual.md](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/ConfigManual.md)  

5) UPLOAD： Score file upload button.  

	Upload the score in "Score" text area to PICO2W.  
	JSON syntax will be checked, however not checked wheather it is suitable for a score data.  If you upload an illegular score data, Pico Guitar & Drum would not work properly.  

## 4. Guitar Score List Upload
![picogd_splash](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/web_music_list.png)  
1) Score List： Score list data.    

	JSON format data for the score.  
	Edit this carefully not to destroy JSON format.  
	
	["Score file name", ""]
	
-- ASCII charactors only.  
-- Use double-quote.  Never use single-quote.  
-- More information: [ConfigManual.md](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/ConfigManual.md)  

2) UPLOAD： Scores list file upload button.  

	Upload the score in "Score List" text area to PICO2W.  
	JSON syntax will be checked, however not checked wheather it is suitable for a score list data.  If you upload an illegular score data, Pico Guitar & Drum would not work properly.  

## 5. Drum Set Upload
![picogd_splash](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/web_drumset.png)  
1) Select File：ドラムセット選択  

	The drop-down list has drum set file names in PICO2W.  
	Select a file name to edit, or "NEW" to make new score.  

2) DOWNLOAD：Drum set data download button.  

	Download a file selected in the "Select File" drop-down list, then show you the contents in File Name, Set Name and 6 instruments.  
	You will see a template data for "NEW" drum set.  

3) File Name： File name for the drum set.  

	A file name downloaded.
	You can change it to save as another file.  

4) Set Name： Drum set name.  

	A drum set name downloaded.  
	You can change it to save as another name.  

5 Inst.1〜Inst.6： Drum instrument select drop-down list.  

	You will see drum instrument names for the 6 pads (P1-P6)   

6) UPLOAD：Drum set file upload button.  

	Upload the drum set you arranged to PICO2W.  

## 6. Drum Set List Upload
![picogd_splash](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/web_drumset_list.png)  
1) Drum Set List： Drum sets list data.  

	JSON format data for the drum sets list.  
	Edit this carefully not to destroy JSON format.  
	
	["Drum set file name", ""]
	
-- ASCII charactors only.  
-- Use double-quote.  Never use single-quote.  
-- More information: [ConfigManual.md](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/ConfigManual.md)  

2) UPLOAD： Drum sets list file upload button.  

	Upload the score in "Drum Set List" text area to PICO2W.  
	JSON syntax will be checked, however not checked wheather it is suitable for a score list data.  If you upload an illegular score data, Pico Guitar & Drum would not work properly.  
