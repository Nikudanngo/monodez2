# 10/25 ものデザまとめ

## 前回の回帰予測をグラフにしてみよう

```python
from sklearn.linear_model import LinearRegression
import matplotlib.pyplot as plt

x = [[1], [2], [3]]
y= [[-1], [2], [5]]

model = LinearRegression() # 学習モデルのインスタンスを生成
model.fit(x, y) # 学習モデルをデータをfit

print(model.predict([[4], [5], [6]])) # 予測

# ここを追加
plt.scatter(x, y)
plt.plot(x, model.predict(x))
plt.show()
```

## データ入力には csv ファイルを使うのが便利

| 名前 | 年齢 | 身長 | 体重 |
| :--- | :--- | :--- | :--- |
| 山田 | 20   | 170  | 60   |
| 田中 | 30   | 180  | 70   |
| 佐藤 | 40   | 160  | 50   |

```csv
"名前","年齢","身長","体重"
"山田",20,170,60
"田中",30,180,70
"佐藤",40,160,50
```

## csv の扱い方

- 標準の csv モジュールを使う

```python
import csv

data = []
with open('humanData.csv', 'r') as f:
    reader = csv.reader(f)
    for row in reader:
        data.append(row)

print(data)

```

- pandas を使う

`pip install pandas`

```python
import pandas as pd

df = pd.read_csv('humanData.csv')
print(df)

```

### warning でる

```
UserWarning: Could not import the lzma module. Your installed Python is incomplete. Attempting to use lzma compression will result in a RuntimeError.
```

### 解決方法

https://qiita.com/siruku6/items/515f3e69b90dd78ba67d

m1 mac なら`brew install xz`してから Python を再度インストールすると治るらしい

## Numpy でデータを扱う

### Numpy とは

Python でベクトルや行列を扱うためのライブラリ
例えば,

```python
data = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
data + 1
print(data)　# SyntaxError: invalid character in identifier
```

みたいなことはできない.
でも NumPy を使えばできる

```python
import numpy as np

Data1 = np.asarray([90, 80, 70, 60, 50, 40, 30, 20, 10, 0])
Data2 = np.asarray([60, 50, 40, 30, 20, 10, 0, 90, 80, 70])

print(Data1 + Data2) # [150 130 110  90  70  50  30 110  90  70]
print(Data1 * 3) # [270 240 210 180 150 120  90  60  30   0]
print(Data1 + 10) # [100  90  80  70  60  50  40  30  20  10]
```

## 機械学習とは

- 回帰分析
- 分類
- ニューラルネットワーク

## ニューラルネットワークとは

神経細胞のようなもの

式

$
y = f(x) \\
x = \Sigma_i w_i x_i + b
$

- w: 重み
- b: バイアス
- x: 入力
- y: 出力
