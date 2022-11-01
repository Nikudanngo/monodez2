# 10/25 ものデザまとめ

## ニューラルネットワーク入門

## じゃんけんを作る(後出し)

[1,0,0] がグー、[0,1,0] がチョキ、[0,0,1] がパー

- 学習なしでランダムにじゃんけんをする

```python
import random

w = [random.random(), random.random() ,random.random()]

def forward(x):
    # u = w[0] * x[0] + w[1] * x[1] + w[2] * x[2]
    u = 0
    # for i in range(len(x)):
    #     u += w[i] * x[i]
    for (wi, xi) in zip(w, x):
        u += wi * xi
    # if で書く
    if u < 0 : y = 0
    else: y = u

    # 三項演算子
    y = 0 if u < 0 else u
    return y

print(forward([1, 0, 0]))
print(forward([0, 1, 0]))
print(forward([0, 0, 1]))
```

- 学習ありでじゃんけんをする

## 学習とは間違えた結果を評価すること

以下にニューラルネットワークの式を示す
$
\begin{align}
y &= f(u) \\
u &= w_1 x_1 + w_2 x_2 + w_3 x_3 \\
f(u) &= 
\begin{cases}
0 & (u < 0) \\
u & (u \geq 0)
\end{cases}
\end{align}
$

```python
import random

w = [random.random(), random.random() ,random.random()]

def forward(x):
    # u = w[0] * x[0] + w[1] * x[1] + w[2] * x[2]
    u = 0
    # for i in range(len(x)):
    #     u += w[i] * x[i]
    for (wi, xi) in zip(w, x):
        u += wi * xi
    # if で書く
    if u < 0 : y = 0
    else: y = u

    # 三項演算子
    y = 0 if u < 0 else u
    return y

# 0.15124689573846695
# 0.4494436318438453
# 0.15904177654762086

def update(x,t):
    y = forward(x)
    leaningRate =  0.1
    dydu = 0 if y <= 0 else 1 # 不動小数点を0で比較するのは危険なので<=を使う
    for i in range(len(w)):
        w[i] += -leaningRate * (y - t) * dydu * x[i]

print(forward([1, 0, 0]))
print(forward([0, 1, 0]))
print(forward([0, 0, 1]))

print('----------------------')

for _ in range(100):
    update([1, 0, 0], 1)
    update([0, 1, 0], 0)
    update([0, 0, 1], 0.5)

print(forward([1, 0, 0]))
print(forward([0, 1, 0]))
print(forward([0, 0, 1]))

```

## バックプロパゲーション

逆方向の計算
