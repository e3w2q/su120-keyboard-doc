[English](index.md) / [日本語](index_jp.md)

# SU120で自由なレイアウトを作成するには

![1](image/1.jpg)

![2](image/2.jpg)

SU120では基板間をビスケットで接続することである程度自由なキー配置が可能です。

## 配置できるキー数の上限

ロータリーエンコーダー無しの場合、Pro Micro1つにつき最大6行10列=60キーを配置できます。

![6x10](image/6x10.png)

2つのPro MicroをTRRSケーブルで接続することにより、片側60キー、合計120キーの分割キーボードとして使えます。

![momo120](../momo120/image/momo120.jpg)

DuplexMatrixとして配線することで、さらに倍の240キーまで利用可能となりますが、ここでは説明を割愛します。

ロータリーエンコーダーを使う場合、ロータリーエンコーダー1つにつき2つのピンを使うため、キー配置に使えるピンがその分減ります。

具体的には、Pro Micro1つに対しロータリーエンコーダーを2つ配置する場合、最大6行6列=36キーを配置できます。

![6x6](image/6x6.png)

Pro Micro1つに対しロータリーエンコーダーを1つ配置する場合、最大6行8列=48キーを配置できます。

![6x8](image/6x8.png)

なお、この行と列は配線上のものであり、例えば6行6列を下図のように組むことで、レイアウト上は3行12列とすることも可能です。

![3x12](image/3x12.png)

## 基板をつなぐネジ

基板をつなぐネジはM1.4ネジを使用します。皿ネジではなく、基板との接地面が大きい鍋ネジなどを使ってください。

ネジ長5mmのM1.4ネジとM1.4ナットを併用するのが確実です。

![4](image/4.jpg)

ネジの調達先によっては、ナット無しでネジ長3mmのM1.4ネジだけで固定できることがあります。ネジ長3mmの場合、基板からはみ出しません。

![5](image/5.jpg)

今のところの経験則は以下のとおりです。

- [ウィルコ](https://wilco.jp/)、[ヒロスギ](http://hirosugi.co.jp/)のM1.4ネジは、基板の穴に対してネジが太めで、ネジ留めが固く、ナット無しで組める。
- ウィルコはM1.4ナットがかなり高い（100個買う場合で税抜単価92円）。ヒロスギはM1.4ナットがラインナップにない。

- Aliexpressの100本で1ドル台の安いM1.4ネジは、ネジが若干細めで、しっかり組むにはM1.4ナットも合わせて調達したほうがよい。

- 一度の発注で届く10枚の基板の中でも微妙な個体差があり、ネジ留めがきつかったりゆるかったりする。

そのため、個人的には以下のようにしています。

- 届くまで2～3週間待てるときは、Aliexpressでネジ長5mmのM1.4ネジとM1.4ナットを買う。足りなくなるとまた届くまで時間がかかるので、必要な数の2倍買う。
- 2～3週間待ちたくないときは、ウィルコ、ヒロスギでネジ長3mmのM1.4ネジを買う。
- とにかく固く頑丈にしたいときは、ウィルコ、ヒロスギでネジ長5mmのM1.4ネジを買い、ナット無しで仮組みする。別途AliexpressでM1.4ナットを発注し、後日ナットを付けて締める。

## ビスケット

カットした基板を繋ぐために使う部品です。

基板の外周に配置されています。カット位置に線を入れてありますので、ここをニッパーで切ってください。小さいパーツなので、飛んでいかないように手を添えてください。

![biscuits_cut](../common/image/biscuits_cut.jpg)

ビスケットのネジ穴はキースイッチを配置する部分の四隅、キースイッチを配置する19.05mm角の四角の頂点から縦横1/8(2.38125mm)だけ内側にあります。

![3](image/3.png)

キースイッチに干渉しないように、基板の裏側から取り付けます。

![biscuit_contact_surface](image/biscuit_contact_surface.jpg)

linearと書いてあるビスケットは、格子配列や横に並んだキー配列など、直線で接続する場合に使います。

staggerと書いてあるビスケットは、Row-Staggered、Column-Staggeredなど、ずらして接続する場合に使います。

例えば、格子配列の場合、縦横方向の結合に1u linearを使い、筋交い用に0.25u staggerを使います。

![matrix_layout_biscuits](image/matrix_layout_biscuits.jpg)

詳しくは以下の表をご覧ください。基板4枚で60%キーボードレイアウト（US、JIS）が可能となるように数量を設計してあります。

| 印字 |   |   | 数量 | 概要 | 接続例（赤丸同士を接続） |
| ------------ | ------------------------------------------------------ | ---- | ---------------- | ---------------- | ---------------- |
| 1u linear    | ![](image/1u_linear.jpg) | ![](image/1u_linear.png) | 5 | 1U間を接続 | ![](image/b2-0.png)<br />![](image/b2-0b.png) |
| 1.25u linear | ![](image/1.25u_linear.jpg) | ![](image/1.25u_linear.png)  | 2 | 1Uと1.25Uを接続 | ![](image/b3-0.png) |
| 1.5u linear<br />1u linear | ![](image/1.5u_linear_1u_linear.jpg) | ![](image/1.5u_linear_1u_linear.png) | 1 | 1Uと1.5Uを接続<br />1.25U同士を接続<br />切れ目で切り離すと1u linearとして使える | ![](image/b4-0.png)<br />![](image/b4-0b.png) |
| 2u linear<br />1.5u linear<br />1u linear | ![](image/2u_linear_1.5u_linear_1u_linear.jpg) | ![](image/2u_linear_1.5u_linear_1u_linear.png) | 1 | 1Uとスタビライザー無しの2Uを接続<br />0.5U空けたキー配置にも使用<br />切れ目で切り離すと1.5u linearまたは1u linearとして使える | ![](image/b6-0.png)<br />![](image/b6-0b.png) |
| 1/8u stagger    | ![](image/1-8u_stagger.jpg) | ![](image/1-8u_stagger.png) | 6    | 1Uを0.125u(1/8u)ずらして接続 | ![](image/b2-1.png)<br />![](image/b2-1b.png) |
| 0.25u stagger    | ![](image/0.25u_stagger.jpg) | ![](image/0.25u_stagger.png) | 4    | 1Uを0.25u(1/4u)ずらして接続<br />1Uを0.5u(1/2u)ずらして接続する場合にも使用<br />格子配列の斜め方向の筋交いにも使用 | ![](image/b2-2.png)<br />![](image/b2-2b.png) |
| 3/8u stagger    | ![](image/3-8u_stagger.jpg) | ![](image/3-8u_stagger.png) | 1    | 1Uを0.375u(3/8u)ずらして接続 | ![](image/b2-3.png)<br />![](image/b2-3b.png) |
| 0.5u stagger<br />0.25u stagger    | ![](image/0.5u_stagger_0.25u_stagger.jpg) | ![](image/0.5u_stagger_0.25u_stagger.png) | 1 | 1Uを0.5u(1/2u)ずらして接続<br />切れ目で切り離すと0.25u staggerとして使える | ![](image/b2-4.png) |
| 5/8u stagger<br />3/8u stagger    | ![](image/5-8u_stagger_3-8u_stagger.jpg) | ![](image/5-8u_stagger_3-8u_stagger.png) | 1 | 1Uを0.625u(5/8u)ずらして接続<br />切れ目で切り離すと3/8u staggerとして使える | ![](image/b2-5.png) |
| 0.75u stagger<br />3/8u stagger | ![](image/0.75u_stagger_3-8u_stagger.jpg) | ![](image/0.75u_stagger_3-8u_stagger.png) | 1 | 1Uを0.75u(3/4u)ずらして接続<br />切れ目で切り離すと3/8u staggerとして使える | ![](image/b2-6.png) |

## 配線に使うワイヤ

格子配列や近いところの接続であれば、ダイオードの足の切れ端を折り曲げて使うと便利です。

![bend_wire](../common/image/bend_wire.jpg)

![8](image/8.jpg)

遠いところの接続は、ショートを避けるために被覆された線を使います。

![wiring](image/wiring.jpg)

配線が多い場合は、厚みを減らすためにポリウレタン銅線を使うとよいです。

最初のうちは0.5mmのポリウレタン銅線を使い、曲げて形を作ってからはんだ付けしていましたが、地味に手間がかかります。

![uew_wiring3](image/uew_wiring3.jpg)

最近は0.29mmのポリウレタン銅線を使い、直線で配線しています。

![uew_wiring2](image/uew_wiring2.jpg)

ポリウレタン銅線の太さについては、以下のScrapboxの記事が参考になります。

- [ポリウレタン銅線 - Self-Made Keyboards in Japan](https://scrapbox.io/self-made-kbds-ja/ポリウレタン銅線)

なお、ポリウレタン銅線を直線で配線するときは、ダイオード、ソケットのはんだ付けの後に行ってください。

## キーマトリクスの配線

基板をビスケットで繋いだあと、縦横のキーマトリクスの配線を繋ぎます。

縦方向はCOLと印字されたスルーホール（例えば、下図の赤色のマル印）が導通するようにします。

横方向も同様に、ROWと印字されたスルーホール（例えば、下図の青色のマル印）が導通するようにします。

プレ配線済みですので、基板が繋がっていれば導通します。

![9](image/9.jpg)

基板が繋がっていないところは配線が必要です。先にも触れたように、ダイオードの足の切れ端を折り曲げてはんだ付けするのが楽です。

![bend_wire](../common/image/bend_wire.jpg)

![8](image/8.jpg)

## Pro Microとキーマトリクスとを接続する配線

キーマトリクスの導通が確認できたら、次はPro Microとキーマトリクスを接続します。

基板の表側から見て、横は最大10キーで、左からA B C D E F G H I J、縦は最大6キーで、上から1 2 3 4 5 6となります。

![6x10](image/6x10.png)ロータリーエンコーダー2個を使う場合は、横は最大6キーとなります。ロータリーエンコーダー1個を使う場合は、横は最大8キーとなります。

名前の付け方は、Microsoft Excelの番地と同じです。

![10](image/10.png)

![front_side_with_address](image/front_side_with_address.jpg)

基板を裏返して、Pro Micro裏のシルク印刷の番地と該当行・該当列をポリウレタン銅線（UEW線）などで結線していきます。

なお、基板の状態で、Pro Microとキーとは、以下の番地となるように配線済みです。

![7](image/7.jpg)

裏側（イメージ）

![11](image/11.png)

基板を連結して拡張する場合は、拡張した行及び列と、Pro Microとの結線が必要となります。

結線の最、該当行・該当列は、どのスルーホールを使ってもよいです。

例えば、Pro MicroのCという印字のスルーホール（オレンジ色の四角）と繋ぐのは、C列のスルーホール（オレンジ色のマル）のどれでも構いません。

Pro Microの3という印字のスルーホール（青色の四角）と繋ぐのは、3行目のスルーホール（青色のマル）のどれでも構いません。

![connect_address](/image/connect_address.jpg)

ロータリーエンコーダー2つの場合、最大で6行6列なので右に1列（F列まで）、下は既存の4行目を折り割って、6行まで拡張可能です。これに必要な基板は3枚であり、例えば赤矢印の部分を結線します。

ロータリーエンコーダーのプッシュボタンには6D、6Eを割り当ててあるため、プッシュボタンと6D、6Eのキーは同じ挙動となります。

![6x6wiring](image/6x6wiring.png)

ロータリーエンコーダーが1つのとき、最大で6行8列なので右に3列（H列まで）、下は既存の4行目を折り割って、6行まで拡張可能です。これに必要な基板は4枚であり（細かく繋げば3枚でも可能）、例えば赤矢印の部分を結線します。

![6x8wiring](image/6x8wiring.png)

ロータリーエンコーダー無しのとき、最大で6行10列なので右に5列（J列まで）、下は既存の4行目を折り割って、6行まで拡張可能です。これに必要な基板は4枚であり、例えば赤矢印の部分を結線します。

![6x10wiring](image/6x10wiring.png)

## GNDのジャンパ

Pro Microを1つしか使わない場合は実施しなくても問題ないのですが、分割キーボードとして使用する場合は、基板の裏側のジャンパ3箇所をハンダ付けします。**表側にもジャンパがありますが、裏側のジャンパのみハンダ付けします**。

![jumper](../common/image/jumper.jpg)

ハンダを盛ってから間を繋いでください。どうしてもうまくいかない場合はダイオードの切れ端を使って繋いでも構いません。

![jumper_wire](../common/image/jumper_wire.jpg)

![jumper_wire2](../common/image/jumper_wire2.jpg)

## ファームウェア

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
qmk flash -kb e3w2q/re5/rev1 -km default
```

デフォルトキーマップを書き込むには、ロータリーエンコーダーの数に合わせて以下を実行します。

- ロータリーエンコーダーなし
  ```
  qmk flash -kb e3w2q/su120/rev1 -km default
  ```
- ロータリーエンコーダー2個（右手1個、左手1個）
  ```
  qmk flash -kb e3w2q/su120/rev1_2knob -km default
  ```
- ロータリーエンコーダー4個（右手2個、左手2個）
  ```
  qmk flash -kb e3w2q/su120/rev1_4knob -km default
  ```

デフォルトキーマップのほかに、テスト用のキーマップを用意しています。

テスト用のキーマップでは、入力したキーの論理的な配置（例えば1行目A列のキーなら「A1」）が入力されます。スレーブ側の入力は頭に「S」が付きます。ロータリーエンコーダーは回すと「1ST_ENC_R」「1ST_ENC_L」などが入力されます。

[QMK Configuratorのテストモード](https://config.qmk.fm/#/test)を使わずに全キーの入力テストを行う際にご利用ください。

- ロータリーエンコーダーなし
  ```
  qmk flash -kb e3w2q/su120/rev1 -km test
  ```
- ロータリーエンコーダー2個（右手1個、左手1個）
  ```
  qmk flash -kb e3w2q/su120/rev1_2knob -km test
  ```
-  ロータリーエンコーダー4個（右手2個、左手2個）
  ```
  qmk flash -kb e3w2q/su120/rev1_4knob -km test
  ```

**Detecting USB port, reset your controller now...** と表示されたらPro Micro横のリセットスイッチを押すと書き込みが始まります。

