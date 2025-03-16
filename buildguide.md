# minimum TL Split Keyboard 16mm Low Rev1ビルドガイド

minimum TL Split Keyboard 16mm Low Rev1は、TRON最小化配列のロープロファイルキーボードです。
TRON最小化配列の16mmピッチを、ロープロファイルキーで実現しています。
ロープロファイル版なので注意してください。

## 説明
minimum TL Split Keyboard 16mm Low Rev1は、PCBが左右違います。4.7kΩ抵抗（R1,R2）がある方が左です。
基本的に、左側にUSBケーブルを接続するようにしています。

PCBには、表面と裏面があります。"minimum TL Split Keyboard 16mm Low"と記載がある方が、裏面です。

## 組み立て
### PCBへパーツ半田付け

- ダイオードを、左右PCB裏面に36カ所実装します。

ダイオードを、左右PCB裏面に実装します。ダイオードは極性があるので、ダイオードのカソード（シルク印刷で白い線が入っている方）をPCB裏面のシルク印刷でK（カソード）と記載されている方になるよう、左右それぞれ36カ所半田付けしていきます。

※表面実装ダイオードの白い線は見づらいので、見えにくい場合はスマホカメラで撮影すると見やすいです。

- 4.7kΩ抵抗を左側PCB表面に2カ所実装します。

4.7kΩ抵抗を、左側PCB表面のみに実装します。極性は無いので、どちらでもかまいません。

- TRRSジャックを、左右PCB表面に実装します。

TRRSジャックを、左右PCB表面に実装します。左右PCBに、それぞれ半田付けしてください。

### Pro Microへコンスルー半田付け

遊舎工房で購入すれば、コンスルー付きが買えます。

PCBから外した状態で、部品（USBコネクタなど）が実装されている面にコンスルーを載せて、半田付けします。

できたら、左右PCBの表面にはめ込みます。基板の外側（左側PCBは右、右側PCBは左）にUSBコネクタが来るようにはめます。

### キースイッチ半田付け

トッププレートとPCBの間に短い方のスペーサー(0.5mm)をはさみ、左右それぞれ7カ所を長い方のねじ（5mm）でネジ止めします。ねじ頭が上側に来るようにして、PCBの下には長い方のスペーサー(3mm)で止めてください。
キースイッチをトッププレートの上からトッププレート・PCBにはめ込み、固定します。ここでキーが浮かないよう、しっかりトッププレートにはめ込んで、半田付けしてください。

![トッププレート](./image/topplate.jpg)

![トッププレート2](./image/topplate2.jpg)

キースイッチは、親指扇形部分含め72カ所半田付けします。

※注意点:親指キー部分は、キースイッチによっては干渉してしまう場合があります。その場合、干渉するキーの出っ張り部分をニッパ等で切り落としてください。


## ProMicroにファームウェア書き込み
ファームウェアは、CherryMX版とロープロファイル版で共通です。

[QMK Toolbox](https://github.com/qmk/qmk_toolbox) で、ファームウェア（hexファイル）をProMicroに書き込む必要があります。

[QMK Toolbox](https://github.com/qmk/qmk_toolbox) のインストール・使い方については、サリチル酸さんが書かれた[（初心者編）自作キーボードにファームウェアを書き込む](https://salicylic-acid3.hatenablog.com/entry/qmk-toolbox) が分かりやすいです。

minimum TL Split Keyboardのファームウエアは、 [satromi_mintlsplit_default.hex](https://github.com/satromi/minimumtlsplit16_rev1/blob/main/hex/satromi_mintlsplit_default.hex) をダウンロードしてQMK Toolboxで書き込みます。

ファームウェアは、左右のProMicroそれぞれに書き込む必要があります。

Dvorak配列のファームも公開しています。[satromi_mintlsplit_dvorak.hex](https://github.com/satromi/minimumtlsplit16_rev1/blob/main/hex/satromi_mintlsplit_dvorak.hex) をダウンロードして、QMK Toolboxで書き込みます。

他のキーマップに変更したい場合は、VIA対応ファームウェアも準備しています。[satromi_mintlsplit_via.hex](https://github.com/satromi/minimumtlsplit16_rev1/blob/main/hex/satromi_mintlsplit_via.hex) をダウンロードして、QMK Toolboxで書き込みます。

VIA対応ファームウェアの場合、Webサイトからキーマップを変更できる [REMAP](https://remap-keys.app/)  も利用できます。
[REMAPのminimum TL Split Keyboardページ](https://remap-keys.app/catalog/6Lzaoh8tO5NVf4gDDHTs)  から書き換えてみてください。

## 動作確認

左右のキーボードをTRRSケーブルで繋いだら、USBケーブルでPCと接続し、動作確認してください。

## ボトムケース取り付け

動作確認して問題なければ、ボトムプレートを取り付けます。左右それぞれ7カ所を短い方のねじ（3mm）でネジ止めします。ねじ頭が下側（ボトムケース側）に来るようにしてください。

![ボトムプレート取り付け](./image/bottomplate.jpg)

最後に、クッションゴムを取り付けます。左右それぞれ6カ所貼り付けます。お好きな位置に取り付けてください。
