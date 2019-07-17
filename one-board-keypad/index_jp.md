# SU120で作るOne Board Keypad

![keycap_attached](keycap_attached.jpg)

## 必要なパーツ
<!--- Bill Of Materials -->
| 名前 | 数 | 備考 |
|:-|:-|:-|
| SU120 PCB | 1枚 | [入手方法はこちら](../common/pcb_order_guide_jp.md) |
| Pro Micro | 1個 | スルーホールをZigzag仕様にしてあるのでコンスルーではなく普通の付属ピンヘッダを使います |
| タクトスイッチ 2本足のもの | 1個 | |
| ダイオード 1N4148 | 20個 | ハンダ付けの難易度は上がりますが表面実装ダイオード(1N4148W)も可 |
| LEDテープ お好みの長さ | 1本 | WS2812Bを使用したもの |
| Kailh PCBソケット CherryMX用 または Choc用 | 20個 | |
| 5ピン仕様のキースイッチ CherryMX用 または Choc用 | 20個 | トッププレートがないので3ピン仕様だとガタガタになります |
| キーキャップ CherryMX用 または Choc用 | 20個 | 19個は1U、1個は2U |
| スタビライザー PCBマウント用 2U | 1個 | 後で付けることも可能なので無いなら無いでOK |
| クッションゴム | 4個以上 | たわみが気になれば増やしてください 適当なものが見つからなければとりあえず100円ショップの滑り止めシートを敷いても |
| Micro USBケーブル | 1本 | |

## 使用する道具類

[SU120で使用する道具、消耗品](../common/tool_guide_jp.md)を参照ください。

## ビルドガイド

### Pro Microのもげ防止加工

Pro Microにエポキシ接着剤を盛って、簡単にはもげないようにします。

参考1:[ProMicroのモゲ防止ついでにQMK_Firmwareを書き込む - Qiita](https://qiita.com/hdbx/items/2f3e4ddfcadda2a5578e)
参考2:[もげ予防 - Self-Made Keyboards in Japan](https://scrapbox.io/self-made-kbds-ja/%E3%82%82%E3%81%92%E4%BA%88%E9%98%B2)

エポキシ接着剤の2液を混ぜます。つまようじを用意します。

![adhesive_prepare](adhesive_prepare.jpg)

接着剤を付け始める前にMicro USBコネクタを横から見てください。側面に穴が開いています。この穴に接着剤が入ると端子が入らなくなったり、入りにくくなったりします。

![usb_side_hole](usb_side_hole.jpg)

この穴を避けて、つまようじで接着剤を付けていきます。

![promicro_pate](promicro_pate.jpg)

乾くまで置いておきます。


### ダイオードの取り付け

19箇所にダイオードを配置します。

基板の表と裏、どちら側に付けても構いません。
なお、キースイッチを配置する枠が描いてあるほうが表で、Kailh PCBソケットを配置する枠が描いてあるほうが裏です。

はじめに1つだけダイオードを曲げて穴に差し込んでみて、うまくいく曲げ具合を見つけて残りのダイオードを同じように曲げておくとやりやすいです。

![diode_bent](diode_bent.jpg)

ダイオードの黒くなっている側が、基板の図の二重線の側になるように差し込みます。

![diode_inserted](diode_inserted.jpg)

全てのダイオードを配置した後、マスキングテープで浮かないようにカバーしておきます。

![diode_taped](diode_taped.jpg)

基板を裏返して全てハンダ付けします。

![diode_soldered](diode_soldered.jpg)

ハンダから飛び出ている線を切ります。

### PCBソケットの取り付け

基板の裏の枠に合うようにPCBソケットを配置します。
CherryMX用のPCBソケットを置く場合は、間違った向きに置かないように注意してください。間違った向きに取り付けるとあとでキースイッチが入りません。

![socket_attached](socket_attached.jpg)
![socket_attached_all](socket_attached_all.jpg)

PCBソケット両端の金属部分をハンダ付けします。

![socket_soldered](socket_soldered.jpg)

### TRRSコネクタの取り付け

基板の表側の枠に合うようにTRRSコネクタを配置します。

![trrs_jack_attached](trrs_jack_attached.jpg)

裏返して金属部分をハンダ付けします。

![trrs_jack_attached](trrs_jack_attached.jpg)

### タクトスイッチの取り付け

基板の表側の枠に合うようにタクトスイッチを配置します。

裏返して金属部分をハンダ付けします。

### Pro Microの取り付け

基板の表側のPro Micro設置部分の2箇所に、Pro Microに付属している12ピンのピンヘッダの短い側を差し込みます。

![pin_header_attaching](pin_header_attaching.jpg)

スルーホールがジグザグになっているので、少し入れにくくなっています。ゆっくり押し込んでください。

基板とピンヘッダはジグザグのスルーホールで接触しているため、ハンダ付けしません。

ピンヘッダにPro Microを差し込みます。Rev.2以降はPro Microの裏面（平らなほう）が上になるようにします。

Pro Microとピンヘッダをハンダ付けします。

![promicro_soldered](promicro_soldered.jpg)

### スタビライザーの取り付け

![stabilizer_attached](stabilizer_attached.jpg)

基板の都合により、スタビライザーの片側はしっかり留まりません。

![stabilizer_loose](stabilizer_loose.jpg)

試用してみてよさそうなら、エキポシ接着剤で固定するとよいかもしれません。

### キースイッチの取り付け

表側から19箇所に差し込みます。キースイッチの足が曲がっている場合はまっすぐにしてから差し込んでください。

![switch_attached](switch_attached.jpg)


### キーキャップの取り付け

キースイッチにキーキャップをはめます。

![keycap_attached](keycap_attached.jpg)

### ゴム足の取り付け

ゴム足を裏面に取り付けます。試打して基板のたわみが気になればゴム足を増やします。

### ファームウェアの書き込み

自作キーボードでは主にQMK Firmwareが使われますが、この書き込みには、いろいろな方法があります。

- [QMK Firmware](https://github.com/qmk/qmk_firmware)本家に取り込まれている
  - GUIの[QMK Toolbox](https://github.com/qmk/qmk_toolbox)を使う
  - CUIでQMK Firmwareをビルドして使う
- [QMK Firmware](https://github.com/qmk/qmk_firmware)本家に取り込まれていない
  - 作者がフォークしたQMK FirmwareをCUIでQMK Firmwareをビルドして使う

SU120は[QMK Firmware](https://github.com/qmk/qmk_firmware)本家に取り込まれていないので、最後の方法を説明します。

まず、以下のリンク先を参考にして、QMK Firmwareのビルド環境を用意します。
- [プログラマーではない人向けのQMK Firmware入門 - Qiita](https://qiita.com/cactusman/items/ac41993d1682c6d8a12e)
- [Getting Started - QMK Firmware](https://docs.qmk.fm/#/newbs_getting_started)

ビルド環境構築時に持ってくるQMK Firmwareは、フォークした[https://github.com/e3w2q/qmk_firmware/tree/su120](https://github.com/e3w2q/qmk_firmware/tree/su120)とします。または、本家を持ってきて、そこに[https://github.com/e3w2q/qmk_firmware/tree/su120/keyboards/handwired/su120](https://github.com/e3w2q/qmk_firmware/tree/su120/keyboards/handwired/su120)以下をコピーしてもよいです。

デフォルトキーマップを書き込むにはqmk_firmwareのフォルダに移動し、以下を実行します。

```
make handwired/su120/rev1:default:avrdude  
```

**Detecting USB port, reset your controller now...** と表示されたらPro Micro横にハンダ付けしたリセットスイッチを押すと書き込みが始まります。

