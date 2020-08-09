# 30 Key Ortholinear Keyboard

![sasami30](image/sasami30.jpg)

## 必要なパーツ
| 名前 | 数 | 備考 | 調達先の例 | 参考価格（送料込） |
|:-|:-|:-|--|--|
| SU120 PCB | 2枚 | [入手方法はこちら](../common/pcb_order_guide_jp.md) | [Elecrow Online store](https://www.elecrow.com/) | 10枚で1,400円($12.94) |
| Pro Micro | 1個 | スルーホールをZigzag仕様にしてあるのでコンスルーではなく普通の付属ピンヘッダを使います | [AliExpress](https://www.aliexpress.com/)で「Pro Micro ATmega32U4 5V 16MHz」を検索 | 290円($2.66) |
| タクトスイッチ 2本足のもの | 1個 | | https://ja.aliexpress.com/item/1068908059.html | 50個で100円($0.90) |
| ダイオード 1N4148 | 30個 | ハンダ付けの難易度は上がりますが表面実装ダイオード(1N4148W)も可 | https://ja.aliexpress.com/item/32729204179.html | 100個で90円($0.80) |
| LEDテープ お好みの長さ | 1本 | WS2812Bを使用したもの　※アンダーグローを実装する場合に必要 | https://ja.aliexpress.com/item/32682015405.html | 1mで500円($4.57) |
| Kailh PCBソケット CherryMX用 または Choc用 | 30個 | | https://yushakobo.jp/shop/a01ps/ | 495円+送料330円 |
| 5ピン仕様のキースイッチ CherryMX用 または Choc用 | 30個 |  | https://yushakobo.jp/product-category/switches/ | 1320円～ |
| キーキャップ CherryMX用 または Choc用 | 30個 |  | CherryMX用 https://ja.aliexpress.com/item/32851511530.html | 40個で670円($6.20～) |
| クッションゴム | 6個 |  | ダイソー クッションゴム 14個入り または すべりどめシート | 110円 |
| M1.4ネジ 5mm長 | 2本 |  | https://ja.aliexpress.com/item/32948746653.html | 100本で130円($1.27) |
| M1.4ナット | 2個 | | https://ja.aliexpress.com/item/32883596896.html | 50本で190円($1.80) |
| ポリウレタン銅線 |  | | https://ja.aliexpress.com/item/32628455799.html | 1mで100円($0.85) |
| Micro USBケーブル | 1本 | 通信ができるもの | ダイソー | 110円 |
| 計 |  |  |  | 5,835円 |

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

![pcb_cut](image/pcb_cut.jpg)

最終的に上の図のようにカットします。

まず基板端のビスケットをニッパーで切断します。切ってよい場所は印を付けているので、印の付いているところだけ切断してください。

![biscuits_cut](../common/image/biscuits_cut.jpg)

次に、不要な行を切断します。

![cut_row](image/cut_row.jpg)

行ごと切断するには、ニッパーで表裏に切れ目を入れてから折り割ってください。

![cut_line_1](../common/image/cut_line_1.jpg)

最後に、L字型に切断します。ニッパーで青と赤のラインに両面から切れ目を入れてねじるように折り割ってください。

![cut_l_shape](image/cut_l_shape.jpg)

### 基板側面のヤスリがけ

机に紙ヤスリを置き、その上で基板の側面をヤスリがけします。粗目だけでもそこそこきれいになります。お好みで細目までかけてもよいです。

![sand_pcb](../common/image/sand_pcb.jpg)

![sand_pcb2](../common/image/sand_pcb2.jpg)

![sand_pcb3](../common/image/sand_pcb3.jpg)

### 基板の結合

M1.4ネジとビスケットで基板を結合させます。基板の裏からネジ止めし、ナットを締めます。

![biscuit_contact_surface](../custom-layout/image/biscuit_contact_surface.jpg)

### ダイオードの取り付け

各キースイッチの端の30箇所にダイオードを取り付けます。

キースイッチの枠が描いてあるほうが基板の表で、Kailh PCBソケットの枠が描いてあるほうが裏です。

ダイオードは、以下の理由で基板の裏に付けることを推奨します

- スタビライザーを装着するキースイッチそばのダイオードを表側に付けるとスタビライザーと干渉する。

- ロープロファイルスイッチでトッププレートを付けたい場合はダイオードを表側に付けると干渉する


なお、ロープロファイルスイッチでトッププレートを付けたい場合は、ダイオードの表側に出た足をカットしてからハンダ付けするか、表面実装ダイオードを裏面で使ってください。

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

ハンダ付け不良のリスクを減らすために、事前に片側のみハンダを盛る→ソケットを置いて、ハンダごてで押し付ける→反対側をはんだ付けする、という手順がおすすめです。

![socket_soldered](../common/image/socket_soldered.jpg)

### GNDのジャンパ

基板の裏側のジャンパ3箇所をハンダ付けします。**表側にもジャンパがありますが、裏側のみハンダ付けします**。

![jumper](../common/image/jumper.jpg)

ハンダを盛ってから間を繋ぐのですが、うまくいかない場合はダイオードの切れ端を使って繋いでも構いません。

![jumper_wire](../common/image/jumper_wire.jpg)

![jumper_wire2](../common/image/jumper_wire2.jpg)

### リセットスイッチの取り付け

基板の表側からタクトスイッチをはめ込みます。

![reset_switch](../common/image/reset_switch.jpg)

裏返してハンダ付けします。

### 配線

基板の裏側を以下の図のように配線します。

![3x10wiring](image/3x10wiring.png)

真ん中のROW同士の接続は、ダイオードの足の切れ端を折り曲げてはんだ付けします。

![bend_wire](../common/image/bend_wire.jpg)

![connect_row](../common/image/connect_row.jpg)

それ以外の接続は、ポリウレタン銅線をハンダごてで加熱し、被膜を焼き切ってからはんだ付けします。下の写真はイメージなので、配線は上図のとおりに行ってください。

![uew_wiring3](../custom-layout/image/uew_wiring3.jpg)

### Pro Microの取り付け

基板の表側のPro Micro設置部分の2箇所に、Pro Microに付属している12ピンのピンヘッダの短い側を根本まで差し込みます。

![pin_header_attach](../common/image/pin_header_attach.jpg)

スルーホールがジグザグになっているので、少し入れにくくなっています。ゆっくり押し込んでください。

ピンヘッダにPro Microを差し込みます。**Pro Microの裏面（平らなほう）が上になるように、またマイクロUSBが基板端になるように**します。

**向きを間違えるとリカバリーが大変です。表裏、左右をよく確認してください。**

ニッパーでピンヘッダの足を切ってからPro Microとピンヘッダをハンダ付けします。まず四隅をハンダ付けし、横から見てピンヘッダとの間に隙間があれば押さえながらハンダを温めて浮かないようにします。そのあと、順番に全てハンダ付けします。

![pinheader_cut](../common/image/pinheader_cut.jpg)

基板とピンヘッダはジグザグのスルーホールで接触しているため、ハンダ付けは不要です。

### キースイッチの取り付け

表側から差し込みます。キースイッチの足が曲がっている場合はまっすぐにしてから差し込んでください。

![switch_attach](../common/image/switch_attach.jpg)


### キーキャップの取り付け

キースイッチにキーキャップをはめます。

![keycap_attach](image/keycap_attach.jpg)

### ゴム足の取り付け

ゴム足を裏面に取り付けます。ソケットやキースイッチに接触する場合はハサミで切ってから取り付けます。

![rubber_foot](../common/image/rubber_foot.jpg)

試打してみて、基板のたわみが気になればゴム足を増やしてください。

### ファームウェアの書き込み

以下のリンク先を参考にして、QMK Firmwareのビルド環境を用意します。

- Windows
  - [QMKビルド環境の構築(Windows Msys2編)](https://gist.github.com/e3w2q/4bc86e531d1c893d3d13af3e9895a94a)
- macOS
  - [セットアップ - QMK Firmware](https://docs.qmk.fm/#/ja/newbs_getting_started?id=macos)
- Linux
  - [セットアップ - QMK Firmware](https://docs.qmk.fm/#/ja/newbs_getting_started?id=linux)

構築中、

```
qmk setup
```

と入力する代わりに

```
qmk setup e3w2q/qmk_firmware --branch e3w2q
```

と入力してください。

または、`qmk setup`した後に、`C:\Users\USER_NAME\qmk_firmware\keyboards`配下に[https://github.com/e3w2q/qmk_firmware/tree/e3w2q/keyboards/e3w2q](https://github.com/e3w2q/qmk_firmware/tree/e3w2q/keyboards/e3w2q)以下をコピーしてもよいです。

用意されたキーマップを書き込むには以下を実行します。

```
qmk flash -kb e3w2q/su120/rev1 -km sasami30
```

**Detecting USB port, reset your controller now...** と表示されたらPro Micro横にハンダ付けしたリセットスイッチを押すと書き込みが始まります。

[KeyboardTester.com](https://www.keyboardtester.com/tester.html)等でキー入力が行えるかテストしてください。