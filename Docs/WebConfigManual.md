# Pico Guitar & Drum Web Configuration Manual

## 1. 機能
　Pico Guitar & DrumはUSB MIDIデバイスとして動作するMIDIコントローラーです。各種設定は本体でもできますが、本体だけではできない設定をWeb画面で実施できます。  
　設定WebのURLはPico Guitar & Drum本体のIPアドレスに依存します。  

	http://<IPアドレス>:8080  
	
　PICO2Wのメモリ利用状況によっては画面が乱れることがあります。その場合は上記のURLで再表示してみて下さい。  

## 2. Change Instrument：楽器変更
![picogd_labels](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/web_instrument.png)  
1) Instrument：楽器選択ドロップダウン  

	ドロップダウンから変更した楽器名を選択します。  
	
2) CHANGE：楽器変更ボタン  

	[CHANGE]を押すとドロップダウンで選択されている楽器に変更されます。  
	Pico Guitar & DrumはプログラムチェンジのMIDIメッセージをMIDI音源に送信します。  

## 3. Guitar Score Upload：コード譜編集
![picogd_labels](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/web_music.png)  
1) Select File：コード譜選択  

	ドロップダウンからPICO2Wに保存されているコード譜を選択します。新規で作成したい場合は「NEW」を選択します。    

2) DOWNLOAD：コード譜ダウンロード  

	ドロップダウンで選択されたコード譜をPICO2WからダウンロードしてScore欄に表示します。  
	NEWの場合はテンプレートが表示されます。      

3) File Name：コード譜ファイル名  

	ダウンロードされたファイル名が表示されます。  
	名称を変更して別名で保存する場合はこの内容を修正します。      

4) Score：コード譜JSONデータ  

	ダウンロードされたコード譜が表示されます。JSON形式の内部データが表示されるので、JSONフォーマットを崩さないように編集して下さい。  
	"NAME": "曲名"  
	"MUSIC": ["ルート音", "コード名", "LOW or HIGH", "分数コードルート音", "歌詞", "演奏タイミング"]  
	
	※ASCII文字のみ記述できます。
	※ダブルクォートを使用して下さい（シングルクォートは不可）  
	※ファイルフォーマットの詳細は[ConfigManual.md](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/ConfigManual.md)を参照して下さい。  

5) UPLOAD：コード譜アップロード  

	Score欄にあるコード譜をPICO2Wにアップロードします。  
	JSON形式の正当性チェックは行なっていますが、JSON形式として問題なければ保存してしまいます。コード譜用のJSONの内容を保存して下さい。それ以外を保存した場合の動作の保証はありません。    

## 4. Guitar Score List Upload：コード譜リスト編集
![picogd_splash](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/web_music_list.png)  
1) Score List：コード譜リストデータ  

	PICO2W内部のコード譜リストが表示されます。JSON形式の内部データが表示されるので、JSONフォーマットを崩さないように編集して下さい。  
	コード譜演奏モードでのコード譜選択時にはこの順番でコード譜が表示されます。  
	
	["コード譜ファイル名", ""]
	
	※ASCII文字のみ記述できます。
	※ダブルクォートを使用して下さい（シングルクォートは不可）
	※ファイルフォーマットの詳細は[ConfigManual.md](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/ConfigManual.md)を参照して下さい。  

2) UPLOAD：コード譜リストアップロード  

	Score List欄にあるコード譜リストをPICO2Wにアップロードします。  
	JSON形式の正当性チェックは行なっていますが、JSON形式として問題なければ保存してしまいます。コード譜リスト用のJSONの内容を保存して下さい。それ以外を保存した場合の動作の保証はありません。    

## 5. Drum Set Upload：ドラムセット編集
![picogd_splash](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/web_drumset.png)  
1) Select File：ドラムセット選択  

	ドロップダウンからPICO2Wに保存されているドラムセットを選択します。新規で作成したい場合は「NEW」を選択します。    

2) DOWNLOAD：ドラムセットダウンロード  

	ドロップダウンで選択されたドラムセットをPICO2Wからダウンロードして以下の欄に表示します。  
	NEWの場合は初期設定が表示されます。      

3) File Name：ドラムセットファイル名  

	ダウンロードされたファイル名が表示されます。  
	名称を変更して別名で保存する場合はこの内容を修正します。      

4) Set Name：ドラムセット名  

	ダウンロードされたドラムセット名が表示されます。本体でドラムセットを選択するときにはこの名前が表示されます。  
	名称を変更して保存する場合はこの内容を修正します。      

5 Inst.1〜Inst.6：楽器名選択ドロップダウン  

	ドラム用感圧パッドP1〜P6に設定する楽器名が一覧表示されます。ドラム用の楽器のみが表示されます。  
	ダウンロードされた設定が現在値として表示されます。    

6) UPLOAD：ドラムセットアップロード  

	編集したドラムセットをPICO2Wにアップロードします。      

## 6. Drum Set List Upload：ドラムセットリスト編集
![picogd_splash](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/web_drumset_list.png)  
1) Drum Set List：ドラムセットリストデータ  

	PICO2W内部のドラムセットリストが表示されます。JSON形式の内部データが表示されるので、JSONフォーマットを崩さないように編集して下さい。  
	本体のドラムセット選択時にはこの順番でコード譜が表示されます。  
	
	["ドラムセットファイル名", ""]
	
	※ASCII文字のみ記述できます。
	※ダブルクォートを使用して下さい（シングルクォートは不可）
	※ファイルフォーマットの詳細は[ConfigManual.md](https://github.com/ohira-s/PicoGuitarDrum2Web/blob/master/Docs/ConfigManual.md)を参照して下さい。  

2) UPLOAD：ドラムセットリストアップロード  

	Drum Set List欄にあるドラムセットリストをPICO2Wにアップロードします。  
	JSON形式の正当性チェックは行なっていますが、JSON形式として問題なければ保存してしまいます。ドラムセットリスト用のJSONの内容を保存して下さい。それ以外を保存した場合の動作の保証はありません。    
