# ベクトル場の可視化
まず最初にベクトル場の可視化について、簡単に例を挙げながら説明します.
2次元ベクトル場を
s$$\vec{F} = \left( F_x(x, y), F_y(x, y) \right)$$
について、
$$F_x = y, F_y = -x$$
とすると、以下のコードのように書けます。
```python
import numpy as np
import matplotlib.pyplot as plt

plt.figure()

LX=2.2
LY=2.2

gridwidth=0.05
x, y= np.meshgrid(np.arange(-LX, LX, gridwidth), np.arange(-LY, LY,gridwidth)) 

Fx = y
Fy = -x

# ベクトル場をプロット
plt.streamplot(x,y,Fx,Fy)

# x,yの描画範囲
plt.xlim([-LX,LX])
plt.ylim([-LY,LY])

# グラフ描画
plt.axes().set_aspect('equal')
plt.grid()
plt.draw()
plt.show()
```
![](https://storage.googleapis.com/zenn-user-upload/8x5d7n6d2vrephpt6b9qb4lphyhr)

今回はstreamplotで表示しましたが、他にもquiverなど様々な表示方法があります。
また、`numpy.meshgrid()`は１次元配列を受け取って格子点を生成する関数です。数値計算においては、平面上あるいは空間内の各点に定義された量を表す時、とても便利です。

# 電場に関するクーロンの法則
では、上記の方法を使って点電荷が作る静電場を可視化してみたいと思います。<br>
まず、原点にある点電荷を点として表示すると次のようになります。
```python
import numpy as np
import matplotlib.pyplot as plt

plt.figure()

#グラフ範囲を指定
LX, LY = 2.2, 2.2

# 点電荷の座標(x, y)=(0,0)を指定
x_0, y_0 =0, 0
plt.plot()


```