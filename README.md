# ADE32CD-オーディオストリーミングスタンド開発ボードの動作確認

### *製品ページは[こちら](http://bit-trade-one.co.jp/ADE32CD)*.

### *他サンプル*

 - [ConnectedDoll サンプルリポジトリ](https://github.com/ConnectedDoll/examples#connecteddoll-%E3%82%B5%E3%83%B3%E3%83%97%E3%83%AB%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA)

 - [OpenAI ChatAPI  (GPT) に繋ぐためのライブラリ](https://github.com/tfuru/ESP32OpenAIChatAPI#esp32openaichatapi)

### [回路図](https://github.com/bit-trade-one/ADE32CD-Connected-Doll/blob/master/Schematics/ADE32CM_V1.1_Schematics.pdf)

### [FAQ](https://github.com/bit-trade-one/ADE32CD-Connected-Doll/blob/master/FAQ.md)

## ファイルリスト
- Readme.md             ［本文書］
- bt_speaker_demo.ino    [Bluetoothスピーカーサンプルプログラム］
- ADE32CD_test.ino       [販売時書き込み済みプログラム］

## 開発環境
本製品の動作確認は、以下の環境で実施することを前提としております。
- Arduino IDE<BR>
  Arduino IDE 1.8.19
- ボードマネージャー<BR>
ESP32 by Espressif Systems バージョン2.0.4
- ライブラリ<BR>
FastLED 3.5.0<BR>
[ESP32-A2DP 1.7.0](https://github.com/pschatzmann/ESP32-A2DP<BR>
@pschatzmann氏のESP32-A2DPライブラリを使用させていただきました。<BR>
Thanks to @pschatzmann, author of the ESP32-A2DP library.


## インストール
- ボードマネージャーの設定<BR>
ESP32ボードマネージャのURLを、Arduino環境設定ダイアログの追加のボードマネージャのURL欄に追加します。<BR>
![](./img/README2022-07-12-09-28-24.png)
```
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
```

- ESP32ボードマネージャのインストール<BR>
Arduino IDEのボードマネージャからESP32 by Espressif Systems バージョン2.0.4をインストールします。
![](./img/README2022-07-12-09-40-08.png)
![](./img/README2022-07-12-09-31-34.png)

- FastLEDライブラリ3.5.0<BR> 
Arduino IDEのライブラリマネージャからインストールしてください。
![](./img/Readme2022-06-21-16-22-53.png)

- ESP32-A2DP 1.7.0<BR>
GitHubからzip形式でダウンロード後、Arduino IDEの「スケッチ」「ライブラリをインクルード」「.ZIP形式のライブラリをインストール」を選択し、ダウンロードしたzipファイルを指定します。
![](./img/Readme2022-06-21-16-23-53.png)

- bt_spaker_demo<BR>
Arduino IDEの「ファイル」「開く」から予めダウンロード済みの「bt_speaker_demo.ino」を入力します。
![](./img/Readme2022-06-21-16-35-54.png)

- Arduino IDEの設定<BR>
「ツール」メニューから「ボード」は「ESP32 Dev Module」、「シリアルポート」はコネクティッドドールを接続したCOM番号を指定します。
![](./img/Readme2022-06-21-16-39-11.png)

- ビルドとインストール<BR>
「スケッチ」「マイコンボードに書き込む」からビルドとインストールを実施します。
書込みが完了すると、基板周辺の4つのLEDのが赤く点灯します。

## 使用方法
IOSやAndroidのBluetoothメニューから、デバイス名「BTO_Music」を選択肢し、ペアリングします。その後、音楽プレーヤー等で音楽等を再生してください。
音楽等が再生できること、および再生中に基板周辺のLEDが点滅することを確認してください。 
