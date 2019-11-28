---
title: Markdown 中 LaTex 数学公式命令
layout: post
categories:
- 通识
tags: 通识
---

- ## 0 引言

  在学习理工科知识或者是目前火热的深度学习等过程中，会涉及到大量的数学公式，并且考虑到准备以 Markdown 为主要做笔记方式，因此，在这里对 Markdown 中 LaTex 数学公式命令做一个汇总。

  > **重要说明:** 本文所有的公式在简书环境下试验可行，示例中的 `$ formula $` 是生成公式的 LaTex 语法。

  ------

  ## 1 Markdown 中使用 LaTex 基础语法

  LaTeX 公式有两种，一种是用在正文中的，一种是单独显示的。

  - 行内公式：用 `$ formula $` 表示，例如: `$ \sum_{i=0}^{n} i^2 $` 表示 ![\sum_{i=0}^{n} i^2](https://math.jianshu.com/math?formula=%5Csum_%7Bi%3D0%7D%5E%7Bn%7D%20i%5E2)
  - 独立公式：用 `$$ formula $$` 表示，例如: `$$ \sum_{i=0}^{n} i^2 $$` 表示 ![\sum_{i=0}^{n} i^2](https://math.jianshu.com/math?formula=%5Csum_%7Bi%3D0%7D%5E%7Bn%7D%20i%5E2)

  > **Tips:** 以下几个字符 # $ % & ~ _ ^ \ { } 有特殊意义，当表示这些字符时，需要转义，即在每个字符前加上 \ ，对于 \ ，可使用 `$ \backslash $` 命令得到 ![\backslash](https://math.jianshu.com/math?formula=%5Cbackslash)。

  ------

  ## 2 常用数学表达命令

  #### 2.1 上下标表示

  - 上标: 用 `^` 后的内容表示上标，例如: `$ x^{(i)} $` , `$ y^{(i)} $` 表示 ![x^{(i)}](https://math.jianshu.com/math?formula=x%5E%7B(i)%7D) , ![y^{(i)}](https://math.jianshu.com/math?formula=y%5E%7B(i)%7D)
  - 下标: 用 `_` 后的内容表示上标，例如: `$ x_{(i)} $` , `$ y_{(i)} $` 表示 ![x_{(i)}](https://math.jianshu.com/math?formula=x_%7B(i)%7D) , ![y_{(i)}](https://math.jianshu.com/math?formula=y_%7B(i)%7D)
  - 上下标混用，例如: `$ x_1^2 $` , `$ x^{y^{z}} $` , `$ x^{y_z} $` 表示 ![x_1^2](https://math.jianshu.com/math?formula=x_1%5E2), ![x^{y^{z}}](https://math.jianshu.com/math?formula=x%5E%7By%5E%7Bz%7D%7D), ![x^{y_z}](https://math.jianshu.com/math?formula=x%5E%7By_z%7D)

  当角标位置看起来不明显时，可以强制改变角标层次或者在角标前面加上改变其大小的命令 (如 `\tiny` , `\small` , `\normalsize` , `\large` , `\Large` , `\LARGE` )，例如:
   `$ y_N $` , `$ y_{_N} $` , `$ y_{\small{N}} $` 表示 ![y_N](https://math.jianshu.com/math?formula=y_N), ![y_{_N}](https://math.jianshu.com/math?formula=y_%7B_N%7D), ![y_{\small{N}}](https://math.jianshu.com/math?formula=y_%7B%5Csmall%7BN%7D%7D)

  并且支持中文作为角标 (仅在简书 Markdown 环境下试验过)，例如:
   `$ {\partial f}_{\tiny 极大值} $` , `$ {\partial f}_{\large 极大值} $` 表示 ![{\partial f}_{\tiny 极大值}](https://math.jianshu.com/math?formula=%7B%5Cpartial%20f%7D_%7B%5Ctiny%20%E6%9E%81%E5%A4%A7%E5%80%BC%7D), ![{\partial f}_{\large 极大值}](https://math.jianshu.com/math?formula=%7B%5Cpartial%20f%7D_%7B%5Clarge%20%E6%9E%81%E5%A4%A7%E5%80%BC%7D)

  #### 2.2 分数形式

  分式命令:

  - `$ \dfrac{}{} $` , 表示该分式是以 displaystyle 设置的，例如: `$ \dfrac{y}{x} $` 表示 ![\dfrac{y}{x}](https://math.jianshu.com/math?formula=%5Cdfrac%7By%7D%7Bx%7D)
  - `$ \tfrac{}{} $` , 表示该分式是以 textstyle 设置的，例如: `$ \tfrac{y}{x} $` 表示 ![\tfrac{y}{x}](https://math.jianshu.com/math?formula=%5Ctfrac%7By%7D%7Bx%7D)
  - `$ \frac{}{} $` , 表示该分式根据环境设置样式，例如: `$ \frac{y}{x} $` 表示 ![\frac{y}{x}](https://math.jianshu.com/math?formula=%5Cfrac%7By%7D%7Bx%7D)
  - `$ {} \over {} $` , 分式的另一种表达方式，一般不建议使用 (但是真的很方便啊)，例如:
     `$ y \over x $` 表示 ![y \over x](https://math.jianshu.com/math?formula=y%20%5Cover%20x)

  其具体区别请参考：
   [What is the difference between \dfrac and \frac?](https://tex.stackexchange.com/questions/135389/what-is-the-difference-between-dfrac-and-frac)
   [What is the difference between \over and \frac?](https://tex.stackexchange.com/questions/73822/what-is-the-difference-between-over-and-frac)

  连分式 `$ x_0+\frac{1}{x_1+\frac{1}{x_2+\frac{1}{x_3+\frac{1}{x_4}}}} $` 表示
   ![x_0+\frac{1}{x_1+\frac{1}{x_2+\frac{1}{x_3+\frac{1}{x_4}}}}](https://math.jianshu.com/math?formula=x_0%2B%5Cfrac%7B1%7D%7Bx_1%2B%5Cfrac%7B1%7D%7Bx_2%2B%5Cfrac%7B1%7D%7Bx_3%2B%5Cfrac%7B1%7D%7Bx_4%7D%7D%7D%7D)

  可以通过强制改变字体大小使得分子分母字体大小一致，例如:
   `$ \newcommand{\FS}[2]{\dfrac{#1}{#2}}x_0+\FS{1}{x_1+\FS{1}{x_2+\FS{1}{x_3+\FS{1}{x_4}}}} $` 表示
   ![\newcommand{\FS}[2]{\dfrac{#1}{#2}}x_0+\FS{1}{x_1+\FS{1}{x_2+\FS{1}{x_3+\FS{1}{x_4}}}}](https://math.jianshu.com/math?formula=%5Cnewcommand%7B%5CFS%7D%5B2%5D%7B%5Cdfrac%7B%231%7D%7B%232%7D%7Dx_0%2B%5CFS%7B1%7D%7Bx_1%2B%5CFS%7B1%7D%7Bx_2%2B%5CFS%7B1%7D%7Bx_3%2B%5CFS%7B1%7D%7Bx_4%7D%7D%7D%7D)

  其中第一行命令定义了一个新的分式命令，规定每个调用该命令的分式都按 `\displaystyle` 的格式显示分式，等价于 `$ x_0+\dfrac{1}{x_1+\dfrac{1}{x_2+\dfrac{1}{x_3+\dfrac{1}{x_4}}}} $`

  分数线长度值是预设为分子分母的最大长度，如果想要使分数线再长一点，可以在分子或分母两端添加一些间隔，例如: `$ \frac{1}{2} $` , `$ \frac{\;1\;}{\;2\;} $` 表示 ![\frac{1}{2}](https://math.jianshu.com/math?formula=%5Cfrac%7B1%7D%7B2%7D), ![\frac{\;1\;}{\;2\;}](https://math.jianshu.com/math?formula=%5Cfrac%7B%5C%3B1%5C%3B%7D%7B%5C%3B2%5C%3B%7D)

  #### 2.3 根式

  - 二次根式命令: `\sqrt{表达式}` , 例如: `$ \sqrt{x} $` 表示 ![\sqrt{x}](https://math.jianshu.com/math?formula=%5Csqrt%7Bx%7D)
  - ![n](https://math.jianshu.com/math?formula=n)次根式命令: `\sqrt[n]{表达式}` , 例如: `$ \sqrt[3]{x} $` 表示 ![\sqrt[3]{x}](https://math.jianshu.com/math?formula=%5Csqrt%5B3%5D%7Bx%7D)

  被开方表达式字符高度不一致时，根号上面的横线可能不在同一条直线上，可以在被开方表达式插入一个只有高度没有宽度的数学支柱 `\mathstrut` , 例如:
   `$ \sqrt{a}+\sqrt{b}+\sqrt{c} $` , `$ \sqrt{\mathstrut a}+\sqrt{\mathstrut b}+\sqrt{\mathstrut c} $` 表示 ![\sqrt{a}+\sqrt{b}+\sqrt{c}](https://math.jianshu.com/math?formula=%5Csqrt%7Ba%7D%2B%5Csqrt%7Bb%7D%2B%5Csqrt%7Bc%7D), ![\sqrt{\mathstrut a}+\sqrt{\mathstrut b}+\sqrt{\mathstrut c}](https://math.jianshu.com/math?formula=%5Csqrt%7B%5Cmathstrut%20a%7D%2B%5Csqrt%7B%5Cmathstrut%20b%7D%2B%5Csqrt%7B%5Cmathstrut%20c%7D)

  当开方次数的位置显得略低时，可以将开方改为上标，并拉近与根式的水平距离，即将命令中的 `[n]` 改为 `[^n \!]` (其中 ^ 表示是上标，! 表示缩小间隔), 例如:
   `$ \sqrt{1+\sqrt[p]{1+\sqrt[p]{1+a}}} $` , `$ \sqrt{1+\sqrt[^p \!]{1+\sqrt[^p \!]{1+a}}} $` 表示
   ![\sqrt{1+\sqrt[p]{1+\sqrt[p]{1+a}}}](https://math.jianshu.com/math?formula=%5Csqrt%7B1%2B%5Csqrt%5Bp%5D%7B1%2B%5Csqrt%5Bp%5D%7B1%2Ba%7D%7D%7D), ![\sqrt{1+\sqrt[^p \!]{1+\sqrt[^p \!]{1+a}}}](https://math.jianshu.com/math?formula=%5Csqrt%7B1%2B%5Csqrt%5B%5Ep%20%5C!%5D%7B1%2B%5Csqrt%5B%5Ep%20%5C!%5D%7B1%2Ba%7D%7D%7D)

  #### 2.4 向量

  使用 `\vec{矢量}` 来产生一个矢量，也可以使用 `\overrightarrow` 等命令自定义字母上方的符号，例如:
   `$$ \vec{x} \quad \overleftarrow{xy} \quad \overleftrightarrow{xy} \quad \overrightarrow{xy} $$` 表示
   ![\vec{x} \quad \overleftarrow{xy} \quad \overleftrightarrow{xy} \quad \overrightarrow{xy}](https://math.jianshu.com/math?formula=%5Cvec%7Bx%7D%20%5Cquad%20%5Coverleftarrow%7Bxy%7D%20%5Cquad%20%5Coverleftrightarrow%7Bxy%7D%20%5Cquad%20%5Coverrightarrow%7Bxy%7D)

  #### 2.5 定界符 - 自适应放大命令

  自适应放大命令: `\left` 和 `\right` , 本命令放在左右定界符前，随着公式内容大小自动调整符号大小，例如: `$ \left(\frac{1}{xyz}\right) $` 表示 ![\left(\frac{1}{xyz}\right)](https://math.jianshu.com/math?formula=%5Cleft(%5Cfrac%7B1%7D%7Bxyz%7D%5Cright))

  还有另外一种使用方式 `$ () \big(\big) \Big(\Big) \Bigg(\Bigg) $` 表示 ![() \big(\big) \Big(\Big) \Bigg(\Bigg)](https://math.jianshu.com/math?formula=()%20%5Cbig(%5Cbig)%20%5CBig(%5CBig)%20%5CBigg(%5CBigg))

  > **Tips:** `\left` 和 `\right` 需成对使用，只需要一边时，可用 `\left.` 或 `\right.` 进行配对，例如: `$ \left.\frac{1}{2}x^2\right|_0^1 $` 表示 ![\left.\frac{1}{2}x^2\right|_0^1](https://math.jianshu.com/math?formula=%5Cleft.%5Cfrac%7B1%7D%7B2%7Dx%5E2%5Cright%7C_0%5E1) .

  #### 2.6 空白间距 - 占位宽度

  `\quad` 代表当前字体下接近字符 `M` 的宽度。

  |        符号        |           命令           |                             效果                             |
  | :----------------: | :----------------------: | :----------------------------------------------------------: |
  |      没有空格      |         `$ ab $`         |       ![ab](https://math.jianshu.com/math?formula=ab)        |
  | 紧贴，缩进1/6m宽度 |        `$ a\!b $`        |    ![a\!b](https://math.jianshu.com/math?formula=a%5C!b)     |
  |       小空格       |        `$ a\,b $`        |   ![a\,b](https://math.jianshu.com/math?formula=a%5C%2Cb)    |
  |     1/3个空格      |        `$ a\ b $`        |   ![a\ b](https://math.jianshu.com/math?formula=a%5C%20b)    |
  |      中等空格      | `$ a\:b $` 或 `$ a\;b $` |   ![a\;b](https://math.jianshu.com/math?formula=a%5C%3Bb)    |
  |      一个空格      |      `$a \quad b $`      | ![a \quad b](https://math.jianshu.com/math?formula=a%20%5Cquad%20b) |
  |      两个空格      |     `$ a \qquad b $`     | ![a \qquad b](https://math.jianshu.com/math?formula=a%20%5Cqquad%20b) |

  #### 2.7 省略号

  省略号用 `\dots \cdots \vdot \ddots` 表示, `\dots` 和 `\cdots` 的纵向位置不同，前者一般用于有下标的序列，例如: `$$ x_1, x_2, \dots, x_n \quad 1,2,\cdots,n \quad \vdots \quad \ddots $$` 表示 ![x_1, x_2, \dots, x_n \quad 1,2,\cdots,n \quad \vdots \quad \ddots](https://math.jianshu.com/math?formula=x_1%2C%20x_2%2C%20%5Cdots%2C%20x_n%20%5Cquad%201%2C2%2C%5Ccdots%2Cn%20%5Cquad%20%5Cvdots%20%5Cquad%20%5Cddots)

  #### 2.8 多行公式

  ##### 长公式

  无须对齐可使用 `multline` , 需要对齐使用 `split` , 用 `\\` 和 `&` 来分行和设置对齐的位置，例如:

  ```ruby
  $$\begin{multline}
  x=a+b+c+{} \\
  d+e+f+g
  \end{multline}$$
  ```

  ![\begin{multline} x=a+b+c+{} \\ d+e+f+g \end{multline}](https://math.jianshu.com/math?formula=%5Cbegin%7Bmultline%7D%20x%3Da%2Bb%2Bc%2B%7B%7D%20%5C%5C%20d%2Be%2Bf%2Bg%20%5Cend%7Bmultline%7D)

  ```ruby
  $$\begin{split}
  x={}$a+b+c+{} \\
  $d+e+f+g
  \end{split}$$
  ```

  ![\begin{split} x={}&a+b+c+{} \\ &d+e+f+g \end{split}](https://math.jianshu.com/math?formula=%5Cbegin%7Bsplit%7D%20x%3D%7B%7D%26a%2Bb%2Bc%2B%7B%7D%20%5C%5C%20%26d%2Be%2Bf%2Bg%20%5Cend%7Bsplit%7D)

  ##### 公式组

  不需要对齐的公式组用 `gather` , 需要对齐使用 `align` , 例如:

  ```ruby
  $$\begin{gather}
  a=b+c+d \\
  x=y+z
  \end{gather}$$
  ```

  ![\begin{gather} a=b+c+d \\ x=y+z \end{gather}](https://math.jianshu.com/math?formula=%5Cbegin%7Bgather%7D%20a%3Db%2Bc%2Bd%20%5C%5C%20x%3Dy%2Bz%20%5Cend%7Bgather%7D)

  ```ruby
  $$\begin{align}
  a &=b+c+d \\
  x &=y+z
  \end{align}$$
  ```

  ![\begin{align} a &=b+c+d \\ x &=y+z \end{align}](https://math.jianshu.com/math?formula=%5Cbegin%7Balign%7D%20a%20%26%3Db%2Bc%2Bd%20%5C%5C%20x%20%26%3Dy%2Bz%20%5Cend%7Balign%7D)

  ##### 分支公式

  分段函数通常用 `cases` , 例如:

  ```ruby
  $$y=\begin{cases}
  -x,\quad &x \leq 0 \\
  x, &x>0
  \end{cases}$$
  ```

  ![y=\begin{cases} -x,\quad &x \leq 0 \\ x, &x>0 \end{cases}](https://math.jianshu.com/math?formula=y%3D%5Cbegin%7Bcases%7D%20-x%2C%5Cquad%20%26x%20%5Cleq%200%20%5C%5C%20x%2C%20%26x%3E0%20%5Cend%7Bcases%7D)

  ##### 公式编号

  可以通过命令 `\tag{n}` 手动为公式编号，例如:

  ```ruby
  $$
  S(r_k)  = \sum_{r_k \ne r_i} \text{exp}(\frac{-D_s(r_k, r_i)}{\sigma_s^2})
  \tag{1}$$
  ```

  ![S(r_k) = \sum_{r_k \ne r_i} \text{exp}(\frac{-D_s(r_k, r_i)}{\sigma_s^2}) \tag{1}](https://math.jianshu.com/math?formula=S(r_k)%20%3D%20%5Csum_%7Br_k%20%5Cne%20r_i%7D%20%5Ctext%7Bexp%7D(%5Cfrac%7B-D_s(r_k%2C%20r_i)%7D%7B%5Csigma_s%5E2%7D)%20%5Ctag%7B1%7D)

  #### 2.9 上下水平线

  - `\overline{表达式}` : 在表达式上方画出水平线，例如: `$ \overline{x+y} $` 表示 ![\overline{x+y}](https://math.jianshu.com/math?formula=%5Coverline%7Bx%2By%7D)
  - `\underline{表达式}` : 在表达式下方画出水平线，例如: `$ \underline{x+y} $` 表示 ![\underline{x+y}](https://math.jianshu.com/math?formula=%5Cunderline%7Bx%2By%7D)

  #### 2.10 上下大括号

  - `\overbrace{表达式}` : 在表达式上方画出一个水平的大括号，例如:
     `$ \overbrace{1+2+3+\cdots+100}^{100} $` 表示 ![\overbrace{1+2+3+\cdots+100}^{100}](https://math.jianshu.com/math?formula=%5Coverbrace%7B1%2B2%2B3%2B%5Ccdots%2B100%7D%5E%7B100%7D)
  - `\underbrace{表达式}` : 在表达式下方画出一个水平的大括号，例如:
     `$ \underbrace{1+2+3+\cdots+100}_{100} $` 表示 ![\underbrace{1+2+3+\cdots+100}_{100}](https://math.jianshu.com/math?formula=%5Cunderbrace%7B1%2B2%2B3%2B%5Ccdots%2B100%7D_%7B100%7D)

  #### 2.11 矩阵

  生成矩阵的命令中每一行以 `\\` 结束，矩阵的元素之间用 `&` 来分隔开，例如:

  ```ruby
  $$\begin{matrix}
  x_{_{11}} & x_{_{12}} & \dots & x_{_{1n}} \\
  x_{_{21}} & x_{_{22}} & \dots & x_{_{2n}} \\
  \vdots & \vdots & \ddots  & \vdots  \\
  x_{_{m1}} & x_{_{m2}} & \dots & x_{_{mn}} \\
  \end{matrix}$$
  ```

  ![\begin{matrix} x_{_{11}} & x_{_{12}} & \dots & x_{_{1n}} \\ x_{_{21}} & x_{_{22}} & \dots & x_{_{2n}} \\ \vdots & \vdots & \ddots & \vdots \\ x_{_{m1}} & x_{_{m2}} & \dots & x_{_{mn}} \\ \end{matrix}](https://math.jianshu.com/math?formula=%5Cbegin%7Bmatrix%7D%20x_%7B_%7B11%7D%7D%20%26%20x_%7B_%7B12%7D%7D%20%26%20%5Cdots%20%26%20x_%7B_%7B1n%7D%7D%20%5C%5C%20x_%7B_%7B21%7D%7D%20%26%20x_%7B_%7B22%7D%7D%20%26%20%5Cdots%20%26%20x_%7B_%7B2n%7D%7D%20%5C%5C%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cddots%20%26%20%5Cvdots%20%5C%5C%20x_%7B_%7Bm1%7D%7D%20%26%20x_%7B_%7Bm2%7D%7D%20%26%20%5Cdots%20%26%20x_%7B_%7Bmn%7D%7D%20%5C%5C%20%5Cend%7Bmatrix%7D)

  带各类不同边界的矩阵:

  ```ruby
  $$
  \begin{pmatrix} a & b \\ c & d \\ \end{pmatrix} \quad
  \begin{bmatrix} a & b \\ c & d \\ \end{bmatrix} \quad
  \left[ \begin{matrix} a & b \\ c & d \\ \end{matrix} \right] \quad
  \begin{Bmatrix} a & b \\ c & d \\ \end{Bmatrix} \quad
  \left\{ \begin{matrix} a & b \\ c & d \\ \end{matrix} \right\} \quad
  \begin{vmatrix} a & b \\ c & d \\ \end{vmatrix} \quad
  \begin{Vmatrix} a & b \\ c & d \\ \end{Vmatrix} \quad
  \left[ \begin{array} {c|c} a & b \\ c & d \\ \end{array} \right]
  $$
  ```

  ![\begin{pmatrix} a & b \\ c & d \\ \end{pmatrix} \quad \begin{bmatrix} a & b \\ c & d \\ \end{bmatrix} \quad \left[ \begin{matrix} a & b \\ c & d \\ \end{matrix} \right] \quad \begin{Bmatrix} a & b \\ c & d \\ \end{Bmatrix} \quad \left\{ \begin{matrix} a & b \\ c & d \\ \end{matrix} \right\} \quad \begin{vmatrix} a & b \\ c & d \\ \end{vmatrix} \quad \begin{Vmatrix} a & b \\ c & d \\ \end{Vmatrix} \quad \left[ \begin{array} {c|c} a & b \\ c & d \\ \end{array} \right]](https://math.jianshu.com/math?formula=%5Cbegin%7Bpmatrix%7D%20a%20%26%20b%20%5C%5C%20c%20%26%20d%20%5C%5C%20%5Cend%7Bpmatrix%7D%20%5Cquad%20%5Cbegin%7Bbmatrix%7D%20a%20%26%20b%20%5C%5C%20c%20%26%20d%20%5C%5C%20%5Cend%7Bbmatrix%7D%20%5Cquad%20%5Cleft%5B%20%5Cbegin%7Bmatrix%7D%20a%20%26%20b%20%5C%5C%20c%20%26%20d%20%5C%5C%20%5Cend%7Bmatrix%7D%20%5Cright%5D%20%5Cquad%20%5Cbegin%7BBmatrix%7D%20a%20%26%20b%20%5C%5C%20c%20%26%20d%20%5C%5C%20%5Cend%7BBmatrix%7D%20%5Cquad%20%5Cleft%5C%7B%20%5Cbegin%7Bmatrix%7D%20a%20%26%20b%20%5C%5C%20c%20%26%20d%20%5C%5C%20%5Cend%7Bmatrix%7D%20%5Cright%5C%7D%20%5Cquad%20%5Cbegin%7Bvmatrix%7D%20a%20%26%20b%20%5C%5C%20c%20%26%20d%20%5C%5C%20%5Cend%7Bvmatrix%7D%20%5Cquad%20%5Cbegin%7BVmatrix%7D%20a%20%26%20b%20%5C%5C%20c%20%26%20d%20%5C%5C%20%5Cend%7BVmatrix%7D%20%5Cquad%20%5Cleft%5B%20%5Cbegin%7Barray%7D%20%7Bc%7Cc%7D%20a%20%26%20b%20%5C%5C%20c%20%26%20d%20%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D)

  #### 2.12 Norm - 范数符号

  范数命令: `\parallel`
   例如: `$ \parallel x \parallel _2 $` 表示 ![\parallel x \parallel _2](https://math.jianshu.com/math?formula=%5Cparallel%20x%20%5Cparallel%20_2)

  #### 2.13 堆积符号

  - `\stackrel{上位符号}{基位符号}` : 基位符号大，上位符号小，例如:
     `$ \vec{x}\stackrel{\mathrm{def}}{=}{x_1,\dots,x_n} $` 表示 ![\vec{x}\stackrel{\mathrm{def}}{=}{x_1,\dots,x_n}](https://math.jianshu.com/math?formula=%5Cvec%7Bx%7D%5Cstackrel%7B%5Cmathrm%7Bdef%7D%7D%7B%3D%7D%7Bx_1%2C%5Cdots%2Cx_n%7D)
  - `{上位公式 \choose 下位公式}` : 上下符号一样大，上下符号被包括在圆弧内，例如:
     `$ {n+1 \choose k}={n \choose k}+{n \choose k-1} $` 表示 ![{n+1 \choose k}={n \choose k}+{n \choose k-1}](https://math.jianshu.com/math?formula=%7Bn%2B1%20%5Cchoose%20k%7D%3D%7Bn%20%5Cchoose%20k%7D%2B%7Bn%20%5Cchoose%20k-1%7D)
  - `{上位公式 \atop 下位公式}` : 上下符号一样大，例如:
     `$ \sum_{k_0,k_1,\ldots>0 \atop k_0+k_1+\cdots=n}A_k $` 表示 ![\sum_{k_0,k_1,\ldots>0 \atop k_0+k_1+\cdots=n}A_k](https://math.jianshu.com/math?formula=%5Csum_%7Bk_0%2Ck_1%2C%5Cldots%3E0%20%5Catop%20k_0%2Bk_1%2B%5Ccdots%3Dn%7DA_k)

  #### 2.14 给公式加一个方框

  `\boxed` 命令给公式加一个方框，例如: `$$ \boxed{E=mc^2} $$`表示 ![\boxed{E=mc^2}](https://math.jianshu.com/math?formula=%5Cboxed%7BE%3Dmc%5E2%7D)

  #### 2.15 字体转换

  若要对公式的某一部分字符进行字体转换，可以用 `{\字体 {需转换的部分字符}}` 命令，其中 `\字体` 部分可以参照下表选择合适的字体，一般情况下，公式默认为意大利体。

  |     命令      |    说明    |                             效果                             |
  | :-----------: | :--------: | :----------------------------------------------------------: |
  |     `\rm`     |   罗马体   |  ![\rm D](https://math.jianshu.com/math?formula=%5Crm%20D)   |
  |    `\cal`     |    花体    | ![\cal D](https://math.jianshu.com/math?formula=%5Ccal%20D)  |
  |     `\it`     |  意大利体  |  ![\it D](https://math.jianshu.com/math?formula=%5Cit%20D)   |
  |    `\Bbb`     |  黑板粗体  | ![\Bbb D](https://math.jianshu.com/math?formula=%5CBbb%20D)  |
  |     `\bf`     |    粗体    |  ![\bf D](https://math.jianshu.com/math?formula=%5Cbf%20D)   |
  |    `\mit`     |  数学斜体  | ![\mit D](https://math.jianshu.com/math?formula=%5Cmit%20D)  |
  |     `\sf`     |   等线体   |  ![\sf D](https://math.jianshu.com/math?formula=%5Csf%20D)   |
  |    `\scr`     |   手写体   | ![\scr D](https://math.jianshu.com/math?formula=%5Cscr%20D)  |
  |     `\tt`     |  打字机体  |  ![\tt D](https://math.jianshu.com/math?formula=%5Ctt%20D)   |
  |    `\frak`    | 旧德式字体 | ![\frak D](https://math.jianshu.com/math?formula=%5Cfrak%20D) |
  | `\boldsymbol` |    黑体    | ![\boldsymbol D](https://math.jianshu.com/math?formula=%5Cboldsymbol%20D) |

  ------

  ## 3 LaTex 常用数学符号整理

  #### 表3.1 数学模式重音符号

  |                             符号                             |      命令       |                             符号                             |      命令       |                             符号                             |        命令         |
  | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: | :-----------------: |
  | ![\hat{a}](https://math.jianshu.com/math?formula=%5Chat%7Ba%7D) |  `$ \hat{a} $`  | ![\check{a}](https://math.jianshu.com/math?formula=%5Ccheck%7Ba%7D) | `$ \check{a} $` | ![\tilde{a}](https://math.jianshu.com/math?formula=%5Ctilde%7Ba%7D) |   `$ \tilde{a} $`   |
  | ![\grave{a}](https://math.jianshu.com/math?formula=%5Cgrave%7Ba%7D) | `$ \grave{a} $` | ![\dot{a}](https://math.jianshu.com/math?formula=%5Cdot%7Ba%7D) |  `$ \dot{a} $`  | ![\ddot{a}](https://math.jianshu.com/math?formula=%5Cddot%7Ba%7D) |   `$ \ddot{a} $`    |
  | ![\bar{a}](https://math.jianshu.com/math?formula=%5Cbar%7Ba%7D) |  `$ \bar{a} $`  | ![\vec{a}](https://math.jianshu.com/math?formula=%5Cvec%7Ba%7D) |  `$ \vec{a} $`  | ![\widehat{A}](https://math.jianshu.com/math?formula=%5Cwidehat%7BA%7D) |  `$ \widehat{A} $`  |
  | ![\acute{a}](https://math.jianshu.com/math?formula=%5Cacute%7Ba%7D) | `$ \acute{a} $` | ![\breve{a}](https://math.jianshu.com/math?formula=%5Cbreve%7Ba%7D) | `$ \breve{a} $` | ![\widetilde{A}](https://math.jianshu.com/math?formula=%5Cwidetilde%7BA%7D) | `$ \widetilde{A} $` |

  #### 表3.2 希腊字母

  |                             符号                             |       命令        |                             符号                             |      命令       |                             符号                             |      命令       |                             符号                             |      命令      |
  | :----------------------------------------------------------: | :---------------: | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: | :------------: |
  |  ![\alpha](https://math.jianshu.com/math?formula=%5Calpha)   |   `$ \alpha $`    |  ![\theta](https://math.jianshu.com/math?formula=%5Ctheta)   |  `$ \theta $`   |        ![o](https://math.jianshu.com/math?formula=o)         |     `$ o $`     | ![\upsilon](https://math.jianshu.com/math?formula=%5Cupsilon) | `$ \upsilon $` |
  |   ![\beta](https://math.jianshu.com/math?formula=%5Cbeta)    |    `$ \beta $`    | ![\vartheta](https://math.jianshu.com/math?formula=%5Cvartheta) | `$ \vartheta $` |     ![\pi](https://math.jianshu.com/math?formula=%5Cpi)      |    `$ \pi $`    |    ![\phi](https://math.jianshu.com/math?formula=%5Cphi)     |   `$ \phi $`   |
  |  ![\gamma](https://math.jianshu.com/math?formula=%5Cgamma)   |   `$ \gamma $`    |   ![\iota](https://math.jianshu.com/math?formula=%5Ciota)    |   `$ \iota $`   |  ![\varpi](https://math.jianshu.com/math?formula=%5Cvarpi)   |  `$ \varpi $`   | ![\varphi](https://math.jianshu.com/math?formula=%5Cvarphi)  | `$ \varphi $`  |
  |  ![\delta](https://math.jianshu.com/math?formula=%5Cdelta)   |   `$ \delta $`    |  ![\kappa](https://math.jianshu.com/math?formula=%5Ckappa)   |  `$ \kappa $`   |    ![\rho](https://math.jianshu.com/math?formula=%5Crho)     |   `$ \rho $`    |    ![\chi](https://math.jianshu.com/math?formula=%5Cchi)     |   `$ \chi $`   |
  | ![\epsilon](https://math.jianshu.com/math?formula=%5Cepsilon) |  `$ \epsilon $`   | ![\lambda](https://math.jianshu.com/math?formula=%5Clambda)  |  `$ \lambda $`  | ![\varrho](https://math.jianshu.com/math?formula=%5Cvarrho)  |  `$ \varrho $`  |    ![\psi](https://math.jianshu.com/math?formula=%5Cpsi)     |   `$ \psi $`   |
  | ![\varepsilon](https://math.jianshu.com/math?formula=%5Cvarepsilon) | `$ \varepsilon $` |     ![\mu](https://math.jianshu.com/math?formula=%5Cmu)      |    `$ \mu $`    |  ![\sigma](https://math.jianshu.com/math?formula=%5Csigma)   |  `$ \sigma $`   |  ![\omega](https://math.jianshu.com/math?formula=%5Comega)   |  `$ \omega $`  |
  |   ![\zeta](https://math.jianshu.com/math?formula=%5Czeta)    |    `$ \zeta $`    |     ![\nu](https://math.jianshu.com/math?formula=%5Cnu)      |    `$ \nu $`    | ![\varsigma](https://math.jianshu.com/math?formula=%5Cvarsigma) | `$ \varsigma $` |                                                              |                |
  |    ![\eta](https://math.jianshu.com/math?formula=%5Ceta)     |    `$ \eta $`     |     ![\xi](https://math.jianshu.com/math?formula=%5Cxi)      |    `$ \xi $`    |    ![\tau](https://math.jianshu.com/math?formula=%5Ctau)     |   `$ \tau $`    |                                                              |                |

  > **Tips:**
  >
  > 1. 如果使用大写的希腊字母，把命令的首字母变成大写即可，例如: `$ \Gamma $` 表示 ![\Gamma](https://math.jianshu.com/math?formula=%5CGamma) .
  > 2. 如果使用斜体大写希腊字母，再在大写希腊字母的 LaTex 命令前加上 var , 例如:
  >     `$ \varGamma $` 表示 ![\varGamma](https://math.jianshu.com/math?formula=%5CvarGamma) .

  #### 表3.3 二元关系符

  |                             符号                             |          命令           |                             符号                             |           命令           |                            符号                             |          命令           |
  | :----------------------------------------------------------: | :---------------------: | :----------------------------------------------------------: | :----------------------: | :---------------------------------------------------------: | :---------------------: |
  |       ![<](https://math.jianshu.com/math?formula=%3C)        |         `$ < $`         |       ![>](https://math.jianshu.com/math?formula=%3E)        |         `$ > $`          |       ![=](https://math.jianshu.com/math?formula=%3D)       |         `$ = $`         |
  |     ![\le](https://math.jianshu.com/math?formula=%5Cle)      | `$ \leq $` 或 `$ \le $` |     ![\ge](https://math.jianshu.com/math?formula=%5Cge)      | `$ \geq $` 或 `$ \ge $`  |  ![\equiv](https://math.jianshu.com/math?formula=%5Cequiv)  |      `$ \equiv $`       |
  |     ![\ll](https://math.jianshu.com/math?formula=%5Cll)      |        `$ \ll $`        |     ![\gg](https://math.jianshu.com/math?formula=%5Cgg)      |        `$ \gg $`         |  ![\doteq](https://math.jianshu.com/math?formula=%5Cdoteq)  |      `$ \doteq $`       |
  |   ![\prec](https://math.jianshu.com/math?formula=%5Cprec)    |       `$ \prec $`       |   ![\succ](https://math.jianshu.com/math?formula=%5Csucc)    |       `$ \succ $`        |    ![\sim](https://math.jianshu.com/math?formula=%5Csim)    |       `$ \sim $`        |
  | ![\preceq](https://math.jianshu.com/math?formula=%5Cpreceq)  |      `$ \preceq $`      | ![\succeq](https://math.jianshu.com/math?formula=%5Csucceq)  |      `$ \succeq $`       |  ![\simeq](https://math.jianshu.com/math?formula=%5Csimeq)  |      `$ \simeq $`       |
  | ![\subset](https://math.jianshu.com/math?formula=%5Csubset)  |      `$ \subset $`      | ![\supset](https://math.jianshu.com/math?formula=%5Csupset)  |      `$ \supset $`       | ![\approx](https://math.jianshu.com/math?formula=%5Capprox) |      `$ \approx $`      |
  | ![\subseteq](https://math.jianshu.com/math?formula=%5Csubseteq) |     `$ \subseteq $`     | ![\supseteq](https://math.jianshu.com/math?formula=%5Csupseteq) |     `$ \supseteq $`      |   ![\cong](https://math.jianshu.com/math?formula=%5Ccong)   |       `$ \cong $`       |
  | ![\sqsubset](https://math.jianshu.com/math?formula=%5Csqsubset) |     `$ \sqsubset $`     | ![\sqsupset](https://math.jianshu.com/math?formula=%5Csqsupset) |     `$ \sqsupset $`      |   ![\Join](https://math.jianshu.com/math?formula=%5CJoin)   |       `$ \Join $`       |
  | ![\sqsubseteq](https://math.jianshu.com/math?formula=%5Csqsubseteq) |    `$ \sqsubseteq $`    | ![\sqsupseteq](https://math.jianshu.com/math?formula=%5Csqsupseteq) |    `$ \sqsupseteq $`     | ![\bowtie](https://math.jianshu.com/math?formula=%5Cbowtie) |      `$ \bowtie $`      |
  |     ![\in](https://math.jianshu.com/math?formula=%5Cin)      |        `$ \in $`        |     ![\ni](https://math.jianshu.com/math?formula=%5Cni)      | `$ \ni $` 或 `$ \owns $` | ![\propto](https://math.jianshu.com/math?formula=%5Cpropto) |      `$ \propto $`      |
  |  ![\vdash](https://math.jianshu.com/math?formula=%5Cvdash)   |      `$ \vdash $`       |  ![\dashv](https://math.jianshu.com/math?formula=%5Cdashv)   |       `$ \dashv $`       | ![\models](https://math.jianshu.com/math?formula=%5Cmodels) |      `$ \models $`      |
  |    ![\mid](https://math.jianshu.com/math?formula=%5Cmid)     |       `$ \mid $`        | ![\parallel](https://math.jianshu.com/math?formula=%5Cparallel) |     `$ \parallel $`      |   ![\perp](https://math.jianshu.com/math?formula=%5Cperp)   |       `$ \perp $`       |
  |  ![\smile](https://math.jianshu.com/math?formula=%5Csmile)   |      `$ \smile $`       |  ![\frown](https://math.jianshu.com/math?formula=%5Cfrown)   |       `$ \frown $`       |  ![\asymp](https://math.jianshu.com/math?formula=%5Casymp)  |      `$ \asymp $`       |
  |       ![:](https://math.jianshu.com/math?formula=%3A)        |         `$ : $`         |  ![\notin](https://math.jianshu.com/math?formula=%5Cnotin)   |       `$ \notin $`       |     ![\ne](https://math.jianshu.com/math?formula=%5Cne)     | `$ \neq $` 或 `$ \ne $` |

  > **Tips:** 可以在上述符号的相应命令前加上 `\not` , 得到其否定形式，例如:
  >  `$ \not\subset $` 表示 ![\not\subset](https://math.jianshu.com/math?formula=%5Cnot%5Csubset) .

  #### 表3.4 二元运算符

  |                             符号                             |         命令         |                             符号                             |            命令             |                             符号                             |         命令         |
  | :----------------------------------------------------------: | :------------------: | :----------------------------------------------------------: | :-------------------------: | :----------------------------------------------------------: | :------------------: |
  |       ![+](https://math.jianshu.com/math?formula=%2B)        |       `$ + $`        |        ![-](https://math.jianshu.com/math?formula=-)         |           `$ - $`           |                                                              |                      |
  |     ![\pm](https://math.jianshu.com/math?formula=%5Cpm)      |      `$ \pm $`       |     ![\mp](https://math.jianshu.com/math?formula=%5Cmp)      |          `$ \mp $`          | ![\triangleleft](https://math.jianshu.com/math?formula=%5Ctriangleleft) | `$ \triangleleft $`  |
  |   ![\cdot](https://math.jianshu.com/math?formula=%5Ccdot)    |     `$ \cdot $`      |    ![\div](https://math.jianshu.com/math?formula=%5Cdiv)     |         `$ \div $`          | ![\triangleright](https://math.jianshu.com/math?formula=%5Ctriangleright) | `$ \triangleright $` |
  |  ![\times](https://math.jianshu.com/math?formula=%5Ctimes)   |     `$ \times $`     | ![\setminus](https://math.jianshu.com/math?formula=%5Csetminus) |       `$ \setminus $`       |   ![\star](https://math.jianshu.com/math?formula=%5Cstar)    |     `$ \star $`      |
  |    ![\cup](https://math.jianshu.com/math?formula=%5Ccup)     |      `$ \cup $`      |    ![\cap](https://math.jianshu.com/math?formula=%5Ccap)     |         `$ \cap $`          |    ![\ast](https://math.jianshu.com/math?formula=%5Cast)     |      `$ \ast $`      |
  |  ![\sqcup](https://math.jianshu.com/math?formula=%5Csqcup)   |     `$ \sqcup $`     |  ![\sqcap](https://math.jianshu.com/math?formula=%5Csqcap)   |        `$ \sqcap $`         |   ![\circ](https://math.jianshu.com/math?formula=%5Ccirc)    |     `$ \circ $`      |
  |    ![\vee](https://math.jianshu.com/math?formula=%5Cvee)     |      `$ \vee $`      |  ![\wedge](https://math.jianshu.com/math?formula=%5Cwedge)   | `$ \wedge $` 或 `$ \land $` | ![\bullet](https://math.jianshu.com/math?formula=%5Cbullet)  |    `$ \bullet $`     |
  |  ![\oplus](https://math.jianshu.com/math?formula=%5Coplus)   |     `$ \oplus $`     | ![\ominus](https://math.jianshu.com/math?formula=%5Cominus)  |        `$ \ominus $`        | ![\diamond](https://math.jianshu.com/math?formula=%5Cdiamond) |    `$ \diamond $`    |
  |   ![\odot](https://math.jianshu.com/math?formula=%5Codot)    |     `$ \odot $`      | ![\oslash](https://math.jianshu.com/math?formula=%5Coslash)  |        `$ \oslash $`        |  ![\uplus](https://math.jianshu.com/math?formula=%5Cuplus)   |     `$ \uplus $`     |
  | ![\otimes](https://math.jianshu.com/math?formula=%5Cotimes)  |    `$ \otimes $`     | ![\bigcirc](https://math.jianshu.com/math?formula=%5Cbigcirc) |       `$ \bigcirc $`        |  ![\amalg](https://math.jianshu.com/math?formula=%5Camalg)   |     `$ \amalg $`     |
  | ![\bigtriangleup](https://math.jianshu.com/math?formula=%5Cbigtriangleup) | `$ \bigtriangleup $` | ![\bigtriangledown](https://math.jianshu.com/math?formula=%5Cbigtriangledown) |   `$ \bigtriangledown $`    | ![\dagger](https://math.jianshu.com/math?formula=%5Cdagger)  |    `$ \dagger $`     |
  |    ![\lhd](https://math.jianshu.com/math?formula=%5Clhd)     |      `$ \lhd $`      |    ![\rhd](https://math.jianshu.com/math?formula=%5Crhd)     |         `$ \rhd $`          | ![\ddagger](https://math.jianshu.com/math?formula=%5Cddagger) |    `$ \ddagger $`    |
  |  ![\unlhd](https://math.jianshu.com/math?formula=%5Cunlhd)   |     `$ \unlhd $`     |  ![\unrhd](https://math.jianshu.com/math?formula=%5Cunrhd)   |        `$ \unrhd $`         |     ![\wr](https://math.jianshu.com/math?formula=%5Cwr)      |      `$ \wr $`       |

  #### 表3.5 大尺寸运算符

  |                            符号                             |     命令      |                             符号                             |      命令       |                             符号                             |      命令       |                             符号                             |       命令       |
  | :---------------------------------------------------------: | :-----------: | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: | :--------------: |
  |    ![\sum](https://math.jianshu.com/math?formula=%5Csum)    |  `$ \sum $`   | ![\bigcup](https://math.jianshu.com/math?formula=%5Cbigcup)  |  `$ \bigcup $`  | ![\bigvee](https://math.jianshu.com/math?formula=%5Cbigvee)  |  `$ \bigvee $`  | ![\bigoplus](https://math.jianshu.com/math?formula=%5Cbigoplus) | `$ \bigoplus $`  |
  |   ![\prod](https://math.jianshu.com/math?formula=%5Cprod)   |  `$ \prod $`  | ![\bigcap](https://math.jianshu.com/math?formula=%5Cbigcap)  |  `$ \bigcap $`  | ![\bigwedge](https://math.jianshu.com/math?formula=%5Cbigwedge) | `$ \bigwedge $` | ![\bigotimes](https://math.jianshu.com/math?formula=%5Cbigotimes) | `$ \bigotimes $` |
  | ![\coprod](https://math.jianshu.com/math?formula=%5Ccoprod) | `$ \coprod $` | ![\bigsqcup](https://math.jianshu.com/math?formula=%5Cbigsqcup) | `$ \bigsqcup $` |                                                              |                 | ![\bigodot](https://math.jianshu.com/math?formula=%5Cbigodot) |  `$ \bigodot $`  |
  |    ![\int](https://math.jianshu.com/math?formula=%5Cint)    |  `$ \int $`   |   ![\oint](https://math.jianshu.com/math?formula=%5Coint)    |   `$ \oint $`   |                                                              |                 | ![\biguplus](https://math.jianshu.com/math?formula=%5Cbiguplus) | `$ \biguplus $`  |

  #### 表3.6 箭头

  |                             符号                             |               命令               |                             符号                             |           命令            |                             符号                             |        命令        |
  | :----------------------------------------------------------: | :------------------------------: | :----------------------------------------------------------: | :-----------------------: | :----------------------------------------------------------: | :----------------: |
  | ![\leftarrow](https://math.jianshu.com/math?formula=%5Cleftarrow) | `$ \leftarrow $`     `$ \gets $` | ![\longleftarrow](https://math.jianshu.com/math?formula=%5Clongleftarrow) |   `$ \longleftarrow $`    | ![\uparrow](https://math.jianshu.com/math?formula=%5Cuparrow) |   `$ \uparrow $`   |
  | ![\rightarrow](https://math.jianshu.com/math?formula=%5Crightarrow) |  `$ \rightarrow $`   `$ \to $`   | ![\longrightarrow](https://math.jianshu.com/math?formula=%5Clongrightarrow) |   `$ \longrightarrow $`   | ![\downarrow](https://math.jianshu.com/math?formula=%5Cdownarrow) |  `$ \downarrow $`  |
  | ![\leftrightarrow](https://math.jianshu.com/math?formula=%5Cleftrightarrow) |      `$ \leftrightarrow $`       | ![\longleftrightarrow](https://math.jianshu.com/math?formula=%5Clongleftrightarrow) | `$ \longleftrightarrow $` | ![\updownarrow](https://math.jianshu.com/math?formula=%5Cupdownarrow) | `$ \updownarrow $` |
  | ![\Leftarrow](https://math.jianshu.com/math?formula=%5CLeftarrow) |         `$ \Leftarrow $`         | ![\Longleftarrow](https://math.jianshu.com/math?formula=%5CLongleftarrow) |   `$ \Longleftarrow $`    | ![\Uparrow](https://math.jianshu.com/math?formula=%5CUparrow) |   `$ \Uparrow $`   |
  | ![\Rightarrow](https://math.jianshu.com/math?formula=%5CRightarrow) |        `$ \Rightarrow $`         | ![\Longrightarrow](https://math.jianshu.com/math?formula=%5CLongrightarrow) |   `$ \Longrightarrow $`   | ![\Downarrow](https://math.jianshu.com/math?formula=%5CDownarrow) |  `$ \Downarrow $`  |
  | ![\Leftrightarrow](https://math.jianshu.com/math?formula=%5CLeftrightarrow) |      `$ \Leftrightarrow $`       | ![\Longleftrightarrow](https://math.jianshu.com/math?formula=%5CLongleftrightarrow) | `$ \Longleftrightarrow $` | ![\Updownarrow](https://math.jianshu.com/math?formula=%5CUpdownarrow) | `$ \Updownarrow $` |
  | ![\mapsto](https://math.jianshu.com/math?formula=%5Cmapsto)  |          `$ \mapsto $`           | ![\longmapsto](https://math.jianshu.com/math?formula=%5Clongmapsto) |     `$ \longmapsto $`     | ![\nearrow](https://math.jianshu.com/math?formula=%5Cnearrow) |   `$ \nearrow $`   |
  | ![\hookleftarrow](https://math.jianshu.com/math?formula=%5Chookleftarrow) |       `$ \hookleftarrow $`       | ![\hookrightarrow](https://math.jianshu.com/math?formula=%5Chookrightarrow) |   `$ \hookrightarrow $`   | ![\searrow](https://math.jianshu.com/math?formula=%5Csearrow) |   `$ \searrow $`   |
  | ![\leftharpoonup](https://math.jianshu.com/math?formula=%5Cleftharpoonup) |       `$ \leftharpoonup $`       | ![\rightharpoonup](https://math.jianshu.com/math?formula=%5Crightharpoonup) |   `$ \rightharpoonup $`   | ![\swarrow](https://math.jianshu.com/math?formula=%5Cswarrow) |   `$ \swarrow $`   |
  | ![\leftharpoondown](https://math.jianshu.com/math?formula=%5Cleftharpoondown) |      `$ \leftharpoondown $`      | ![\rightharpoondown](https://math.jianshu.com/math?formula=%5Crightharpoondown) |  `$ \rightharpoondown $`  | ![\nwarrow](https://math.jianshu.com/math?formula=%5Cnwarrow) |   `$ \nwarrow $`   |
  | ![\rightleftharpoons](https://math.jianshu.com/math?formula=%5Crightleftharpoons) |     `$ \rightleftharpoons $`     |    ![\iff](https://math.jianshu.com/math?formula=%5Ciff)     |        `$ \iff $`         | ![\leadsto](https://math.jianshu.com/math?formula=%5Cleadsto) |   `$ \leadsto $`   |

  #### 表3.7 大尺寸定界符

  |                             符号                             |       命令        |                             符号                             |       命令        |
  | :----------------------------------------------------------: | :---------------: | :----------------------------------------------------------: | :---------------: |
  | ![\lgroup](https://math.jianshu.com/math?formula=%5Clgroup)  |   `$ \lgroup $`   | ![\rgroup](https://math.jianshu.com/math?formula=%5Crgroup)  |   `$ \rgroup $`   |
  | ![\lmoustache](https://math.jianshu.com/math?formula=%5Clmoustache) | `$ \lmoustache $` | ![\rmoustache](https://math.jianshu.com/math?formula=%5Crmoustache) | `$ \rmoustache $` |
  | ![\arrowvert](https://math.jianshu.com/math?formula=%5Carrowvert) | `$ \arrowvert $`  | ![\Arrowvert](https://math.jianshu.com/math?formula=%5CArrowvert) | `$ \Arrowvert $`  |
  | ![\bracevert](https://math.jianshu.com/math?formula=%5Cbracevert) | `$ \bracevert $`  |                                                              |                   |

  #### 表3.8 其它符号

  |                             符号                             |           命令           |                             符号                             |       命令       |                             符号                             |      命令       |                             符号                             |       命令       |
  | :----------------------------------------------------------: | :----------------------: | :----------------------------------------------------------: | :--------------: | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: | :--------------: |
  |   ![\dots](https://math.jianshu.com/math?formula=%5Cdots)    |       `$ \dots $`        |  ![\cdots](https://math.jianshu.com/math?formula=%5Ccdots)   |   `$ \cdots $`   |  ![\vdots](https://math.jianshu.com/math?formula=%5Cvdots)   |  `$ \vdots $`   |  ![\ddots](https://math.jianshu.com/math?formula=%5Cddots)   |   `$ \ddots $`   |
  |   ![\hbar](https://math.jianshu.com/math?formula=%5Chbar)    |       `$ \hbar $`        |  ![\imath](https://math.jianshu.com/math?formula=%5Cimath)   |   `$ \imath $`   |  ![\jmath](https://math.jianshu.com/math?formula=%5Cjmath)   |  `$ \jmath $`   |    ![\ell](https://math.jianshu.com/math?formula=%5Cell)     |    `$ \ell $`    |
  |     ![\Re](https://math.jianshu.com/math?formula=%5CRe)      |        `$ \Re $`         |     ![\Im](https://math.jianshu.com/math?formula=%5CIm)      |    `$ \Im $`     |  ![\aleph](https://math.jianshu.com/math?formula=%5Caleph)   |  `$ \aleph $`   |     ![\wp](https://math.jianshu.com/math?formula=%5Cwp)      |    `$ \wp $`     |
  | ![\forall](https://math.jianshu.com/math?formula=%5Cforall)  |      `$ \forall $`       | ![\exists](https://math.jianshu.com/math?formula=%5Cexists)  |  `$ \exists $`   |    ![\mho](https://math.jianshu.com/math?formula=%5Cmho)     |   `$ \mho $`    | ![\partial](https://math.jianshu.com/math?formula=%5Cpartial) |   `\partial $`   |
  |        !['](https://math.jianshu.com/math?formula=')         |         `$ ' $`          |  ![\prime](https://math.jianshu.com/math?formula=%5Cprime)   |   `$ \prime $`   | ![\emptyset](https://math.jianshu.com/math?formula=%5Cemptyset) | `$ \emptyset $` |  ![\infty](https://math.jianshu.com/math?formula=%5Cinfty)   |   `$ \infty $`   |
  |  ![\nabla](https://math.jianshu.com/math?formula=%5Cnabla)   |       `$ \nabla $`       | ![\triangle](https://math.jianshu.com/math?formula=%5Ctriangle) | `$ \triangle $`  |    ![\Box](https://math.jianshu.com/math?formula=%5CBox)     |   `$ \Box $`    | ![\Diamond](https://math.jianshu.com/math?formula=%5CDiamond) |  `$ \Diamond $`  |
  |    ![\bot](https://math.jianshu.com/math?formula=%5Cbot)     |        `$ \bot $`        |    ![\top](https://math.jianshu.com/math?formula=%5Ctop)     |    `$ \top $`    |  ![\angle](https://math.jianshu.com/math?formula=%5Cangle)   |  `$ \angle $`   |   ![\surd](https://math.jianshu.com/math?formula=%5Csurd)    |   `$ \surd $`    |
  | ![\diamondsuit](https://math.jianshu.com/math?formula=%5Cdiamondsuit) |    `$ \diamondsuit $`    | ![\heartsuit](https://math.jianshu.com/math?formula=%5Cheartsuit) | `$ \heartsuit $` | ![\clubsuit](https://math.jianshu.com/math?formula=%5Cclubsuit) | `$ \clubsuit $` | ![\spadesuit](https://math.jianshu.com/math?formula=%5Cspadesuit) | `$ \spadesuit $` |
  |   ![\lnot](https://math.jianshu.com/math?formula=%5Clnot)    | `$ \neg $`   `$ \lnot $` |   ![\flat](https://math.jianshu.com/math?formula=%5Cflat)    |   `$ \flat $`    | ![\natural](https://math.jianshu.com/math?formula=%5Cnatural) | `$ \natural $`  |  ![\sharp](https://math.jianshu.com/math?formula=%5Csharp)   |   `$ \sharp $`   |

  #### 表3.9 AMS 定界符

  |                             符号                             |      命令       |                             符号                             |      命令       |                             符号                             |      命令       |                             符号                             |      命令       |
  | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: | :-------------: | :----------------------------------------------------------: | :-------------: |
  | ![\ulcorner](https://math.jianshu.com/math?formula=%5Culcorner) | `$ \ulcorner $` | ![\urcorner](https://math.jianshu.com/math?formula=%5Curcorner) | `$ \urcorner $` | ![\llcorner](https://math.jianshu.com/math?formula=%5Cllcorner) | `$ \llcorner $` | ![\lrcorner](https://math.jianshu.com/math?formula=%5Clrcorner) | `$ \lrcorner $` |
  |  ![\lvert](https://math.jianshu.com/math?formula=%5Clvert)   |  `$ \lvert $`   |  ![\rvert](https://math.jianshu.com/math?formula=%5Crvert)   |  `$ \rvert $`   |  ![\lVert](https://math.jianshu.com/math?formula=%5ClVert)   |  `$ \lVert $`   |  ![\rVert](https://math.jianshu.com/math?formula=%5CrVert)   |  `$ \rVert $`   |

  #### 表3.10 AMS 希腊和希伯来字母

  |                             符号                             |      命令      |                             符号                             |      命令       |                          符号                           |    命令     |
  | :----------------------------------------------------------: | :------------: | :----------------------------------------------------------: | :-------------: | :-----------------------------------------------------: | :---------: |
  | ![\digamma](https://math.jianshu.com/math?formula=%5Cdigamma) | `$ \digamma $` | ![\varkappa](https://math.jianshu.com/math?formula=%5Cvarkappa) | `$ \varkappa $` | ![\beth](https://math.jianshu.com/math?formula=%5Cbeth) | `$ \beth $` |
  | ![\daleth](https://math.jianshu.com/math?formula=%5Cdaleth)  | `$ \daleth $`  |  ![\gimel](https://math.jianshu.com/math?formula=%5Cgimel)   |  `$ \gimel $`   |                                                         |             |

  #### 表3.11 AMS 二元关系符

  |                             符号                             |            命令             |                             符号                             |          命令           |                             符号                             |           命令            |
  | :----------------------------------------------------------: | :-------------------------: | :----------------------------------------------------------: | :---------------------: | :----------------------------------------------------------: | :-----------------------: |
  | ![\lessdot](https://math.jianshu.com/math?formula=%5Clessdot) |       `$ \lessdot $`        | ![\gtrdot](https://math.jianshu.com/math?formula=%5Cgtrdot)  |       `\gtrdot $`       | ![\doteqdot](https://math.jianshu.com/math?formula=%5Cdoteqdot) |      `$ \doteqdot $`      |
  | ![\leqslant](https://math.jianshu.com/math?formula=%5Cleqslant) |       `$ \leqslant $`       | ![\geqslant](https://math.jianshu.com/math?formula=%5Cgeqslant) |     `$ \geqslant $`     | ![\risingdotseq](https://math.jianshu.com/math?formula=%5Crisingdotseq) |    `$ \risingdotseq $`    |
  | ![\eqslantless](https://math.jianshu.com/math?formula=%5Ceqslantless) |     `$ \eqslantless $`      | ![\eqslantgtr](https://math.jianshu.com/math?formula=%5Ceqslantgtr) |    `$ \eqslantgtr $`    | ![\fallingdotseq](https://math.jianshu.com/math?formula=%5Cfallingdotseq) |   `$ \fallingdotseq $`    |
  |   ![\leqq](https://math.jianshu.com/math?formula=%5Cleqq)    |         `$ \leqq $`         |   ![\geqq](https://math.jianshu.com/math?formula=%5Cgeqq)    |       `$ \geqq $`       | ![\eqcirc](https://math.jianshu.com/math?formula=%5Ceqcirc)  |       `$ \eqcirc $`       |
  |    ![\lll](https://math.jianshu.com/math?formula=%5Clll)     | `$ \lll $` 或 `$ \llless $` |    ![\ggg](https://math.jianshu.com/math?formula=%5Cggg)     |       `$ \ggg $`        | ![\circeq](https://math.jianshu.com/math?formula=%5Ccirceq)  |       `$ \circeq $`       |
  | ![\lesssim](https://math.jianshu.com/math?formula=%5Clesssim) |       `$ \lesssim $`        | ![\gtrsim](https://math.jianshu.com/math?formula=%5Cgtrsim)  |      `$ \gtrsim $`      | ![\triangleq](https://math.jianshu.com/math?formula=%5Ctriangleq) |     `$ \triangleq $`      |
  | ![\lessapprox](https://math.jianshu.com/math?formula=%5Clessapprox) |      `$ \lessapprox $`      | ![\gtrapprox](https://math.jianshu.com/math?formula=%5Cgtrapprox) |    `$ \gtrapprox $`     | ![\bumpeq](https://math.jianshu.com/math?formula=%5Cbumpeq)  |       `$ \bumpeq $`       |
  | ![\lessgtr](https://math.jianshu.com/math?formula=%5Clessgtr) |       `$ \lessgtr $`        | ![\gtrless](https://math.jianshu.com/math?formula=%5Cgtrless) |     `$ \gtrless $`      | ![\Bumpeq](https://math.jianshu.com/math?formula=%5CBumpeq)  |       `$ \Bumpeq $`       |
  | ![\lesseqgtr](https://math.jianshu.com/math?formula=%5Clesseqgtr) |      `$ \lesseqgtr $`       | ![\gtreqless](https://math.jianshu.com/math?formula=%5Cgtreqless) |    `$ \gtreqless $`     | ![\thicksim](https://math.jianshu.com/math?formula=%5Cthicksim) |      `$ \thicksim $`      |
  | ![\lesseqqgtr](https://math.jianshu.com/math?formula=%5Clesseqqgtr) |      `$ \lesseqqgtr $`      | ![\gtreqqless](https://math.jianshu.com/math?formula=%5Cgtreqqless) |    `$ \gtreqqless $`    | ![\thickapprox](https://math.jianshu.com/math?formula=%5Cthickapprox) |    `$ \thickapprox $`     |
  | ![\preccurlyeq](https://math.jianshu.com/math?formula=%5Cpreccurlyeq) |     `$ \preccurlyeq $`      | ![\succcurlyeq](https://math.jianshu.com/math?formula=%5Csucccurlyeq) |   `$ \succcurlyeq $`    | ![\approxeq](https://math.jianshu.com/math?formula=%5Capproxeq) |      `$ \approxeq $`      |
  | ![\curlyeqprec](https://math.jianshu.com/math?formula=%5Ccurlyeqprec) |     `$ \curlyeqprec $`      | ![\curlyeqsucc](https://math.jianshu.com/math?formula=%5Ccurlyeqsucc) |   `$ \curlyeqsucc $`    | ![\backsim](https://math.jianshu.com/math?formula=%5Cbacksim) |      `$ \backsim $`       |
  | ![\precsim](https://math.jianshu.com/math?formula=%5Cprecsim) |       `$ \precsim $`        | ![\succsim](https://math.jianshu.com/math?formula=%5Csuccsim) |     `$ \succsim $`      | ![\backsimeq](https://math.jianshu.com/math?formula=%5Cbacksimeq) |     `$ \backsimeq $`      |
  | ![\precapprox](https://math.jianshu.com/math?formula=%5Cprecapprox) |      `$ \precapprox $`      | ![\succapprox](https://math.jianshu.com/math?formula=%5Csuccapprox) |    `$ \succapprox $`    |  ![\vDash](https://math.jianshu.com/math?formula=%5CvDash)   |       `$ \vDash $`        |
  | ![\subseteqq](https://math.jianshu.com/math?formula=%5Csubseteqq) |      `$ \subseteqq $`       | ![\supseteqq](https://math.jianshu.com/math?formula=%5Csupseteqq) |    `$ \supseteqq $`     |  ![\Vdash](https://math.jianshu.com/math?formula=%5CVdash)   |       `$ \Vdash $`        |
  | ![\Subset](https://math.jianshu.com/math?formula=%5CSubset)  |        `$ \Subset $`        | ![\Supset](https://math.jianshu.com/math?formula=%5CSupset)  |      `$ \Supset $`      | ![\Vvdash](https://math.jianshu.com/math?formula=%5CVvdash)  |        `\Vvdash $`        |
  | ![\sqsubset](https://math.jianshu.com/math?formula=%5Csqsubset) |       `$ \sqsubset $`       | ![\sqsupset](https://math.jianshu.com/math?formula=%5Csqsupset) |     `$ \sqsupset $`     | ![\backepsilon](https://math.jianshu.com/math?formula=%5Cbackepsilon) |    `$ \backepsilon $`     |
  | ![\therefore](https://math.jianshu.com/math?formula=%5Ctherefore) |      `$ \therefore $`       | ![\because](https://math.jianshu.com/math?formula=%5Cbecause) |     `$ \because $`      | ![\varpropto](https://math.jianshu.com/math?formula=%5Cvarpropto) |     `$ \varpropto $`      |
  | ![\shortmid](https://math.jianshu.com/math?formula=%5Cshortmid) |       `$ \shortmid $`       | ![\shortparallel](https://math.jianshu.com/math?formula=%5Cshortparallel) |  `$ \shortparallel $`   | ![\between](https://math.jianshu.com/math?formula=%5Cbetween) |      `$ \between $`       |
  | ![\smallsmile](https://math.jianshu.com/math?formula=%5Csmallsmile) |      `$ \smallsmile $`      | ![\smallfrown](https://math.jianshu.com/math?formula=%5Csmallfrown) |    `$ \smallfrown $`    | ![\pitchfork](https://math.jianshu.com/math?formula=%5Cpitchfork) |     `$ \pitchfork $`      |
  | ![\vartriangleleft](https://math.jianshu.com/math?formula=%5Cvartriangleleft) |   `$ \vartriangleleft $`    | ![\vartriangleright](https://math.jianshu.com/math?formula=%5Cvartriangleright) | `$ \vartriangleright $` | ![\blacktriangleleft](https://math.jianshu.com/math?formula=%5Cblacktriangleleft) | `$ \blacktriangleleft $`  |
  | ![\trianglelefteq](https://math.jianshu.com/math?formula=%5Ctrianglelefteq) |    `$ \trianglelefteq $`    | ![\trianglerighteq](https://math.jianshu.com/math?formula=%5Ctrianglerighteq) | `$ \trianglerighteq $`  | ![\blacktriangleright](https://math.jianshu.com/math?formula=%5Cblacktriangleright) | `$ \blacktriangleright $` |

  #### 表3.12 AMS 箭头

  |                             符号                             |          命令           |                             符号                             |           命令           |                             符号                             |            命令            |
  | :----------------------------------------------------------: | :---------------------: | :----------------------------------------------------------: | :----------------------: | :----------------------------------------------------------: | :------------------------: |
  | ![\dashleftarrow](https://math.jianshu.com/math?formula=%5Cdashleftarrow) |  `$ \dashleftarrow $`   | ![\dashrightarrow](https://math.jianshu.com/math?formula=%5Cdashrightarrow) |  `$ \dashrightarrow $`   | ![\multimap](https://math.jianshu.com/math?formula=%5Cmultimap) |      `$ \multimap $`       |
  | ![\leftleftarrows](https://math.jianshu.com/math?formula=%5Cleftleftarrows) |  `$ \leftleftarrows $`  | ![\rightrightarrows](https://math.jianshu.com/math?formula=%5Crightrightarrows) | `$ \rightrightarrows $`  | ![\upuparrows](https://math.jianshu.com/math?formula=%5Cupuparrows) |     `$ \upuparrows $`      |
  | ![\leftrightarrows](https://math.jianshu.com/math?formula=%5Cleftrightarrows) | `$ \leftrightarrows $`  | ![\rightleftarrows](https://math.jianshu.com/math?formula=%5Crightleftarrows) |  `$ \rightleftarrows $`  | ![\downdownarrows](https://math.jianshu.com/math?formula=%5Cdowndownarrows) |   `$ \downdownarrows $`    |
  | ![\Lleftarrow](https://math.jianshu.com/math?formula=%5CLleftarrow) |    `$ \Lleftarrow $`    | ![\Rrightarrow](https://math.jianshu.com/math?formula=%5CRrightarrow) |    `$ \Rrightarrow $`    | ![\upharpoonleft](https://math.jianshu.com/math?formula=%5Cupharpoonleft) |    `$ \upharpoonleft $`    |
  | ![\twoheadleftarrow](https://math.jianshu.com/math?formula=%5Ctwoheadleftarrow) | `$ \twoheadleftarrow $` | ![\twoheadrightarrow](https://math.jianshu.com/math?formula=%5Ctwoheadrightarrow) | `$ \twoheadrightarrow $` | ![\upharpoonright](https://math.jianshu.com/math?formula=%5Cupharpoonright) |   `$ \upharpoonright $`    |
  | ![\leftarrowtail](https://math.jianshu.com/math?formula=%5Cleftarrowtail) |  `$ \leftarrowtail $`   | ![\rightarrowtail](https://math.jianshu.com/math?formula=%5Crightarrowtail) |  `$ \rightarrowtail $`   | ![\downharpoonleft](https://math.jianshu.com/math?formula=%5Cdownharpoonleft) |   `$ \downharpoonleft $`   |
  | ![\leftrightharpoons](https://math.jianshu.com/math?formula=%5Cleftrightharpoons) | `$\leftrightharpoons $` | ![\rightleftharpoons](https://math.jianshu.com/math?formula=%5Crightleftharpoons) | `$ \rightleftharpoons $` | ![\downharpoonright](https://math.jianshu.com/math?formula=%5Cdownharpoonright) |  `$ \downharpoonright $`   |
  |    ![\Lsh](https://math.jianshu.com/math?formula=%5CLsh)     |       `$ \Lsh $`        |    ![\Rsh](https://math.jianshu.com/math?formula=%5CRsh)     |        `$ \Rsh $`        | ![\rightsquigarrow](https://math.jianshu.com/math?formula=%5Crightsquigarrow) |   `$ \rightsquigarrow $`   |
  | ![\looparrowleft](https://math.jianshu.com/math?formula=%5Clooparrowleft) |  `$ \looparrowleft $`   | ![\looparrowright](https://math.jianshu.com/math?formula=%5Clooparrowright) |  `$ \looparrowright $`   | ![\leftrightsquigarrow](https://math.jianshu.com/math?formula=%5Cleftrightsquigarrow) | `$ \leftrightsquigarrow $` |
  | ![\curvearrowleft](https://math.jianshu.com/math?formula=%5Ccurvearrowleft) |  `$ \curvearrowleft $`  | ![\curvearrowright](https://math.jianshu.com/math?formula=%5Ccurvearrowright) |  `$ \curvearrowright $`  |                                                              |                            |
  | ![\circlearrowleft](https://math.jianshu.com/math?formula=%5Ccirclearrowleft) | `$ \circlearrowleft $`  | ![\circlearrowright](https://math.jianshu.com/math?formula=%5Ccirclearrowright) | `$ \circlearrowright $`  |                                                              |                            |

  #### 表3.13 AMS 二元否定关系符和箭头

  |                             符号                             |        命令         |                             符号                             |        命令         |                             符号                             |          命令           |
  | :----------------------------------------------------------: | :-----------------: | :----------------------------------------------------------: | :-----------------: | :----------------------------------------------------------: | :---------------------: |
  |  ![\nless](https://math.jianshu.com/math?formula=%5Cnless)   |    `$ \nless $`     |   ![\ngtr](https://math.jianshu.com/math?formula=%5Cngtr)    |     `$ \ngtr $`     | ![\varsubsetneqq](https://math.jianshu.com/math?formula=%5Cvarsubsetneqq) |  `$ \varsubsetneqq $`   |
  |   ![\lneq](https://math.jianshu.com/math?formula=%5Clneq)    |     `$ \lneq $`     |   ![\gneq](https://math.jianshu.com/math?formula=%5Cgneq)    |     `$ \gneq $`     | ![\varsupsetneqq](https://math.jianshu.com/math?formula=%5Cvarsupsetneqq) |  `$ \varsupsetneqq $`   |
  |   ![\nleq](https://math.jianshu.com/math?formula=%5Cnleq)    |     `$ \nleq $`     |   ![\ngeq](https://math.jianshu.com/math?formula=%5Cngeq)    |     `$ \ngeq $`     | ![\nsubseteqq](https://math.jianshu.com/math?formula=%5Cnsubseteqq) |    `$ \nsubseteqq $`    |
  | ![\nleqslant](https://math.jianshu.com/math?formula=%5Cnleqslant) |  `$ \nleqslant $`   | ![\ngeqslant](https://math.jianshu.com/math?formula=%5Cngeqslant) |  `$ \ngeqslant $`   | ![\nsupseteqq](https://math.jianshu.com/math?formula=%5Cnsupseteqq) |    `$ \nsupseteqq $`    |
  |  ![\lneqq](https://math.jianshu.com/math?formula=%5Clneqq)   |    `$ \lneqq $`     |  ![\gneqq](https://math.jianshu.com/math?formula=%5Cgneqq)   |    `$ \gneqq $`     |   ![\nmid](https://math.jianshu.com/math?formula=%5Cnmid)    |       `$ \nmid $`       |
  | ![\lvertneqq](https://math.jianshu.com/math?formula=%5Clvertneqq) |  `$ \lvertneqq $`   | ![\gvertneqq](https://math.jianshu.com/math?formula=%5Cgvertneqq) |  `$ \gvertneqq $`   | ![\nparallel](https://math.jianshu.com/math?formula=%5Cnparallel) |    `$ \nparallel $`     |
  |  ![\nleqq](https://math.jianshu.com/math?formula=%5Cnleqq)   |    `$ \nleqq $`     |  ![\ngeqq](https://math.jianshu.com/math?formula=%5Cngeqq)   |    `$ \ngeqq $`     | ![\nshortmid](https://math.jianshu.com/math?formula=%5Cnshortmid) |    `$ \nshortmid $`     |
  |  ![\lnsim](https://math.jianshu.com/math?formula=%5Clnsim)   |    `$ \lnsim $`     |  ![\gnsim](https://math.jianshu.com/math?formula=%5Cgnsim)   |    `$ \gnsim $`     | ![\nshortparallel](https://math.jianshu.com/math?formula=%5Cnshortparallel) |  `$ \nshortparallel $`  |
  | ![\lnapprox](https://math.jianshu.com/math?formula=%5Clnapprox) |   `$ \lnapprox $`   | ![\gnapprox](https://math.jianshu.com/math?formula=%5Cgnapprox) |   `$ \gnapprox $`   |   ![\nsim](https://math.jianshu.com/math?formula=%5Cnsim)    |      `$ \nsimd $`       |
  |  ![\nprec](https://math.jianshu.com/math?formula=%5Cnprec)   |    `$ \nprec $`     |  ![\nsucc](https://math.jianshu.com/math?formula=%5Cnsucc)   |    `$ \nsucc $`     |  ![\ncong](https://math.jianshu.com/math?formula=%5Cncong)   |      `$ \ncong $`       |
  | ![\npreceq](https://math.jianshu.com/math?formula=%5Cnpreceq) |   `$ \npreceq $`    | ![\nsucceq](https://math.jianshu.com/math?formula=%5Cnsucceq) |   `$ \nsucceq $`    | ![\nvdash](https://math.jianshu.com/math?formula=%5Cnvdash)  |      `$ \nvdash $`      |
  | ![\precneqq](https://math.jianshu.com/math?formula=%5Cprecneqq) |   `$ \precneqq $`   | ![\succneqq](https://math.jianshu.com/math?formula=%5Csuccneqq) |   `$ \succneqq $`   | ![\nvDash](https://math.jianshu.com/math?formula=%5CnvDash)  |      `$ \nvDash $`      |
  | ![\precnsim](https://math.jianshu.com/math?formula=%5Cprecnsim) |   `$ \precnsim $`   | ![\succnsim](https://math.jianshu.com/math?formula=%5Csuccnsim) |   `$ \succnsim $`   | ![\nVdash](https://math.jianshu.com/math?formula=%5CnVdash)  |      `$ \nVdash $`      |
  | ![\precnapprox](https://math.jianshu.com/math?formula=%5Cprecnapprox) | `$ \precnapprox $`  | ![\succnapprox](https://math.jianshu.com/math?formula=%5Csuccnapprox) | `$ \succnapprox $`  | ![\nVDash](https://math.jianshu.com/math?formula=%5CnVDash)  |      `$ \nVDash $`      |
  | ![\subsetneq](https://math.jianshu.com/math?formula=%5Csubsetneq) |  `$ \subsetneq $`   | ![\supsetneq](https://math.jianshu.com/math?formula=%5Csupsetneq) |  `$ \supsetneq $`   | ![\ntriangleleft](https://math.jianshu.com/math?formula=%5Cntriangleleft) |  `$ \ntriangleleft $`   |
  | ![\varsubsetneq](https://math.jianshu.com/math?formula=%5Cvarsubsetneq) | `$ \varsubsetneq $` | ![\varsupsetneq](https://math.jianshu.com/math?formula=%5Cvarsupsetneq) | `$ \varsupsetneq $` | ![\ntriangleright](https://math.jianshu.com/math?formula=%5Cntriangleright) | `$ \ntrianglerightt $`  |
  | ![\nsubseteq](https://math.jianshu.com/math?formula=%5Cnsubseteq) |  `$ \nsubseteq $`   | ![\nsupseteq](https://math.jianshu.com/math?formula=%5Cnsupseteq) |  `$ \nsupseteq $`   | ![\ntrianglelefteq](https://math.jianshu.com/math?formula=%5Cntrianglelefteq) | `$ \ntrianglelefteq $`  |
  | ![\subsetneqq](https://math.jianshu.com/math?formula=%5Csubsetneqq) |  `$ \subsetneqq $`  | ![\supsetneqq](https://math.jianshu.com/math?formula=%5Csupsetneqq) |  `$ \supsetneqq $`  | ![\ntrianglerighteq](https://math.jianshu.com/math?formula=%5Cntrianglerighteq) | `$ \ntrianglerighteq $` |
  | ![\nleftarrow](https://math.jianshu.com/math?formula=%5Cnleftarrow) |  `$ \nleftarrow $`  | ![\nrightarrow](https://math.jianshu.com/math?formula=%5Cnrightarrow) |  `$ nrightarrow $`  | ![\nleftrightarrow](https://math.jianshu.com/math?formula=%5Cnleftrightarrow) | `$ \nleftrightarrow $`  |
  | ![\nLeftarrow](https://math.jianshu.com/math?formula=%5CnLeftarrow) |  `$ \nLeftarrow $`  | ![\nRightarrow](https://math.jianshu.com/math?formula=%5CnRightarrow) |  `$ nRightarrow $`  | ![\nLeftrightarrow](https://math.jianshu.com/math?formula=%5CnLeftrightarrow) | `$ \nLeftrightarrow $`  |

  #### 表3.14 AMS 二元运算符

  |                             符号                             |             命令              |                             符号                             |           命令            |                             符号                             |         命令          |
  | :----------------------------------------------------------: | :---------------------------: | :----------------------------------------------------------: | :-----------------------: | :----------------------------------------------------------: | :-------------------: |
  | ![\dotplus](https://math.jianshu.com/math?formula=%5Cdotplus) |        `$ \dotplus $`         | ![\centerdot](https://math.jianshu.com/math?formula=%5Ccenterdot) |     `$ \centerdot $`      | ![\intercal](https://math.jianshu.com/math?formula=%5Cintercal) |    `$ \intercal $`    |
  | ![\ltimes](https://math.jianshu.com/math?formula=%5Cltimes)  |         `$ \ltimes $`         | ![\rtimes](https://math.jianshu.com/math?formula=%5Crtimes)  |       `$ \rtimes $`       | ![\divideontimes](https://math.jianshu.com/math?formula=%5Cdivideontimes) | `$ \divideontimes $`  |
  |    ![\Cup](https://math.jianshu.com/math?formula=%5CCup)     | `$ \Cup $`   `$ \doublecup $` | ![\doublecap](https://math.jianshu.com/math?formula=%5Cdoublecap) | `\Cap`   `$ \doublecap $` | ![\smallsetminus](https://math.jianshu.com/math?formula=%5Csmallsetminus) | `$ \smallsetminus $`  |
  | ![\veebar](https://math.jianshu.com/math?formula=%5Cveebar)  |         `$ \veebar $`         | ![\barwedge](https://math.jianshu.com/math?formula=%5Cbarwedge) |      `$ \barwedge $`      | ![\doublebarwedge](https://math.jianshu.com/math?formula=%5Cdoublebarwedge) | `$ \doublebarwedge $` |
  | ![\boxplus](https://math.jianshu.com/math?formula=%5Cboxplus) |        `$ \boxplus $`         | ![\boxminus](https://math.jianshu.com/math?formula=%5Cboxminus) |      `$ \boxminus $`      | ![\circleddash](https://math.jianshu.com/math?formula=%5Ccircleddash) |  `$ \circleddash $`   |
  | ![\boxtimes](https://math.jianshu.com/math?formula=%5Cboxtimes) |        `$ \boxtimes $`        | ![\boxdot](https://math.jianshu.com/math?formula=%5Cboxdot)  |       `$ \boxdot $`       | ![\circledcirc](https://math.jianshu.com/math?formula=%5Ccircledcirc) |  `$ \circledcirc $`   |
  | ![\leftthreetimes](https://math.jianshu.com/math?formula=%5Cleftthreetimes) |     `$ \leftthreetimes $`     | ![\rightthreetimes](https://math.jianshu.com/math?formula=%5Crightthreetimes) |  `$ \rightthreetimes $`   | ![\circledast](https://math.jianshu.com/math?formula=%5Ccircledast) |   `$ \circledast $`   |
  | ![\curlyvee](https://math.jianshu.com/math?formula=%5Ccurlyvee) |        `$ \curlyvee $`        | ![\curlywedge](https://math.jianshu.com/math?formula=%5Ccurlywedge) |     `$ \curlywedge $`     |                                                              |                       |

  #### 表3.15 AMS 其它符号

  |                             符号                             |        命令         |                             符号                             |           命令           |                             符号                             |         命令          |
  | :----------------------------------------------------------: | :-----------------: | :----------------------------------------------------------: | :----------------------: | :----------------------------------------------------------: | :-------------------: |
  |   ![\hbar](https://math.jianshu.com/math?formula=%5Chbar)    |     `$ \hbar $`     | ![\hslash](https://math.jianshu.com/math?formula=%5Chslash)  |      `$ \hslash $`       |   ![\Bbbk](https://math.jianshu.com/math?formula=%5CBbbk)    |      `$ \Bbbk $`      |
  | ![\square](https://math.jianshu.com/math?formula=%5Csquare)  |    `$ \square $`    | ![\blacksquare](https://math.jianshu.com/math?formula=%5Cblacksquare) |    `$ \blacksquare $`    | ![\circledS](https://math.jianshu.com/math?formula=%5CcircledS) |    `$ \circledS $`    |
  | ![\vartriangle](https://math.jianshu.com/math?formula=%5Cvartriangle) | `$ \vartriangle $`  | ![\blacktriangle](https://math.jianshu.com/math?formula=%5Cblacktriangle) |   `$ \blacktriangle $`   | ![\complement](https://math.jianshu.com/math?formula=%5Ccomplement) |   `$ \complement $`   |
  | ![\triangledown](https://math.jianshu.com/math?formula=%5Ctriangledown) | `$ \triangledown $` | ![\blacktriangledown](https://math.jianshu.com/math?formula=%5Cblacktriangledown) | `$ \blacktriangledown $` |   ![\Game](https://math.jianshu.com/math?formula=%5CGame)    |       `$ \Game`       |
  | ![\lozenge](https://math.jianshu.com/math?formula=%5Clozenge) |   `$ \lozenge $`    | ![\blacklozenge](https://math.jianshu.com/math?formula=%5Cblacklozenge) |   `$ \blacklozenge $`    | ![\bigstar](https://math.jianshu.com/math?formula=%5Cbigstar) |    `$ \bigstar $`     |
  |  ![\angle](https://math.jianshu.com/math?formula=%5Cangle)   |    `$ \angle $`     | ![\measuredangle](https://math.jianshu.com/math?formula=%5Cmeasuredangle) |   `$ \measuredangle $`   | ![\sphericalangle](https://math.jianshu.com/math?formula=%5Csphericalangle) | `$ \sphericalangle $` |
  | ![\diagup](https://math.jianshu.com/math?formula=%5Cdiagup)  |    `$ \diagup $`    | ![\diagdown](https://math.jianshu.com/math?formula=%5Cdiagdown) |     `$ \diagdown $`      | ![\backprime](https://math.jianshu.com/math?formula=%5Cbackprime) |   `$ \backprime $`    |
  | ![\nexists](https://math.jianshu.com/math?formula=%5Cnexists) |   `$ \nexists $`    |   ![\Finv](https://math.jianshu.com/math?formula=%5CFinv)    |       `$ \Finv $`        | ![\varnothing](https://math.jianshu.com/math?formula=%5Cvarnothing) |   `$ \varnothing $`   |
  |    ![\eth](https://math.jianshu.com/math?formula=%5Ceth)     |     `$ \eth $`      |    ![\mho](https://math.jianshu.com/math?formula=%5Cmho)     |        `$ \mho $`        |                                                              |                       |

  #### 表3.16 数学字母

  |                             符号                             |          命令           |
  | :----------------------------------------------------------: | :---------------------: |
  | ![\mathrm{ABCdef}](https://math.jianshu.com/math?formula=%5Cmathrm%7BABCdef%7D) |  `$ \mathrm{ABCdef} $`  |
  | ![\mathit{ABCdef}](https://math.jianshu.com/math?formula=%5Cmathit%7BABCdef%7D) |  `$ \mathit{ABCdef} $`  |
  | ![\mathcal{ABCdef}](https://math.jianshu.com/math?formula=%5Cmathcal%7BABCdef%7D) | `$ \mathcal{ABCdef} $`  |
  | ![\mathscr{ABCdef}](https://math.jianshu.com/math?formula=%5Cmathscr%7BABCdef%7D) | `$ \mathscr{ABCdef} $`  |
  | ![\mathfrak{ABCdef}](https://math.jianshu.com/math?formula=%5Cmathfrak%7BABCdef%7D) | `$ \mathfrak{ABCdef} $` |
  | ![\mathbb{ABCdef}](https://math.jianshu.com/math?formula=%5Cmathbb%7BABCdef%7D) | `$ \mathbbk{ABCdef} $`  |