## 方程组的几何表示

从解线性方程组开始
$$
x + 2y + z =2\\
3x + 8y + z =12\\
0x + 4y + z = 2\\
$$
$可将线性方程组理解为 Ax=b$

$A为x,y,z系数所构成的矩阵$
$$
\begin{bmatrix}
1 & 2 & 1 \\
3 & 8 & 1\\
0 & 4 & 1
\end{bmatrix}
$$


$x 为自变量所构成的向量$ 
$$
\begin{bmatrix}
x \\
y\\
z\\
\end{bmatrix}
$$
$b为常数向量$
$$
\begin{bmatrix}
2\\
12\\
2\\
\end{bmatrix}
$$
$则Ax = b 等价于$
$$
\begin{bmatrix}
1 & 2 & 1 \\
3 & 8 & 1\\
0 & 4 & 1
\end{bmatrix}
\cdot
\begin{bmatrix}
x \\
y\\
z\\
\end{bmatrix}
= \begin{bmatrix}
2\\
12\\
2\\
\end{bmatrix}
$$
$从行向量的角度出发  x y z的解即是三个平面的交点tuple(x,y,z)$

就是从
$$
\begin{bmatrix}
1&2&1
\end{bmatrix}
\cdot \begin{bmatrix}
x\\
y\\
z\\
\end{bmatrix}
$$
<img src="C:\Users\CC\AppData\Roaming\Typora\typora-user-images\image-20240802122651307.png" width="300" height="200">

线性组合:将变量前的系数看成列向量相加 解的是向量增长\缩短的倍数
$$
\begin{bmatrix}
1\\
3\\
0
\end{bmatrix} \cdot x
+
\begin{bmatrix}
2\\
8\\
4
\end{bmatrix} \cdot y
+
\begin{bmatrix}
1\\
1\\
1
\end{bmatrix} \cdot z
=
\begin{bmatrix}
2\\
12\\
2
\end{bmatrix}
$$
<img src="C:\Users\CC\AppData\Roaming\Typora\typora-user-images\image-20240802123746291.png" width="300" height="200">

向量空间: Ax 所构成的集合

## 消元法

所有计算机(matlab)解线性方程组都是用消元法
$$
x + 2y + z =2\\
3x + 8y + z =12\\
0x + 4y + z = 2\\
$$
消元法即是找到通过矩阵的转换主元
$$
\begin{bmatrix}
1 & 2 & 1 \\
3 & 8 & 1\\
0 & 4 & 1\\
\end{bmatrix}
\overset{R_2 \rightarrow R_2 - 3R_1}{\longrightarrow}
\begin{bmatrix}
1 & 2 & 1 \\
0 & 2 & -2\\
0 & 4 & 1
\end{bmatrix}
\overset{R3\rightarrow R3-2R2}{\longrightarrow}
\begin{bmatrix}
1 & 2 & 1 \\
0 & 2 & -2\\
0 & 0 & 5
\end{bmatrix}
$$
主元通过行列的加减 使得他的下方全部为0 同时主元不唯一

$在这里 对角线的1\  2\  3 都是矩阵的主元$

再添加常量向量 变成增广矩阵 注意 需要同时变换向量常数
$$
\begin{bmatrix}
1 & 2 & 1 & 2\\
0 & 2 & -2 & 6\\
0 & 0 & 5 & -4
\end{bmatrix}
$$
用方程组表示 即
$$
x + 2y + z =2\\
2y  -2z =6\\
5z = -4\\
$$


## 矩阵乘法

$求解矩阵C \ AB =C$
$$
\begin{bmatrix}
a_{11}& \cdots & a_{1n} \\
\vdots  & \ddots & \vdots \\
a_{m1} & \cdots & a_{mn}
\end{bmatrix}
\cdot
\begin{bmatrix}
b_{11}& \cdots & b_{1p} \\
\vdots  & \ddots & \vdots \\
b_{n1} & \cdots & b_{np}
\end{bmatrix}
 = \begin{bmatrix}
c_{11}& \cdots & c_{1p} \\
\vdots  & \ddots & \vdots \\
c_{n1} & \cdots & c_{np}
\end{bmatrix}
$$
$方法1: C_{ij} = \sum_{r =1}^{n}a_{ir}*b_{rj}$

$方法2 \ 线性组合:(直观:列列一组组合)$

$$
由线性方程组的线性组合可以推想 \\
$$

$$
\begin{bmatrix}
\begin{bmatrix}
a_{11}& \cdots & a_{1n} \\
\vdots  & \ddots & \vdots \\
a_{m1} & \cdots & a_{mn}
\end{bmatrix} \cdot
\begin{bmatrix}
b_{11} \\ 
\vdots  \\
b_{n1}
\end{bmatrix}
\cdots
\begin{bmatrix}
a_{11}& \cdots & a_{1n} \\
\vdots  & \ddots & \vdots \\
a_{m1} & \cdots & a_{mn}
\end{bmatrix} \cdot
\begin{bmatrix}
b_{1p}\\
\vdots\\
b_{np}
\end{bmatrix}
\end{bmatrix}
$$

$$
\begin{bmatrix}
a_{11}& \cdots & a_{1n} \\
\vdots  & \ddots & \vdots \\
a_{m1} & \cdots & a_{mn}
\end{bmatrix}
==\begin{bmatrix}
A_{1}&\cdots A_{n}
\end{bmatrix}
$$

$$
A_{i} =
\begin{bmatrix}
a_{11}\\
a_{21}\\
\vdots \\
a_{m1}
\end{bmatrix}
$$

$称此为a的线性组合$
$$
\begin{bmatrix}
\begin{bmatrix}
a_{11}& \cdots & a_{1n} \\
\end{bmatrix}\cdot
\begin{bmatrix}
b_{11}& \cdots & b_{1p} \\
\vdots  & \ddots & \vdots \\
b_{n1} & \cdots & b_{np}
\end{bmatrix}
\\
\vdots \\
\begin{bmatrix}
a_{m1}& \cdots & a_{mn} \\
\end{bmatrix}\cdot
\begin{bmatrix}
b_{11}& \cdots & b_{1p} \\
\vdots  & \ddots & \vdots \\
b_{n1} & \cdots & b_{np}
\end{bmatrix}
\end{bmatrix}
$$

$方法3 :行列组合\ B行乘A列$


$$
\begin{bmatrix}
a_{11} \\
\vdots  \\
a_{m1}
\end{bmatrix}
\cdot
\begin{bmatrix}
b_{11} \cdots b_{1p}
\end{bmatrix} = 
\begin{bmatrix}
a_{11}b_{11}&\cdots &a_{11}b_{1p}\\
a_{21}b_{11}&... &a_{21}b_{1p}\\
\vdots &\ddots & \vdots \\
a_{m1}b_{11}&\cdots &a_{m1}b_{1p}
\end{bmatrix}
$$
可见 C中每个向量都是行向量的倍数
$$

$$


## 逆矩阵

如果存在向量x使得Ax = 0 且x不为零向量 则A矩阵不是可逆的

等价主元数量为方阵的维数

例如:
$$
\begin{bmatrix}
1 & 3\\
2& 6\\
\end{bmatrix}
\cdot
\begin{bmatrix}
x\\
y
\end{bmatrix}
=\begin{bmatrix}
0\\
0\\
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 \\
2\\
\end{bmatrix}
\cdot x+ \begin{bmatrix}
2 \\
6\\
\end{bmatrix}
\cdot y = 0
$$

一眼盯帧 
$$
\begin{bmatrix}
-3 \\
1\\
\end{bmatrix}
$$
则该向量不是可逆的

  $AA^{-1}=I=A^{-1}A$

$A^{-1}是由一系列初等矩阵相乘得到的$

逆矩阵的性质:

1. $(AB)^{-1} =B^{-1}A^{-1} $

     $  (AB)^{-1}AB = I = AB(AB)^{-1} $

$B^{-1}A^{-1}AB = I$

$2.(A^{-1})^{-1} = A $

$3.(A^T)^{-1} = (A^{-1})^{T}$
$$
(AA^{-1})
$$


### 求解逆矩阵

####     待定系数法

$$
\begin{bmatrix}
1 & 3\\
2& 6\\
\end{bmatrix}
\cdot
\begin{bmatrix}
a &b\\
c&d
\end{bmatrix}
=\begin{bmatrix}
1&0\\
0&1\\
\end{bmatrix}
$$

$$
\begin{bmatrix}
a+3c&b+3d\\
2a+6c&2b+6d
\end{bmatrix}
=\begin{bmatrix}
1&0\\
0&1\\
\end{bmatrix}
$$

####     高斯-约尔当消去法


$$
E\begin{bmatrix} A & I \end{bmatrix} \rightarrow \begin{bmatrix} I & A^{-1} \end{bmatrix}
$$
$可知 E=A^{-1}$

## 初等矩阵

单位阵进行初等变换

1. 行交换
2. 行的数乘
3. 行相加

## 置换矩阵:?

  $阶数为n的单位矩阵 他的种类有n!(Permutation)$

  是一种特殊的初等矩阵
$$
\begin{bmatrix}
0&0&1\\
0&1&0\\
1&0&0
\end{bmatrix}
$$
性质:

1. $P^T = P^{-1}$
   $$
   C_{ii} = P_{ij}\cdot P_{ji} \\
   P_{ij} = P_{ji}
   $$

2. 

## 转置矩阵

定义：$(A^T)_{ij} = A_{ji}$

$1.(AB)^T = B^TA^T$



$2.(\lambda A)^{-1} = 1 \backslash \lambda  A^{-1} $

$ \lambda A B = I$

$B = 1/ \lambda \ A^{-1}$

$3.(A^T)^T=A$

4.

### 可逆矩阵A = LU 分解:?

如何将 A 分解为上三角矩阵(upper triangular matrix)和下三角矩阵(lower triangular matrix)的乘积？

$可以知道  矩阵A 可以通过变换变成上三角矩阵$

$E^{-1}EA = E^{-1}U \\ 其中 E是通过一系列初等矩阵的乘积所得到的$



<img src="C:\Users\CC\AppData\Roaming\Typora\typora-user-images\image-20240803104723357.png" width="1000" height="200">

初等矩阵的逆矩阵即是对初等矩阵的作用的"消去"
$$
(E_{21})^{-1}=
\begin{bmatrix}
1 & 0&0\\
2&1&0\\
0&0&1
\end{bmatrix}\ \
(E_{32})^{-1}=
\begin{bmatrix}
1 & 0&0\\
0&1&0\\
0&5&1
\end{bmatrix}\ \
$$

$$
A = (E_{21})^{-1}I(E_{32})^{-1}U
\\
L =\begin{bmatrix}
1 & 0&0\\
2&1&0\\
0&5&1
\end{bmatrix}
$$

可见 变换矩阵的逆位下三角矩阵

## 向量空间

  **一个特殊的集合 里面元素 满足数乘 线性组合 封闭性 **

  **必须有零向量 任何线性组合都需要经过存在0的数乘**

  向量组的线性相关和线性无关是在描述什么性质？

  存在k不全为的组合 即是线性无关

  $k_1a_1+\cdots+k_na_n = 0$

  **等价于任何一个向量不能用其他向量的线性组合表示**

<img src="C:\Users\CC\AppData\Roaming\Typora\typora-user-images\image-20240803152514749.png" width="300" height="200">

### 子空间

####     列空间

$矩阵A_{mn}的列空间是在R^{m}中的子空间$
$$
\begin{bmatrix}
1&1&1\\
3&4&1\\
2&3&1\\
5&6&1
\end{bmatrix}
$$


$issue1： 列空间是否是R^4的真子集？ 也就是说 展开的空间是否能铺满R^4$

$回顾之前的内容 容易看出 Ax =b 中A的线性组合就是列空间$
$$
\begin{bmatrix}
1&1&1\\
3&4&1\\
2&3&1\\
5&6&1
\end{bmatrix}
\cdot
\begin{bmatrix}
x_{1}\\
x_{2}\\
x_{3}
\end{bmatrix}
=
 b
$$
  $Ax=b$

$显然 3个四维向量的线性组合无法铺满R^4$

$推论：当n==m时 列空间等于R^m \ n>m时 可能无解(方程组线性相关)n<m时 无法铺满 需要严格证明$

$issue2:什么能使b有解?$

符合A的线性组合

###   零空间

  经过原点时 数乘组成的向量构成的列向量

​     $Ax = 0$
