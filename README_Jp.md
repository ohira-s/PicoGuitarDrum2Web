[README in English](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/README.md)  
# Pico Guitar & Drum
Pico Guitar and Drumはギターとドラム演奏用のUIを持つUSB MIDIデバイスです。ラズベリーパイPICO2Wで制御しています。  
本機はUSB MIDデバイスモードで動作していて音源は内蔵していないので、別途USB MIDIホストとなるパソコンや音源モジュールが必要です。  
  
本機は8個の押しボタンスイッチと8個の感圧パッドを備えています。  
6個のスイッチにはギターのコードを設定することができ、スイッチを押して演奏するコードを選択します。その後、感圧パッドを押すことでそのコードを演奏することができます。8個の感圧パッドの中の6個はギターの6弦に相当し、弦単位での演奏ができます。残りの2個はストローク奏法用と、ピッチベンド用のパッドです。  
Pico Guitar & Drumは演奏されたデータをMIDI NOTE-ONメッセージとしてUSB経由で音源モジュールに送信します。
  
ギターの6弦に相当する感圧パッドにはドラム楽器を割り当てることもできます。この場合はギターの単弦での演奏はできませんが、ストローク奏法と同時にドラムを演奏できるようになります。  
  
感圧パッドは押す力を検出し、強く押せば大きな音になったり、ピッチベンドの深さを変わったりします。
  
ギターコード譜を本機のデータフォーマットで作成すれば、スイッチを押す毎にコードが譜面順に切り替わります。スイッチを押して譜面のコード通りに切り替えながら感圧パッドで曲を演奏できます。  
  
Pico Guita & Drumはウェブサーバ機能も持っていて、ウェブブラウザから設定変更やギターコード譜データをアップロードすることもできます。  

Pico Guitar & Drum外観:  
![picogd_overview2](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_overview2.jpg)  

スイッチと感圧パッド:  
![picogd_overview2](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/picogd_labels.jpg)  

PICO2Wはcircuitpythonでプログラムしています。  

# User's Manual
[日本語版](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/UsersManual.md)  
[英語版](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/UsersManual_Eng.md)  

# Web Configulation User's Manual
[日本語版](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/WebConfigManual.md)  
[英語版](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/WebConfigManual_Eng.md)  

# Application Configuration Manual
[日本語版](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/ConfigManual.md)  
[英語版](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/ConfigManual_Eng.md)  

# Circuit Schematics
[回路図](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/PICO_Guitar_Circuit.pdf)

# Software Installation
1) circuitpython (v9.2.1)をPICO2Wにインストールします。  
2) 以下のファイル群をPICO2Wのルートにコピーします。  

- usb_midi_instrument.py  

	code.pyにリネームして下さい。  
	
- settings_TO_BE_EDITED.toml  

	setting.tomlにリネームし、ネット関連の環境変数の値を自身の環境に合わせて編集して下さい。  
	
- font5x8.bin.  
- lib folder.  
- SYNTH folder.  
