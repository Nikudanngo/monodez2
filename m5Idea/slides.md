---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: "text-center"
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
---

# M5Stack を用いた制作物の案

---

# 目次

<!-- - M5Stack でできること -->

- アイディア紹介
- どうやって作るか

---

<!-- # M5Stack でできること

公式サイトのドキュメントによると
https://docs.m5stack.com/en/core/core2

<div class="grid grid-cols-[50%,50%]">
<div>

- ESP32 → Wi-Fi モジュールあり
- 16M フラッシュ、8M PSRAM
- スピーカー
- 電源インジケーターランプ
- 振動モーター
- RTC
- I2S アンプ

</div>
<div>

- 静電容量式タッチスクリーン
- 電源ボタン、リセット ボタン
- TF カードスロット (最大サイズ 16G)
- リチウム電池
- 加速度センサー
- マイク
- M-Bus ソケット & ピン

</div>
</div>

<span v-click class="text-blue-400 text-4xl flex justify-end mt-30">性能が期待できないスマホ...</span>
-->

# アイディア紹介

## スマートミラー

<p v-click class="flex justify-end">
endo > 鏡よ鏡...今日の天気はどんな感じ？<br>
M5Stack > 今日はめっちゃ寒いです(ディスプレイ) 
</p>

<p v-click>

## 概要

1. ディスプレイにマジックミラーフィルムを被せて、普段は時計付き鏡として利用できる。

1. 何かしらの<span class="text-pink-400">トリガー</span>を<span class="text-blue-400">受け取る</span>と天気やニュースなどをディスプレイに表示する。(黒背景に白文字)

1. まるで魔法の鏡のような体験を提供するスマートデバイス。

</p>

---

# どうやって作るか

## マジックミラーとは

<div v-click class="grid grid-cols-[50%,50%] gap-4">
  <div>
    <img class="w-full" src="https://www-e-kagami-com-w.imgix.net/images/column/18/8480d71d-157c-46e2-be64-5f9f69c2380b-1594799585691.jpg?auto=format&fit=max&w=1200&v=1671498832"/>
    参照:https://www.e-kagami.com/column.html?no=18
  </div>

  <div>

### 暗いところから明るいところは見れるけど、逆は見えないようなガラス

    つまり、フィルムの向こう側を黒色の布とかディスプレイで密着させると、
    実質的に鏡になる。

  </div>
</div>

---

# どうやって作るか

## イメージ動画

https://twitter.com/onikumaruBuu/status/1347522773120286720
<video controls>
<Tweet class="h-[50%]" id="1347522773120286720" />
</video>

---

# どうやって作るか

## 懸念点

- ### 何をトリガーとするか
  音声認識？Get 通信？
- ### スマート？ミラー
  AI 的な要素が欲しい、音声認識とか画像認識
