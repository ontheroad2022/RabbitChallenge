


# 深層学習 day２ Section１：勾配消失問題

## 確認テスト１

連鎖率の原理を使い、dz/dx を求めよ。

<p align="center">
    <img src="https://latex.codecogs.com/svg.latex?\begin{align*}z&=t^2\\t&=x+y\\\end{align*}"> 
</p>

解答：

<p align="center">
    <img src="https://github.com/ontheroad2021/RabbitChallenge/blob/main/images/3_2_1_2_Review_Test_01.png"> 
</p>


## 確認テスト２

シグモイド関数を微分した時、入力値が０の時に最大値をとる。その値として正しいものを選択肢から選べ。

<p align="center">(1) 0.15</p>
<p align="center">(2) 0.25</p>
<p align="center">(3) 0.35</p>
<p align="center">(4) 0.45</p>

解答：

正解は (2) 0.25

<p align="center">
    <img src="https://raw.githubusercontent.com/ontheroad2021/RabbitChallenge/main/images/3_2_1_2_Review_Test_02.png"> 
</p>

```
import numpy as np
import matplotlib.pyplot as plt

x = np.arange(-10, 10, 0.1)
def sigmoid(x):
  return 1/(1+np.exp(-x))

fig, axes = plt.subplots(nrows=1, ncols=2, figsize=(10, 4))
axes[0].plot(x, sigmoid(x), label="sigmoid")
axes[0].set_title('sigmoid')

def sigmoid_d(x):
  return (1-sigmoid(x)) * sigmoid(x)

axes[1].plot(x, sigmoid_d(x))
axes[1].set_title('derivative of sigmoid')
plt.show()
```

## 確認テスト３

重みの初期値に０を設定すると、どのような問題が発生するか。簡潔に説明せよ。

解答：

重みを０で初期化すると正しい学習が行えない。
全ての重みの値が均一に更新されるため、多数の重みを持つ意味がなくなる。

## 確認テスト４

一般的に考えられるバッチ正規化の効果を２点挙げよ。

解答：

1. バッチ正規化を行う事で、ニューラルネットワークの学習中に、中間層の重みの更新が安定化されます。その結果として学習がスピードアップします。
2. 過学習を押さえる事ができます。バッチ正規化はミニバッチの単位でデータの分布を正規化します。学習データの極端なばらつきが抑えられます。この状態でニューラルネットワークを学習できますので、過学習が起きにくく調整が行われていきます。

