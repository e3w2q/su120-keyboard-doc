# 15 key 2 knob keypad

![sasami17](image/sasami17-4.jpg)

## 必要なパーツ
| 名前 | 数 | 備考 | 調達先の例 | 参考価格（送料込） |
|:-|:-|:-|--|--|
| SU120 PCB | 1枚 | [入手方法はこちら](../common/pcb_order_guide_jp.md) | [Elecrow Online Store](https://www.elecrow.com/pcb-manufacturing.html) | 10枚で1,400円($12.94) |
| Pro Micro | 1個 | スルーホールをZigzag仕様にしてあるのでコンスルーではなく普通の付属ピンヘッダを使います | [AliExpress](https://www.aliexpress.com/)で「Pro Micro ATmega32U4 5V 16MHz」を検索 | 290円($2.66) |
| タクトスイッチ 2本足のもの | 1個 | | https://www.amazon.co.jp/dp/B00QLTSZK6 | 50個で184円 |
| ダイオード 1N4148 | 17個 | ハンダ付けの難易度は上がりますが表面実装ダイオード(1N4148W)も可 | https://www.amazon.co.jp/dp/B06WWJ76D7 | 500個で313円 |
| Dシャフト（平軸） プッシュスイッチ付きロータリーエンコーダー | 2個 |  | https://ja.aliexpress.com/item/32835514781.html | 5個で230円($2.12) |
| Dシャフト ロータリーエンコーダー用キャップ | 2個 |  | https://ja.aliexpress.com/item/4000111239246.html | 10個で110円($1.01) |
| Kailh PCBソケット CherryMX用 または Choc用 | 15個 | | https://yushakobo.jp/shop/a01ps/ | 20個で300円+送料300円 |
| 5ピン仕様のキースイッチ CherryMX用 または Choc用 | 15個 |  | https://yushakobo.jp/product-category/switches/ | 20個で800円～ |
| キーキャップ CherryMX用 または Choc用 | 15個 |  | CherryMX用 https://ja.aliexpress.com/item/32851511530.html | 20個で340円～($6.20～) |
| クッションゴム | 4個 |  | ダイソー クッションゴム 14個入り または すべりどめシート | 108円 |
| Micro USBケーブル | 1本 | 通信ができるもの | ダイソー | 108円 |
| 計 |  |  |  | 4,483円 |
### オプション:トッププレートを付ける場合
| 名前 | 数 | 備考 | 調達先の例 | 参考価格（送料込） |
|:-|:-|:-|--|--|
| SU120 Plate PCB | 1枚 | [入手方法はこちら](../common/pcb_order_guide_jp.md) | [Elecrow Online Store](https://www.elecrow.com/pcb-manufacturing.html) | 10枚で1,400円($12.94) |
| M2ネジ 鍋ネジ ネジ長3mm | 8本 |  | https://ja.aliexpress.com/item/32948978177.html | 100本で85円($0.76) |
| M2スペーサー オス-メス スペーサー長3mm | 4個 |  | https://ja.aliexpress.com/item/33022872348.html | 50個で95円($0.85) |
| M2ナット | 4個 |  | https://ja.aliexpress.com/item/33022872348.html | 100個で65円($0.59) |
| M2スペーサー メス-メス スペーサー長5mm | 2個 |  | https://ja.aliexpress.com/item/33022872348.html | 50個で95円($0.87) |
| 計 |  |  |  | 1,675円 |


## 使用する道具、消耗品

[使用する道具、消耗品](../common/tool_guide_jp.md)を参照ください。

## ビルドガイド

### Pro Microのもげ防止加工

Pro Microにエポキシ接着剤を盛って、簡単にはもげないようにします。

参考1:[ProMicroのモゲ防止ついでにQMK_Firmwareを書き込む - Qiita](https://qiita.com/hdbx/items/2f3e4ddfcadda2a5578e)
参考2:[もげ予防 - Self-Made Keyboards in Japan](https://scrapbox.io/self-made-kbds-ja/%E3%82%82%E3%81%92%E4%BA%88%E9%98%B2)

エポキシ接着剤の2液を混ぜます。

![adhesive_prepare](../common/image/promicro_adhesive_prepare.jpg)

接着剤を付け始める前にMicro USBコネクタを横から見てください。側面に穴が開いています。この穴に接着剤が入ると端子が入らなくなったり、入りにくくなったりします。

![usb_side_hole](../common/image/promicro_usb_side_hole.jpg)

この穴を避けて、つまようじなどで接着剤を盛っていきます。

![promicro_pate](../common/image/promicro_pate.jpg)

乾くまで置いておきます。

### 基板のカット

下の図のように、ニッパーで切っていきます。トッププレートを付けない場合は左側のみです。

![pcb_cut](image/pcb_cut-2.jpg)

ニッパーで表裏に切れ目を入れてから手で折り割ってください。

![cut_line_1](../common/image/cut_line_1.jpg)

### 基板側面のヤスリがけ

机に紙ヤスリを置き、その上で基板のバリがある側面をヤスリがけします。粗目だけでも結構きれいになります。お好みで細目までかけてもよいです。

![sand_pcb](../common/image/sand_pcb.jpg)

![sand_pcb2](../common/image/sand_pcb2.jpg)

![sand_pcb3](../common/image/sand_pcb3.jpg)

### ダイオードの取り付け

各キースイッチの端の17箇所にダイオードを取り付けます。

キースイッチの枠が描いてあるほうが基板の表で、Kailh PCBソケットの枠が描いてあるほうが裏です。

ダイオードは、基板の表と裏、どちら側に付けても構いませんが、以下の注意点があります。

- スタビライザーを装着するキースイッチそばのダイオードは、裏側に付けてください。表側だと干渉します。
- ロープロファイルスイッチでトッププレートを付けたい場合は、ダイオードを裏側に取り付け、表側に出た足をカットしてからハンダ付けしてください。表面実装ダイオードを裏側にハンダ付けしてもいいです。

ダイオードの足は、指で根本付近を曲げます。はじめに1つだけダイオードを曲げて穴に差し込んでみて、うまくいく曲げ具合を確認して残りのダイオードを同じように曲げてください。

ダイオードの黒くなっている側が、基板の図の二重線の側になるように差し込みます。

![diode_bent](../common/image/diode_bent.jpg)



![diode_inserted](../common/image/diode_inserted.jpg)

全てのダイオードを配置した後、マスキングテープで浮かないようにカバーしておきます。

![diode_taped](../common/image/diode_taped.jpg)

基板をひっくり返してダイオードを全てハンダ付けし、ニッパーで足を切ります。ダイオードの足を切ってからハンダ付けしても構いません。私はハンダ付けのときに周りの足が邪魔なのと、後がきれいになるので、最近はカットしてからハンダ付けするようにしています。

![diode_soldered](../common/image/diode_soldered.jpg)

### PCBソケットの取り付け

基板の裏の印刷された枠に合うようにPCBソケットを配置します。
CherryMX用のPCBソケットを置く場合は、間違った向きに置かないように注意してください。間違った向きに取り付けるとあとでキースイッチが入りません。

![socket_attached](../common/image/socket_attached.jpg)
![socket_attached_all](../common/image/socket_attached_all.jpg)

PCBソケット両端の金属部分をハンダ付けします。

![socket_soldered](../common/image/socket_soldered.jpg)

### GNDのジャンパ

基板の裏側のジャンパ3箇所をハンダ付けします。**表側にもジャンパがありますが、裏側のみハンダ付けします**。

![jumper](../common/image/jumper.jpg)

ハンダを盛ってから間を繋いでください。どうしてもうまくいかない場合はダイオードの切れ端を使って繋いでも構いません。

![jumper_wire](../common/image/jumper_wire.jpg)

![jumper_wire2](../common/image/jumper_wire2.jpg)

### リセットスイッチの取り付け

基板の表側からタクトスイッチをはめ込みます。

![reset_switch](../common/image/reset_switch.jpg)

裏返してハンダ付けします。

### Pro Microの取り付け

基板の表側のPro Micro設置部分の2箇所に、Pro Microに付属している12ピンのピンヘッダの短い側を根本まで差し込みます。

![pin_header_attach](../common/image/pin_header_attach.jpg)

スルーホールがジグザグになっているので、少し入れにくくなっています。ゆっくり押し込んでください。

ピンヘッダにPro Microを差し込みます。**Pro Microの裏面（平らなほう）が上になるように、またマイクロUSBが基板端になるように**します。

**向きを間違えるとリカバリーが大変です。表裏、左右をよく確認してください。**

ニッパーでピンヘッダの足を切ってから、Pro Microとピンヘッダをハンダ付けします。まず四隅をハンダ付けし、横から見てピンヘッダとの間に隙間があれば押さえながらハンダを温めて浮かないようにします。そのあと、順番に全てハンダ付けします。

![pinheader_cut](../common/image/pinheader_cut.jpg)

基板とピンヘッダはジグザグのスルーホールで接触しているため、ハンダ付けは不要です。

### ロータリーエンコーダーの取り付け

表側から差し込み、裏側をはんだ付けします。まずは対角の2箇所をハンダ付けし、傾いている場合はハンダを温めて傾きを解消してから残りの箇所をハンダ付けしてください。

![rotary_encoder](../common/image/rotary_encoder.jpg)

そのあと、ロータリーエンコーダーにキャップを取り付けます。

### トッププレートの取り付け（オプション）

外周から一つ内側の4箇所にM2スペーサー（オス-メス）を差し込み、裏側からM2ナットで留めます。

![top_plate_attach_1](image/top_plate_attach_1.jpg)

トッププレートを置き、M2ネジとスペーサーでトッププレートを挟んでネジ留めします。

![top_plate_attach_2](image/top_plate_attach_2.jpg)

### カバープレートの取り付け（オプション）

Pro MicroのカバープレートをM2ネジとM2スペーサー5mmで挟んでネジ留めします。

カバープレートは表と裏でデザインが違っているので、好きなほうを表面としてください。

![cover_plate_attach_1](../common/image/cover_plate_attach_1.jpg)

そのあと、基板裏からM2ネジでカバープレートを取り付けます。

![cover_plate_attach_2](../common/image/cover_plate_attach_2.jpg)

### キースイッチの取り付け

表側から差し込みます。キースイッチの足が曲がっている場合はまっすぐにしてから差し込んでください。

![switch_attach](../common/image/switch_attach.jpg)


### キーキャップの取り付け

キースイッチにキーキャップをはめます。

![keycap_attach_2](image/keycap_attach_2.jpg)

### ゴム足の取り付け

ゴム足を裏面に取り付けます。ソケットやキースイッチに接触する場合はハサミで切ってから取り付けます。

![rubber_foot](../common/image/rubber_foot.jpg)

試打してみて、基板のたわみが気になればゴム足を増やしてください。

### ファームウェアの書き込み

まず、以下のリンク先を参考にして、QMK Firmwareのビルド環境を用意します。
- [プログラマーではない人向けのQMK Firmware入門 - Qiita](https://qiita.com/cactusman/items/ac41993d1682c6d8a12e)
- [Getting Started - QMK Firmware](https://docs.qmk.fm/#/newbs_getting_started)

ビルド環境構築時に持ってくるQMK Firmwareは、フォークした[https://github.com/e3w2q/qmk_firmware/tree/su120](https://github.com/e3w2q/qmk_firmware/tree/su120)とします。または、本家を持ってきて、そこに[https://github.com/e3w2q/qmk_firmware/tree/su120/keyboards/handwired/su120](https://github.com/e3w2q/qmk_firmware/tree/su120/keyboards/handwired/su120)以下をコピーしてもよいです。

用意されたキーマップを書き込むにはqmk_firmwareのフォルダに移動し、以下を実行します。

```
make handwired/su120/rev1_4knob:sasami17:avrdude  
```

**Detecting USB port, reset your controller now...** と表示されたらPro Micro横にハンダ付けしたリセットスイッチを押すと書き込みが始まります。

[KeyboardTester.com](https://www.keyboardtester.com/tester.html)等でキー入力が行えるかテストしてください。