[English](index.md) / [日本語](index_jp.md)

# How to create a custom layout with SU120

![1](image/1.jpg)

![2](image/2.jpg)

The SU120 allows a certain degree of freedom in key arrangement by connecting the boards with biscuits.

## Maximum number of keys that can be placed

Without a rotary encoder, up to 6 rows and 10 columns = 60 keys can be placed per Pro Micro.

![6x10](image/6x10.png)

By connecting two Pro Micro with TRRS cable, it can be used as a split keyboard with 60 keys on one side and a total of 120 keys.

![momo120](../momo120/image/momo120.jpg)

By wiring as DuplexMatrix, it is possible to use up to 240 times more keys, but I will omit the explanation here.

When using a rotary encoder, two pins are used for each rotary encoder, so the number of pins that can be used for key placement is reduced accordingly.

Specifically, when two rotary encoders are arranged for one Pro Micro, a maximum of 6 rows and 6 columns = 36 keys can be arranged.

![6x6](image/6x6.png)

If you place one rotary encoder for one Pro Micro, you can place up to 6 rows and 8 columns = 48 keys.

![6x8](image/6x8.png)

Note that these rows and columns are on the wiring. For example, by combining 6 rows and 6 columns as shown in the figure below, the layout can be 3 rows and 12 columns.

![3x12](image/3x12.png)

## Screw to connect the board

Use M1.4 screws to connect the boards. Use a pan-head screw with a large ground contact surface, not a flat head screw.

It is certain to use a M1.4 screw with a screw length of 5 mm and an M1.4 nut together.

![4](image/4.jpg)

Depending on the source of the screw, it may be possible to fix it with just a M1.4 screw with a screw length of 3 mm without a nut. If the screw length is 3mm, it will not protrude from the board.

![5](image/5.jpg)

The rules of thumb so far are as follows:

-[Wilco](https://wilco.jp/)'s and [Hirosugi](http://hirosugi.co.jp/)'s M1.4 screws are thicker than the holes in the board, and the screws are tight. Can be assembled without nuts.
-Wilco's M1.4 nut is quite expensive (if you buy 100, the unit price before tax is 92 yen). Hirosugi does not have an M1.4 nut in the lineup.

-Aliexpress's 100 cheap M1.4 screws that cost around $ 1 are slightly thinner, and it is better to procure M1.4 nuts together to assemble securely.

-There are subtle differences among the 10 boards that can be received in one order, and the screwing is tight or loose.

Therefore, I personally do the following.

-If you can wait 2-3 weeks for delivery, buy 5mm M1.4 screw and M1.4 nut on Aliexpress. If it runs short, it takes time to arrive again, so buy twice as many as you need.
-If you do not want to wait 2-3 weeks, buy M1.4 screws with a screw length of 3 mm from Wilco and Hirosugi.
-If you want to make it hard and strong anyway, buy M1.4 screws with a screw length of 5mm with Wilco and Hiroshi, and temporarily assemble without nuts. Order M1.4 nuts separately from Aliexpress, and tighten them with nuts at a later date.

## Biscuits

These parts are used to connect cut boards.

Located on the outer periphery of the board. There is a line at the cutting position, so cut it with a nipper. Since it is a small part, please attach your hand so that it does not fly.

![biscuits_cut](../common/image/biscuits_cut.jpg)

The screw holes of the biscuit are located at the corners of the part where the key switch is placed, and the inside of the corner of the 19.05 mm square where the key switch is placed by 1/8 (2.38125 mm) vertically and horizontally.

![3](image/3.png)

Install from the back side of the board so that it does not interfere with the key switch.

![biscuit_contact_surface](image/biscuit_contact_surface.jpg)

Biscuits written as linear are used when connecting in a straight line such as a grid layout or a side-by-side key layout.

Biscuits written as stagger are used when connecting staggered, such as Row-Staggered and Column-Staggered.

For example, for a grid layouts, use 1u linear for vertical and horizontal connections and 0.25u stagger for bracing.

![matrix_layout_biscuits](image/matrix_layout_biscuits.jpg)

See the table below for details. Quantity is designed so that 60% keyboard layout (US, JIS) is possible with 4 boards.

| Printing | | | Quantity | Overview | Connection example (connecting red circles) |
| ------------ | ------------------------------------------------------ | ---- | ---------------- | ---------------- | ---------------- |
| 1u linear    | ![](image/1u_linear.jpg) | ![](image/1u_linear.png) | 5 | Connect 1U | ![](image/b2-0.png)<br />![](image/b2-0b.png) |
| 1.25u linear | ![](image/1.25u_linear.jpg) | ![](image/1.25u_linear.png)  | 2 | Connect 1U and 1.25U | ![](image/b3-0.png) |
| 1.5u linear<br />1u linear | ![](image/1.5u_linear_1u_linear.jpg) | ![](image/1.5u_linear_1u_linear.png) | 1 | Connect 1U and 1.5U <br />Connect 1.25U<br />1.25U Can be used as a 1u linear by disconnecting at the break <br /> | ![](image/b4-0.png)<br />![](image/b4-0b.png) |
| 2u linear<br />1.5u linear<br />1u linear | ![](image/2u_linear_1.5u_linear_1u_linear.jpg) | ![](image/2u_linear_1.5u_linear_1u_linear.png) | 1 | 1U with no stabilizer Connect 2U <br />Use it for key arrangement with 0.5U space <br />If you separated by a cut, you can use it as a 1.5u linear or 1u linear. | ![](image/b6-0.png)<br />![](image/b6-0b.png) |
| 1/8u stagger    | ![](image/1-8u_stagger.jpg) | ![](image/1-8u_stagger.png) | 6    | Connect 1U by 0.125u (1 / 8u) | ![](image/b2-1.png)<br />![](image/b2-1b.png) |
| 0.25u stagger    | ![](image/0.25u_stagger.jpg) | ![](image/0.25u_stagger.png) | 4    | Connect 1U by 0.25u (1 / 4u) shift<br />Connect 1U by 0.5u (1 / 2u) shift <br />Used for diagonal bracing of the grid layouts | ![](image/b2-2.png)<br />![](image/b2-2b.png) |
| 3/8u stagger    | ![](image/3-8u_stagger.jpg) | ![](image/3-8u_stagger.png) | 1    | Connect 1U by 0.375u (3 / 8u) shift | ![](image/b2-3.png)<br />![](image/b2-3b.png) |
| 0.5u stagger<br />0.25u stagger    | ![](image/0.5u_stagger_0.25u_stagger.jpg) | ![](image/0.5u_stagger_0.25u_stagger.png) | 1 | Connect 1U by 0.5u (1 / 2u ) shift<br />If you separated by a cut, you can use it as a 0.25u stagger | ![](image/b2-4.png) |
| 5/8u stagger<br />3/8u stagger    | ![](image/5-8u_stagger_3-8u_stagger.jpg) | ![](image/5-8u_stagger_3-8u_stagger.png) | 1 | Connect 1U by 0.625u ( 5 / 8u ) shift<br />If you separated by a cut, you can use it as a 3 / 8u stagger | ![](image/b2-5.png) |
| 0.75u stagger<br />3/8u stagger | ![](image/0.75u_stagger_3-8u_stagger.jpg) | ![](image/0.75u_stagger_3-8u_stagger.png) | 1 | Connect 1U by 0.75u ( 3 / 4u ) shift<br />If you separated by a cut, you can use it as a 3 / 8u stagger | ![](image/b2-6.png) |


## Wire used for wiring

If you have a grid arrangement or a close connection, it is convenient to bend the diode legs.

![bend_wire](../common/image/bend_wire.jpg)

![8](image/8.jpg)

For distant connections, use covered wires to avoid shorts.

![wiring](image/wiring.jpg)

If there is a lot of wiring, it is better to use polyurethane copper wire to reduce the thickness.

At first, we used 0.5mm polyurethane copper wire, bent it to form and then soldered it, but it takes time and effort.

![uew_wiring3](image/uew_wiring3.jpg)

Recently, 0.29mm polyurethane copper wire is used and wired in a straight line.

![uew_wiring2](image/uew_wiring2.jpg)

The following Scrapbox article is helpful for the thickness of polyurethane copper wire.

- [ポリウレタン銅線 - Self-Made Keyboards in Japan](https://scrapbox.io/self-made-kbds-ja/polyurethane copper wire)

When wiring polyurethane copper wires in a straight line, do so after soldering diodes and sockets.

## Key matrix wiring

After connecting the board with biscuits, connect the wiring of the vertical and horizontal key matrix.

In the vertical direction, make the through hole printed with COL (for example, the red circle in the figure below) conductive.

Similarly in the horizontal direction, the through hole printed with ROW (for example, the blue circle in the figure below) should be connected.

Since it has been pre-wired, it will conduct if the board is connected.

![9](image/9.jpg)

Wiring is required where the board is not connected. As mentioned earlier, it is easier to bend and solder the diode's legs.

![bend_wire](../common/image/bend_wire.jpg)

![8](image/8.jpg)

## Wiring to connect Pro Micro and key matrix

After confirming the continuity of the key matrix, connect Pro Micro to the key matrix.

When viewed from the front side of the board, the maximum is 10 keys on the side, A B C D E F G H I J from the left, the maximum is 6 keys on the vertical, and 1 2 3 4 5 6 from the top.

![6x10](image/6x10.png) When using two rotary encoders, the maximum is 6 keys on the side. When using one rotary encoder, the side is a maximum of 8 keys.

The naming method is the same as the address in Microsoft Excel.

![10](image/10.png)

![front_side_with_address](image/front_side_with_address.jpg)

Turn the board over and connect the silk printing address on the back of the Pro Micro to the corresponding row / column with polyurethane copper wire (UEW wire).

In the state of the board, the Pro Micro and the key are already wired so that they have the following addresses.

![7](image/7.jpg)

Back side (image)

![11](image/11.png)

When connecting and expanding boards, it is necessary to connect the expanded rows and columns to Pro Micro.

Any through hole can be used for the corresponding row and column at the end of the connection.

For example, any through hole in the C row (orange circle) can be connected to the Pro Micro C printed through hole (orange square).

The through hole (blue circle) on the third line can be connected to the Pro Micro 3 printed through hole (blue square).

![connect_address](/image/connect_address.jpg)

In the case of two rotary encoders, the maximum is 6 rows and 6 columns, so one column to the right (up to F column) and the bottom can be expanded to 6 rows by breaking the existing 4th row. Three boards are required for this, and for example, the red arrows are connected.

Since 6D and 6E are assigned to the push buttons of the rotary encoder, the push buttons and 6D and 6E keys have the same behavior.

![6x6wiring](image/6x6wiring.png)

When there is one rotary encoder, the maximum is 6 rows and 8 columns, so 3 columns to the right (up to H columns), the bottom can be expanded to 6 rows by breaking the existing 4th row. The number of boards required for this is four (three can be made if they are finely connected). For example, the red arrows are connected.

![6x8wiring](image/6x8wiring.png)

When there is no rotary encoder, the maximum is 6 rows and 10 columns, so 5 columns to the right (up to column J), and the bottom can be expanded to 6 rows by breaking the existing 4th row. Four boards are required for this, for example, connecting the red arrows.

![6x10wiring](image/6x10wiring.png)

## Firmware

Prepare the QMK Firmware build environment referring to the following link.

- [Getting Started-QMK Firmware] (https://docs.qmk.fm/#/newbs_getting_started)

QMK Firmware brought when building the build environment is forked [https://github.com/e3w2q/qmk_firmware/tree/su120](https://github.com/e3w2q/qmk_firmware/tree/su120). Or bring the headquarters and there [https://github.com/e3w2q/qmk_firmware/tree/su120/keyboards/handwired/su120](https://github.com/e3w2q/qmk_firmware/tree/su120/ keyboards / handwired / su120) You may copy the following:

To write the default keymap, go to the qmk_firmware folder and execute the following according to the number of rotary encoders.

- No rotary encoder
  ```
  make handwired/su120/rev1:default:avrdude  
  ```
- 2 rotary encoders (1 right hand, 1 left hand)

  ```
  make handwired/su120/rev1_2knob:default:avrdude  
  ```
- 4 rotary encoders (2 right hand, 2 left hand)

  ```
  make handwired/su120/rev1_4knob:default:avrdude  
  ```

In addition to the default keymap, a test keymap is provided.

In the test keymap, the logical arrangement of the entered key (for example, "A1" for the key in the first row and A column) is entered. Slave side inputs are prefixed with an “S”. When the rotary encoder is turned, “1ST_ENC_R”, “1ST_ENC_L”, etc. are input.

Please use it when performing the input test of all keys without using [KeyboardTester.com] (https://www.keyboardtester.com/tester.html).

- No rotary encoder
  ```
  make handwired/su120/rev1:test:avrdude  
  ```
- 2 rotary encoders (1 right hand, 1 left hand)
  ```
  make handwired/su120/rev1_2knob:test:avrdude  
  ```
- 4 rotary encoders (2 right hand, 2 left hand)
  ```
  make handwired/su120/rev1_4knob:test:avrdude  
  ```

When **Detecting USB port, reset your controller now ...** is displayed, press the reset switch next to Pro Micro to start writing.
