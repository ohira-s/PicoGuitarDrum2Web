# Pico Guitar & Drum User's Manual

![picogd_overview2](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_overview2.jpg)
## 1. 機能
　Pico Guitar & DeumはUSB MIDIデバイスとして動作するMIDIコントローラーです。  
　押しボタンスイッチにコードを割り当てておくことでスイッチを押してコードを選択し、ギターの弦に相当する感圧パッドを押すことでギターをコード演奏しているようにMIDIメッセージをUSB MIDI音源に送信できます。ピッチベンドをかけたり、アフタータッチでモジュレーションをかけて演奏に変化をつけることもできます。  
　パッドの一部をドラムに変更して、ギターコードとドラムでの演奏も可能です。  
　コード譜のファイルで登録することで、ワンボタンで譜面に合わせて次のコードへ切り替えながら、簡単に演奏を楽しむこともできます。

## 2. 外観
![picogd_labels](/Users/sohira/Documents/PICO2W/circuit/PicoGuitarDrums2W/Docs/picogd_labels.jpg)  
1) スイッチS1〜S8  

	8個の押しボタンスイッチ（S1〜S8）でコードを選んだり、各種設定を行います。  
2) 感圧パッドP1〜P6  

	ギターの1弦〜6弦を演奏します。
	ドラム演奏モードでは別途設定された6個のドラム系楽器を演奏します。  
3) 感圧パッドStrumming  

	ギターのコードをストローク奏法で演奏します。  
4) 感圧パッドPitch Bend  

	発音中のギターの全ての音をピッチベンドします。  
	ドラムには適用されません。

## 3. 注意事項
　Pico GuitarのほかにUSBホストデバイスになるUSB MIDI音源が必要です。本機への電源もUSBホスト側から供給される必要があります。MacOSとWindows11の音源への接続も可能です。

## 4. 接続〜起動
![picogd_splash](/Users/sohira/Documents/PICO2W/circuit/PicoGuitarDrums2W/Docs/picogd_splash.jpg)  
1) Pico Guitar & Drum（本機）を用意します。  
2) USBホストとなるUSB MIDI音源を用意します。  
3) Pico Guitar & DrumとMIDI音源を接続するUSBケーブルを用意します。Pico Guitar & Drum側はRapsberry Pi PICO2WのMicro USB-Bオスです。  
4) Pico GuitarのRapsberry Pi PICOのUSBコネクタとMIDI音源をUSBケーブルで接続します。  
5) MIDI音源の電源を入れます。MIDI音源からUSBケーブルで電源が供給されると、Pico Guitar & Drumが起動してOLED画面に「**PicoGuitar & Drum**」と表示されます。  
6) OLED画面が「**---GUITAR PLAY---**」という演奏用画面になると演奏できます。  
　この画像は、Unit-SYNTH/Unit-MIDIというGM音源シンセモジュールをPICO2で制御している自作のUSB MIDIホスト音源と接続したものです。  
![picogd_connection](/Users/sohira/Documents/PICO2W/circuit/PicoGuitarDrums2W/Docs/picogd_connection.jpg)

## 5. ギターコード演奏モード
　起動直後はコード演奏画面になっています。このモードではギターのコード演奏ができます。  

### 5-1. OLED画面
![picogd_chrod_settings](/Users/sohira/Documents/PICO2W/circuit/PicoGuitarDrums2W/Docs/picogd_guitar_play.jpg)
　コード演奏時の画面は以下のようになっています（上記サンプル画面の表示で説明します）  

・C m7-5  H +0  

	選択されているベース音(C)、コード(m7-5)、ロー／ハイコード(H=ハイコード)、カポタスト位置(+0=カポタストなし)が表示されています。  
・E4（縦書き表示）  
 　オンコード（分数コード）CmM7/Eの場合は、カポタスト位置表示の右側に縦書きで「E4」のように表示されます。 <br/>
・Aco GT (nylo
　演奏するGM音源の楽器名が表示されています。名称が画面に収まらない場合は後半がカットされます。
　後述の楽器選択で楽器が指定されていない場合は「---」が表示されます。<br/>
・Cm7-5 H/E, GM L, ..., Dm L
　画面左下の3行は6個のスイッチS1〜S6に割り当てられているコードが表示されています。Cm7-5 H/EはCm7-5のハイコードでEの分数コード、GM LはAメジャーのローコードを表しています。
　S7でコード設定のページを切り替えると、この表示も変化します。ただし表示が変化するだけで、演奏するコードはスイッチS1〜S6を押すまで変わりません。<br/>
・画面右上のノート表示
　縦書きで音程が表示されています。右の6列がギターの6弦に相当し、一番右が高音の1弦になっています。画面のコードは高音側の3弦をE6, B5, G5で発音することを表しています。
　4〜6弦はxxとなっていますが、これらの弦がミュート弦で音を発しないことを表しています。これらの感圧パッドを押しても音は出ません。
　一番左のE4はオンコード（分数コード）でベース音に変えて発音する音程を表しています。オンコードがない場合は--と表示されます。<br/>

### 5-2. コード選択
![picogd_labels_switches](/Users/sohira/Documents/PICO2W/circuit/PicoGuitarDrums2W/Docs/picogd_labels_switches.jpg)  
1) スイッチS1〜S6  

	演奏するコードを選びます。画面の
	各スイッチへのコードの割り当ては後述のコード設定モード画面で行います。    
2) スイッチS7  

	ギターの1弦〜6弦を演奏します。
	ドラム演奏モードでは別途設定された6個のドラム系楽器を演奏します。  
3) 感圧パッドStrumming  

	ギターのコードをストローク奏法で演奏します。  
4) 感圧パッドPitch Bend  

	発音中のギターの全ての音をピッチベンドします。  
	ドラムには適用されません。
　6個のスイッチS1〜S6でコードを選択します。各スイッチのコードはコード設定モードで割り当てることができます（後述）<br/>
　コード選択のスイッチは6個ですが、各スイッチに2つのコードを割り当てることができます。Chord Pageスイッチ（S7）を押すと、S1〜S6のスイッチに割り当てられている2つのコードを入れ替えできます。6個のスイッチの1ページ目と2ページ目を切り替えるイメージです。<br/>
 
### 5-3. 8 Pads
![picogd_labels_pads](https://hackmd.io/_uploads/HJfH4TVA1g.jpg)
 　コードを選択したら、8個の感圧パッドを指で押して演奏します。Guitar String1〜6はギターの6弦に対応します。String1が高音側です。Strummingはストーク奏法でコードを鳴らすパッドです。Pitch Bendは鳴っている音にピッチベンドをかけます。<br/>
　感圧パッドは押される圧力を検知します。強く押すと音が大きくなったり、ピッチベンドが強くかかったりします。また、長く押しているとビブラートがかかります。<br/>

### 5-4. モード変更
　スイッチS8を押すとコード設定モードに移行します。<br/>

## 6. コード設定モード
　コード設定モードでは、コード演奏モードのChord Selectorsの6個のスイッチにコードを割り当てることができます。<br/>
![picoguitar_guitar_settings.png](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/picoguitar_guitar_settings.png)

### 6-1. Switch Selector
　コードを割り当てるスイッチの番号を選択します。押すたびに番号が1〜12に変化し、12で押すと1に戻ります。<br/>
　1,2,3,4,5,6はスイッチの緑、黄、橙、赤、茶、灰に対応します。コード演奏モードのChord Pageで切り替えられる1ページ目に相当します。7〜12の6個はその2ページ目に相当します。演奏中によく使うコードを1ページ目、稀に登場するコードは2ページ目に割り当てると良いかもしれません。<br/>

### 6-2. Root Selector
　コードのベース音を選択します。スイッチを押すたびにC, C#, D, D#, E, F,...のように切り替わり、最後のBで押すとCに戻ります。<br/>

### 6-3. Chord Selector
　Root Selectorで選んだベース音にコードを設定します。スイッチを押すたびにM(major), M7, 7, 6, aug, m, mM7, ...のように切り替わります。最後のdim7で押すとMに戻ります。<br/>

### 6-4. Low/High Selector
　ローコード、ハイコードの切り替えをします。スイッチを押すたびにLow, Highが切り替わります。<br/>

### 6-5. On-chord Selector
　ベース音の代わりとする音程を指定します。押すたびにC,C##,...と変化し、Bの次は空欄となってオンコードとしないことになります。<br/>

### 6-6. Octave Selector
　1〜9の範囲でオクターブを切り替えられます。初期値は4です。9で押すと1に戻ります。<br/>

### 6-7. Chord Set File Selector
　曲調などに合ったコード進行を構成するコード群をあらかじめ定義した設定ファイルがあると、そのファイルを指定してChord Selectorsスイッチに一括してコードを割り当てることができます（設定ファイルの個数制限はありません。PICOのメモリが許す範囲で保存できます）<br/>
　スイッチを押すたびに設定ファイルが切り替わり、切り替わった時点でChord Selectorsのスイッチへのコード割り当ても変更されます。<br/>
 
### 6-8. 8 Pads
 　設定中のコードは8個のパッドを指で押して演奏できます。<br/>

### 6-9. Display
　コード設定時の画面は以下のようになっています。<br/>
![chord_settings.jpg](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/chord_settings.jpg)
<br/>
・SWTCH:<br/>
　Chord Switch Selectorで選択されたChord Selectorsスイッチの番号が表示されています。このスイッチにコードを設定することになります。<br/><br/>
・CHORD:<br/>
　Root Selector、Chord Selector、Low/High Selector、On-chord Selectorで指定されたコード名が表示されています。<br/><br/>
・OCTAV:<br/>
　設定されているオクターブが表示されます。通常は4です。<br/><br/>
・CD FL:<br/>
　選択されたコード設定ファイルのタイトルが表示されています。<br/><br/>

### 6-10. Mode Change
　このスイッチを押すとコンフィグレーションモードに移行します。<br/>

## 7. コンフィグレーションモード1
　コンフィグレーションモード1では、演奏の全体的な設定ができます。<br/>
![picoguitar_guitar_config1.png](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/picoguitar_guitar_config1.png)
<br/>
### 7-1. Velocity Offset
　8個のパッドは圧力を検知して、MIDI NOTE-ONのベロシティを変更して演奏する音の大きさを変えています。このスイッチを押すとベロシティの下限を変更できます。ベロシティの範囲が大きくて弱い音の音量が小さすぎるといった場合は、この値を大きくすることで解消できます。<br/>
　ただし、この値が大きくなるほどベロシティの変化範囲が狭くなるので、音の強弱の変化が少なくなります。<br/>

### 7-2. Velocity Curve
　パッドを押す圧力をベロシティに変換するときの変化の特性を変更できます。スイッチを押すたびに1.5〜4.0の範囲で0.1単位で値が変化します。値が大きいほど強弱の変化量がダイナミックになります。小さいと全体的にフラットになって強弱があまりつかなくなります。<br/>

### 7-3. Pitch Bend Range
　ピッチベンドで変化する音程の範囲を設定できます。スイッチを押すたびに0〜+12の範囲で変化します。1が半音に相当するので、最大1オクターブの範囲で設定できます。<br/>
　0を選ぶとピッチベンドのパッドを押しても音程は変化しなくなります。<br/>

### 7-4. Modulation Level01
　アフタータッチでかかるエフェクトのモジュレーションのレベル（LSB側）を設定します。<br/>

### 7-5. Modulation Level02
　アフタータッチでかかるエフェクトのモジュレーションのレベル（MSB側）を設定します。<br/>

### 7-6. After Touch On
　Padを押したままにしたときに機能するアフターエフェクトがかかるまでの秒数を指定します。<br/>
　なお、Padがドラムの場合にはアフターエフェクトは機能しません。<br/>

### 7-7. 8 Pads
 　設定中のコードは8個のパッドを指で押して演奏できます。<br/>

### 7-8. Display
　コンフィグレーション時の画面は以下のようになっています。<br/>
![config1.jpg](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/config1.jpg)
<br/>
・VELOC OFFSET:<br/>
　指定されたベロシティの下限値が表示されています。<br/><br/>
・VELOC CURVE:<br/>
　指定されたベロシティカーブの値が表示されています。<br/><br/>
・P-BEND RANGE:<br/>
　指定されたピッチベンドレンジの値が表示されています。<br/><br/>
・MODULA LVL01:<br/>
　指定されたモジュレーションのレベル01(LSB)が表示されています。<br/><br/>
・MODULA LVL02:<br/>
　指定されたモジュレーションのレベル02(MSB)が表示されています。<br/><br/>
・AFT-TOUCH ON:<br/>
　モジュレーションがかかるまでのアフタータッチの秒数が表示されています。<br/><br/>

### 7-9. Mode Change
　このスイッチを押すとコンフィグレーションモード2に移行します。<br/>

## 8. コンフィグレーションモード2
　コンフィグレーションモード2では、演奏の全体的な設定ができます。<br/>
![picoguitar_guitar_config2.png](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/picoguitar_guitar_config2.png)
<br/>
### 8-1. MIDI Channel
　ギター演奏データを送信するMIDI OUTチャンネルを指定します。<br/>
　ただし、ドラム演奏は強制的に10チャンネルに送信されます。<br/>

### 8-2. Capotasto
　カポタストを付けるフレットの位置を設定できます。-12〜+12の範囲で変更できます。0でカポタストなしです。実際のギターでマイナスのカポタストは付けられませんが、Pico Guitarでは可能としました。<br/>
　コード設定のOctave Selectorではオクターブ単位での音程を設定できましたが、カポタストではさらに半音単位で音程を変更できます。<br/>

### 8-3. Instrument Selector
　MIDI GM音源内の楽器を変更できます。スイッチを押すたびに切り替わります。各種ギターとシタールなどの弦楽器系から選択できます。<br/>
　選択した時点でMIDIのプログラムチェンジが送信され、音源のプログラムが切り替わります（その後、音源側でプログラムを変更した場合は、その音で演奏されます）

### 8-4. Play Drum
　Pad1〜6をドラム演奏用にするか、しないかの設定ができます。ONでドラム、OFFでギターの弦になります。<br/>

### 8-5. Drum Set Selector
　ファイルに保存されているドラムセット（Pad1〜6に割り当てるドラム系音色群）を変更できます。現時点でドラムセットの定義はファイルでしかできません。<br/>
　ドラムの演奏はMIDIチャンネル10で送信されます。<br/>

### 8-6. Drum Pad Selector
　ドラムの種類を変更したいPad1〜6を選択します。<br/>

### 8-7. Drum Selector
　ドラムの種類を変更します。<br/>

### 8-8. 8 Pads
 　設定中のコードは8個のパッドを指で押して演奏できます。<br/>

### 8-9. Display
　コンフィグレーション時の画面は以下のようになっています。<br/>
![config2.jpg](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/config2.jpg)
<br/>
・MIDI CHANNEL:<br/>
　指定されたMIDI OUT CHANNELが表示されています。<br/><br/>
・CAPOTASTO FRET:<br/>
　指定されたカポタストのフレット位置が表示されています。<br/>
・INST:<br/>
　選択されたGM音源楽器名が表示されています。<br/>
・PLAY DRUM:<br/>
　ドラム演奏機能のON/OFFが表示されています。ONのとき、ギターの6弦に相当するPad1〜6がドラム用に変化します。ストローク演奏とピッチベンドはそのままです。<br/>
・DRUM:<br/>
　指定されたドラムセット名が表示されています。<br/>
・DR2=5:<br/>
　指定されたドラムパッドのドラム名が表示されています。<br/>DR2の2はパッド番号、=の後ろの番号はドラムの種類番号（Pico Guitarの内部番号）です。その右側にドラムのGM音源名が表示されています。<br/><br/>

### 8-10. Mode Change
　このスイッチを押すとコード譜演奏モードに移行します。<br/>

## 9. コード譜演奏モード
　コード譜演奏モードでは、あらかじめ保存されているコード譜を使ってスイッチを押すだけでコードが切り替わって曲を演奏できます。コード譜は複数保存可能です（個数制限はありません。PICOのメモリが許す範囲で保存できます）<br/>
![picoguitar_play_music.png](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/picoguitar_play_music.png)

### 9-1. Previous File
　1つ前のコード譜ファイルを選択します。演奏対象のコードはコード譜の先頭になります。<br/>

### 9-2. Next File
　1つ後ろのコード譜ファイルを選択します。演奏対象のコードはコード譜の先頭になります。<br/>

### 9-3. Previous Chord
　演奏しているコードの1つ前のコードに戻します。譜面の先頭で押すと最後のコードに移動します。<br/>

### 9-4. Next Chord
　演奏しているコードの次のコードに移動ます。通常は曲に合わせてこのスイッチを押し、次のコードへ切り替えながらパッドでコードを演奏します。<br/>
　コード設定では12個のコードまで設定できましたが、コード譜ではその制限もなく、譜面通りに必要なコードを設定して演奏できます。<br/>
　最後のコードのところでNext Chordを押すと曲の終わりを表すEndという表示になります。ここでNext Chordを押すと先頭に戻ります。<br/>

### 9-4. Head of Music
　譜面の先頭のコードに戻します。<br/>

### 9-5. End of Music
　譜面の最後のコードに移動します。<br/>
 
### 9-6. 8 Pads
 　コード譜面で選択されているコードは8個のパッドを指で押して演奏できます。Next Chordでコードを切り替えながら簡単に演奏を楽しめます。<br/>

### 9-7. Display
　コード譜演奏時の画面は以下のようになっています。<br/>
![music_player.jpg](https://github.com/ohira-s/PICO_USB_MIDI_INSTRUMENT/blob/master/Docs/music_player.jpg)
<br/>
・MUSIC:<br/>
　選択されているコード譜のタイトルが表示されています。<br/><br/>
・PLAY:<br/>
　演奏対象のコード位置と全コード数がスラッシュで区切られて表示されています。最後のコードを演奏し終わるとENDと表示されます。<br/><br/>
・CHORD:<br/>
　演奏対象のコードが表示されています。パッドを押すとこのコードで演奏できます。<br/>
　歌詞と演奏タイミングデータが定義されている場合、その情報がコード名の下に2行で表示されます。<br/>

### 9-8. Mode Change
　このスイッチを押すとコード演奏モードに移行します。<br/>
