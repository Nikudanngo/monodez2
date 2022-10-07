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

# 10/4 のモノデザ２のまとめ

---

# 目次

- LaTex のセットアップ
- marpのススメ
- Slidevのススメ
---

# LaTex のセットアップ

- [Orver leaf](https://www.overleaf.com/)にアクセスして Google アカウントでログイン
- プロジェクトを作成
- 左の Menu から compillerを `LaTex` に変更
- プロジェクト内に `latexmkrc` というファイルを作成し以下の内容を記述

```
$latex = 'uplatex';
$dvipdf = 'dvipdfmx %O -o %D %S';
$ENV{OPENTYPEFONTS}='/usr/share/fonts//:';
$ENV{TTFONTS}='/usr/share/fonts//:';
```

- `\begin{document}`に色々書いてく
---

# LaTexの構文

## リスト

<div class="grid grid-cols-2 gap-2">
<div>

```latex
\begin{itemize}
    \item リスト１
    \item リスト２
    \begin{itemize}
      \item さらにリスト1
    \end{itemize}
    \item $ \frac{1}{2} x^2 + x = -4 $ワンラインで数式を書く

以下にテイラー展開の式を示す.
\end{itemize}
\begin{eqnarray}
    f(x) &=& \sum \limits_{ k = 0 }^ { \infty }f ^ {(k)}(0) \frac{ x ^ k } { k! } \\
         &=& f(0) 
            + f'(0)x 
            + \frac{f''(0)}{2!}x^2 
            + \cdots
\end{eqnarray}
```

</div>
<div>

- リスト１
- リスト２
  1. さらにリスト1
- $\frac{1}{2}x^2 + x = -4$

以下にテイラー展開の式を示す.
$$
\begin{align}
f(x) &= \sum \limits_{ k = 0 }^ { \infty }f ^ {(k)}(0) \frac{ x ^ k } { k! } \\
  &= f(0) + f'(0)x + \frac{f''(0)}{2!}x^2 + \cdots \\
\end{align}   
$$

</div>
</div>
---

# marpのススメ:[https://marp.app/](https://marp.app/)

  - マークダウンでスライドを作成できるtool
  ```md
  # クソでかタイトル
  ##　そこそこのタイトル
  - リスト
    - ネストしたリスト

  ```
  # クソでかタイトル

  ##　そこそこのタイトル

  - リスト

---

# ちな私はslidevを使ってます

<h2 class="absolute top-[50%] left-{50%} text-center text-blue-300">
  Slidevもmarpもマークダウンでスライドを作成できるtool
</h2>

---

# Slidevとmarpの比較

## 共通点
- LaTexが書ける
$\sqrt{3x-1}+(1+x)^2$

- 

---

# Slidevとmarpの比較

## Slidevが優れている点
- デフォルトでTailwindCSS(Windi CSS)が使える!

```html
<h2 class="absolute top-[50%] left-{50%} text-center text-blue-300">
  Slidevもmarpもマークダウンでスライドを作成できるtool
</h2>
```
<v-clicks>

- アニメーションが豊富(marpと比べて)
- SPAビルドできる！
- プレゼン中にテーマを変更できる
- 録画、プレゼンモード、まるでパワポ！

</v-clicks>