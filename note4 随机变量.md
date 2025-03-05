# 4 随机变量
我们已经有了离散概率空间上的随机变量的概念. 本章我们要在一般的概率空间上定义随机变量并研究它们的各种性质.

[TOC]




## 4.1 基本概念
### 4.1.1 原相
> 设$S_1, S_2$是两个集合, $f: S_1 \mapsto S_2$. 对 $A \subset S_2$ , 令
> $$f^{−1}(A) := \{x \in S_1 : f(x) \in A\}$$
> 称为A在f下的原像

原像的一个简单有用的性质是它*保持所有的运算关系不变*.

设$\mathscr{S}_2$是$S_2$中的集类. 记
$$f^{−1}(\mathscr{S}_2) := \{f^{−1}(A): A \in S_2\}$$

则$f^{−1}(\mathscr{S}_2)$是$S_1$中的集类. 当$\mathscr{S}_2$本身为$\sigma$-代数时, $f^{−1}(\mathscr{S}_2)$也为$\sigma$-代数. 我们还有

> 设$\mathscr{S}_2$是$S_2$中的集类. , 则
> $$
> \sigma(f^{−1}(\mathscr{S}_2)) = f^{−1}(\sigma(\mathscr{S}_2))
> $$

### 4.1.2 博雷尔代数
在欧氏空间上有一个经典的$\sigma$-代数, 称为Borel $σ$-代数. 我们现在来介绍它. 让我们从最简单的一维情况$\mathbb{R}$开始.  
对$x \in \mathbb{R}, \rho > 0$, 令
$$B(x, \rho) := \{y : |y − x| < \rho\}$$
称为以$x$为中心$\rho$为半径的开球.

设$O \subset R$. 如果
$$x \in O \Rightarrow \exist\rho > 0 使 B(x, \rho) ⊂ O$$ 
(对于$O$中的每个点，都可以找到一个以该点为中心的小球完全包含在$O$内)  
则$O$称为**开集**.  

与开集对立的概念是闭集. 
一个集合$C, x \in \mathbb{R}$, 如果对某个$x$
$$\forall \rho > 0, 都有C \cap B(x, \rho) \neq \emptyset$$
称$x$为$C$的**聚点**. 如果$C$包含它所有的聚点, 则称为**闭集**. 

我们有
> $$C为闭集 \Leftrightarrow C^c为开集$$

以$\mathscr{O}$表示$\mathbb{R}$上的全体开集, $\mathscr{B}$表示$\mathscr{O}$生成的$\sigma$-代数:
$$ \mathscr{B} := \sigma(\mathscr{O})$$
称$\mathscr{B}$为(一维)Borel σ-代数.  

以$O^c$表示闭集全体. 由上一命题, 我们有
> $$\mathscr{B} = \sigma(O^c)$$

我们注意到$\forall x \in \mathbb{R}$, $x$是闭集, 所以任意单点集$\{x\} \in \mathscr{B}$.

### 4.1.3 博雷尔代数的生成
不管开集或者闭集, 其结构都相当复杂. 我们当然希望找到一些结构简单的集合来生成$\mathscr{B}$. 这就是我们下面要做的事情.

#### 4.1.3.1 开区间生成
对$a,b$满足$\forall −\infty \leqslant a \leqslant b \leqslant \infty$, 以$(a, b)$表示开区间:
$$(a, b) := \{x \in \mathbb{R} : a < x < b\}$$
$\Pi_1$表示所有这样的开区间构成的集类:
$$\Pi_1 := \{(a, b) : −\infty \leqslant a \leqslant b \leqslant \infty\}$$
因为$(a, b) \cup (c, d) = (a \vee c, b \wedge d)$ (若$a \vee c \geqslant b \wedge d$, 则视为$\emptyset$), 所以$\Pi_1$为$\pi$- 类.  
令$\mathscr{C} := \{B(x, \rho) : x \in \mathbb{Q}, \rho \in \mathbb{Q}^{+}\}$.  
因为$\mathbb{Q}$为可数集, 所以$\mathscr{C}$为可数集.

> 设$O$是开集, 则$\exist 开球B_i, i \in I$, 其中$I$是**可数集**, 使得
> $$O = \bigcup_{i \in I}B_i$$
由此命题, $\mathscr{O} \subset \sigma(\Pi_1)$ , 因此我们有
$$\mathscr{B} = \sigma(\Pi_1)$$

#### 4.1.3.2 左开右闭区间生成
仍然对$\forall -\infty \leqslant a \leqslant b < \infty$, 以$(a, b]$表示左开右闭的区间
$$(a, b] := \{x \in \mathbb{R} : a < x \leqslant b\}$$
再约定$(a, \infty] := (a, \infty)$


以$\Pi_2$表示这样的区间全体:
$$\Pi_2 := \{(a, b] : −\infty \leqslant a \leqslant b \leqslant \infty\}$$
显然$\Pi_2$也是$\pi$-类.

我们来看看$\sigma(\Pi_2)$是什么. 由于
$$(a, b] = (a, b) \cup \{b\}$$
所以$(a, b] \in \mathscr{B}$, 故$\sigma(\Pi_2) \subset \mathscr{B}$. 又由于
$$(a, b) = \bigcup_{i=1}^n(a, b - \frac{1}{n}]$$
所以
$$ \Pi_1 \subset \sigma(\Pi_2) $$
所以
$$ \mathscr{B} = \sigma(\Pi_1) \subset \sigma(\Pi_2) $$
于是
$$ \mathscr{B} = \sigma(\Pi_2)$$

### 4.1.3.3 闭区间生成
令
$$\Pi_3 := \{[a, b] : −\infty \leqslant a \leqslant b \leqslant \infty\}$$
这里同样约定$[−\infty, \infty] = (−\infty, \infty)$
由于$[a, b]$是闭集, 所以
$$\sigma(\Pi_3) \subset \mathscr{B}1$$

又由于
$$(a, b) = \bigcup_{i=1}^n [a + \frac1n, b − \frac1n]$$

所以
$$\sigma(\Pi_3) \supset \sigma(\Pi_1) = \mathscr{B}$$

所以
$$ \mathscr{B} = \sigma(\Pi_3)$$

### 4.1.3.4 左闭右开区间生成
再令
$$\Pi_4 := \{[a, b） : −\infty \leqslant a \leqslant b \leqslant \infty\}$$
在$-\infty$处做同样的约定$[-\infty,a)=(-\infty,a)$. 和$\Pi_2$同样可证
$$\mathscr{B} = σ(\Pi_4)$$

### 4.1.3.5 一侧含无限的区间生成
令
$$\Pi_5 = \{(−\infty, a), −\infty < a \leqslant \infty\}$$
由于$\Pi_5 \subset \Pi_4$, 所以
$$\Pi_5 \subset \sigma(\Pi_4) = \mathscr{B}$$
所以
$$\sigma(\Pi_5) \subset \mathscr{B}$$
又因为
$$[a, b) = (−\infty, b) − (−\infty, a)$$
所以
$$\Pi_4 \subset \sigma(\Pi_5)$$
因此
$$\mathscr{B} = \sigma(\Pi_4) = \sigma(\Pi_5)$$

类似地，
令
$$\Pi_6 = \{(−\infty, a], −\infty < a \leqslant \infty\}$$
$$\Pi_7 = \{(a,\infty), −\infty \leqslant a < \infty\}$$
$$\Pi_8 = \{[a,\infty), −\infty \leqslant a < \infty\}$$
也可证明
$$\mathscr{B} = \sigma(\Pi_6) = \sigma(\Pi_7) = \sigma(\Pi_8)$$



### 4.1.4 博雷尔函数
一般地, 对任意$n \in \mathbb{N}^{+}$, 以$\mathscr{B}^n$表示n-维Borel $\sigma$-代数. 有了Borel $\sigma$-代数的概念, 就有
了Borel可测函数的概念.

> 设$f: \mathbb{R}^n \to \mathbb{R}^m$. 若
> $$f^{−1}(B) ∈ \mathscr{B}^n, \forall B \in \mathscr{B}^m$$
> 则称$f$为Borel可测函数, 简称Borel函数.

上述定义中的条件常常简记为
$$f^{−1}(\mathscr{B}^m) \subset \mathscr{B}^n$$


Borel函数复合Borel函数仍然是Borel函数, 即
> 设$\phi: \mathbb{R}^n \to \mathbb{R}^m$及$\psi: \mathbb{R}^m \to \mathbb{R}^l$均为 Borel函数, 则$\psi \circ \phi : \mathbb{R}^n \to \mathbb{R}^l$也为Borel函数.

我们可以简化验证一个函数是Borel函数的手续. 首先我们有:
> 设$\mathscr{C}$是$\mathbb{R}^m$的某些子集构成的集类, 且$\sigma(\mathscr{C}) = \mathscr{B}^m$. 则$\phi : \mathbb{R}^n \to \mathbb{R}^m$ 是Borel函数的充要条件是$\phi^{-1}(\mathscr{C}) \subset \mathscr{B}^n$.

我们知道有很多这样的集类. 例如可取$\mathscr{C}$为开集全体, 或者闭集全体, 或者以及上面所定义的$\Pi_i^m, i = 1, \dots , 8$.

> $\phi = (\phi_1, \dots , \phi_m) : \mathbb{R}^n \to \mathbb{R}^m$为Borel函数的充要条件是每个$\phi_i, i = 1, 2, \dots , m$,都是Borel函数.

有了这个结果, 很多命题的证明往往退化到只需对数值Borel函数证明.
数值Borel函数包含了哪些函数呢? 首先, 它包含了**连续函数**, 即我们有:

> 设$\phi : \mathbb{R}^n \to \mathbb{R}$连续, 则$\phi$为Borel函数

其次, 它包含了Boreal集的**示性函数**
> 对任何一个$\mathbb{R}^n$上的Borel集$A \in \mathscr{B}^n$, 其示性函数
> $$f(x) := I_{A}(x)$$
> 也是Borel函数.

> 设$a_1, \dots , a_k \in \mathbb{R}$, $A_1, \dots , A_k \in \mathscr{B}^n$. 函数
> $$φ(x1, · · · , xn) := \sum_{i=1}^ka_iI_{A_i}(x_1, \dots , x_n)$$
> 也为Borel函数.

由于$(y_1, \dots , y_k) \to a_1y_1 + \dots + a_ky_k$ 为连续函数, 且$y_i = I_{A_i}(x)$是Borel函数，由复合Borel函数仍然是Borel函数得证。

这样的函数结构简单, 因此称为**简单Borel函数**.  
并不是所有的Borel函数都是简单Borel函数, 当然. 不过, 简单Borel函数却可以逼近任何Borel函数. 这是一个非常有用的结果, 其精确叙述如下:
> 设$f$为$\mathbb{R}^n$上的数值Borel函数, 则存在一列简单Borel函数$f_k$, 使得
> $$\lim_{k\to\infty}f_k(x) = f(x), \forall x \in \mathbb{R}^n$$

设f ⩾ 0. 令
$$f_k(x) := \sum_{i=0}^{2^{2k−1}}i2^{−k}I_{f \in [i2^{−k},(i+1)2^{−k})}(x) + 2^kI_{f \geqslant 2^k}(x)$$
易证fk满足要求.

### 4.1.5 随机变量
将Borel函数定义中的$(\mathbb{R}^m, \mathscr{B}^m)$换为概率空间$(\Omega, \mathscr{F}, P)$中的$(\Omega, \mathscr{F})$, 再取$n = 1$, 就得到随机变量的定义. 不过为方便起见, 我们允许随机变量取$\pm\infty$值
> 函数$\xi : \Omega \to \bar{\mathbb{R}} := [−\infty, +\infty]$若满足
> $$\xi^{−1}(A) := \{\omega : \xi(\omega) \in A\} \in \mathscr{F}, \forall A \in \bar{\mathscr{B}}$$
> 则称$\xi$为随机变量, 其中
> $$\bar{\mathscr{B}} := \sigma(\mathscr{B}, \{−\infty\}, \{\infty\})$$
>若进一步有$P(\lvert\xi\rvert = \infty) = 0$(或换一种写法, $\lvert\xi\rvert < \infty~a.s.$), 则称$\xi$为实值随机变量.

多维随机变量可类似定义:
> 函数$\xi : \Omega \to \mathbb{R}^n$ 若满足
> $$\xi^{−1}(A) := \{\omega : \xi(\omega) \in A\} \in \mathscr{F}, \forall A \in \mathscr{B}^n$$
> 则称$\xi$为n维随机变量.

我们注意到, 在随机变量的定义中, P是不起作用的.   
此外, 我们有下面的等价性条件:  
$\xi$为随机变量  $\Leftrightarrow$ $\forall$开集$O$, $\xi
^{−1}(O) \in \mathscr{F}$ $\Leftrightarrow$ $\exist i \in \{1, \dots , 8\}$, 使得$\xi^{-1}(A) \in \mathscr{F}, \forall A ∈ \Pi_i$

有了这个结果, 我们就很容易地知道, 判断一个多维函数是不是随机变量, 只要看各个分量即可. 即我们有:
>$\xi = (\xi_1, \dots , \xi_n)$是n维随机变量的充要条件是: 对任意$i$, $\xi_i$是实值随机变量.

考虑复合函数，有
> 设$\xi$是$n$维随机变量, $\phi : \mathbb{R}^n \to \mathbb{R}^m$为Borel函数, 则$\phi(\xi)$为m维随机变量.


## 4.2 分布函数
设$\xi$是实值随机变量. 对$A \in \mathscr{B}$, 由于$\xi^{−1}(A) \in \mathscr{F}$, 所以$P(\xi^{−1}(A))$是有意义的. 因此可定义
$$\mu(A) := P(\xi^{−1}(A))$$
易证$\mu$是$(\mathbb{R}, \mathscr{B})$上的概率, 因此$(\mathbb{R}, \mathscr{B}, \mu)$是概率空间. $\mu$称为$\xi$的概率分布, 因为它反映了$\xi$的值是依什么概率分布的.

对实值随机变量$\xi$, 定义其分布函数为
$$F_{\xi}(x) := P(\xi \geqslant x)$$
在不发生混淆的情况下, 往往简写为$F$. 分布函数和概率分布的关系是：
$$F(x) = \mu((−\infty, x])$$

任意一个实值随机变量的分布函数F都具有下列性质:
> - (i) $F : \mathbb{R} \to [0, 1]$
> - (ii) $F$单调上升且在任意一点右连续, 有左极限；
> - (iii) $F(−\infty) := \lim_{x \to -\infty}F(x) = 0$, $F(+\infty) := \lim_{x \to +\infty}F(x) = 1$

反过来, 设$F$是分布函数, 则有唯一一个概率$\mu$, 使得$F$是$\mu$的分布函数. 可以证明$\mu$是由$F$唯一决定的, 即我们有
> 设$\mu, \nu$是$(\mathbb{R}^m, \mathscr{B}^m)$上的两个概率. 若
> $$\mu((−\infty, a]) = \nu((−\infty, a]), \forall a \in \mathbb{R}^m$$
> 则$\mu \equiv \nu$.

因此, $(\mathbb{R}, \mathscr{B})$上的概率和$\mathbb{R}$上的分布函数是一一对应的. 如果随机变量$\xi, \eta$的概率分布一样, 我们称$\xi, \eta$同分布. 显然, 这等价于$\xi, \eta$的分布函数$F_{\xi}, F_{\eta}$是一样的.

## 4.3 随机变量分类

根据分布函数的性质, 可将随机变量分为离散型随机变量、连续型随机变量.

### 4.3.1 离散型随机变量
#### 4.3.1.1 分布列与分布函数
> 如果随机变量$\xi$的值域为可数集$\{x_1, x_2, \dots \}$, 则称$\xi$为**离散型随机变量**, 其分布函数$F(x)$称为**离散型分布**. 此时有
> $$\Delta F(x_i) := F(x_i) − F(x_i^{−}) = P(\xi = x_i) > 0$$
> 其中$F(x^{−})$是$F$在$x$的左极限. 我们称$\{(x_k, p_k), k = 1, 2, \dots \}$为$\xi$的**分布列**, 其中$p_k := P(\xi = x_k)$. 

由上式, 由分布函数也可唯一地确定分布列.   

分布列包含$\xi$的可能取值$x_1, x_2, \dots$和分别取这些值的概率$p_1, p_2, \dots$两方面的信息. 显然
$$p_k > 0, \forall k \geqslant 1, \text{且} \sum_{k}p_k = 1$$

反之, 对所有满足上面两个性质的$p_k$, 结合一个可列点集$\{x_1, x_2, \dots \}$, 都可以构造一个概率空间和定义在其上的随机变量$\xi$, 使得它以$\{(x_k, p_k), k = 1, 2, \dots \}$为分布列.  
设$\xi$的分布列为$\{(x_k, p_k), k = 1, 2, \dots \}$, 那么其分布函数为
$$F(x) = \sum_{k:x_k \leqslant x}p_k$$
所以由分布列可以唯一地确定分布函数.   

因此我们得到:
> 对离散分布而言, 分布函数和分布列是相互唯一确定的.

#### 4.3.1.2 Bernoulli分布
设$p \in (0, 1)$. 若$\xi$的分布函数为
$$
F(x) = \begin{cases}
0, x < 0\\
1-p, 0 \leqslant x < 1\\
1, x \geqslant 1
\end{cases}
$$
则称$\xi$服从参数为$p$的Bernoulli分布, 记为$\xi \sim \mathcal{B}(p)$. 此时$\xi$的分布列为
$$\{(0, q), (1, p)\}$$

#### 4.3.1.3 二项分布  
设p ∈ (0, 1), q := 1 − p. 若$\xi$的分布列为
$$\{(k, p_k), k = 0, \dots , n\}$$
其中
$$p_k := C_n^kp^kq^{n−k}$$
则称$\xi$服从二项分布, 记为$\xi \sim \mathcal{B}(n, p)$.  
显然, $\mathcal{B}(1, p) = \mathcal{B}(p)$.

#### 4.3.1.4 泊松分布  
设$\lambda > 0$. 若$\xi$的分布列为
$$\{(k, p_k), k = 0, 1, \dots \}$$
其中
$$p_k := \frac{\lambda^k}{k!}e^{-\lambda}$$
则称$\xi$服从Poisson分布, 记为$\xi \sim \mathcal{P}(\lambda)$.

#### 4.3.1.5 几何分布.
设$p \in (0, 1), q := 1 - p$. 若$\xi$的分布列为
$$\{(k, p_k), k = 1, 2, \dots \}$$
其中
$$p_k := pq^{k-1}$$
则称$\xi$服从几何分布, 记为$\xi \sim \mathcal{Ge}(p)$.

### 4.3.2 连续型随机变量
#### 4.3.2.1 密度函数PDF与分布函数CDF
设$F$是随机变量$\xi$的分布函数. 由于$F$单调上升, 故至多只有可数个间断点. 令A为其间断点全体, 即
$$A := \{x : \Delta F(x) := F(x) - F(x^{-}) > 0\}$$

$\xi$是离散型随机变量的充要条件是
$$\sum_{x \in A} \Delta F(x) = 1$$
此时$\xi$的值域即$A$.

与此对立的情况是$A$为空集, 此时$F$是连续函数. 在这种情况中, 有一种更加特别也更加引人注目的情况, 即$F$是绝对连续函数, 亦即它可以表示为某个可积函数的不定积分.  
> 如果随机变量$\xi$的分布函数$F(x)$满足
> $$F(x) = \int_{−\infty}^xp(t)dt, \forall x \in \mathbb{R}$$
> 其中$p(\cdot)$是非负Riemann可积函数, 则称$F(x)$为**连续型分布**, $\xi$为**连续型随机变量**, $p(\cdot)$为$\xi$的(或称$F$的)**密度函数**(或分布密度).  

- 本书涉及到的密度函数都是分段连续函数, 所以都是Riemann可积的.
- 在$p$的连续点上, 有$p(x) = F^{\prime}(x)$. 所以在这些点上, $p$由$F$唯一确定.
- 在任何一个Lebesgue零测集上改变p的值都不会影响这个等式, 所以密度函数$p$不是“绝对唯一的”, 而只是在*几乎处处相等*意义下的唯一.
- 密度函数的直观意义是：当$b - a > 0$很小, $x \in [a, b]$且$x$是$p$的连续点时, 有$P(\xi \in [a, b]) \approx p(x)(b - a)$. 这里之所以强调$x$是$p$的连续点, 是因为$p$在任意一个单点上的值都是可以随意改变的, 因此可以取一个与$\xi$毫无关系的值; 但如果限定$p$在$x$处连续, 则$p(x)$便唯一确定, 无法改变了.

显然, 密度函数满足
$$\int_{-\infty}^{\infty}p(x)dx = 1$$
有必要时, 在有限个点上改变$p$的值, 我们还可以假定——我们将总是这样假定——它满足
$$p(x) ⩾ 0, \forall x \in \mathbb{R}$$
反之, 给定满足上面两个性质的函数$p$, 总可以通过Riemann积分求得函数$F$, 且$F$为一连续型分布函数.  

#### 4.3.2.2 指数分布
黄昏, 村子里的炊烟升起来了, 星星一个接着一个地跳出来, 一个小朋友在地面捕捉它们. 假设他在不同的时间段内捕捉到多少颗星星的事件是相互独立的, 且捕捉到多少星星的概率只与时间的长度有关,而与具体的起止点无关. 我们想知道他为捕捉到第一个星星需要等待的时间的概率分布.  

若以$\xi(t)$记在$[0, t)$内捕捉到的星星颗数, 那么$\xi(s + t) - \xi(t)$就是在$[t, t + s)$内捕捉到的星星数. 注意这里假设的两个特征用数学语言表达出来就是:

- (i) $\forall k \in \mathbb{N}^{+}, \forall 0 = t_0 < t1 < t2 < \dots < t_k, n_1, n_2, \dots , n_k \in \mathbb{N}+$, 事件$\{\xi(t_i) - \xi(t_{i-1}) = n_i\}, i = 1, 2, \dots , k$
相互独立.
- (ii) $\forall m, P(\xi(s + t) - \xi(s) = m)$只与$t$有关而与$s$无关.  

任意如上的计数过程都是一个**Poisson过程**
> 在长度为$t$的任意区间中的事件数服从以$\lambda t$为均值的Poisson分布
> $$P(\xi(s + t) - \xi(s) = m) = \frac{(\lambda t)^m}{m!}e^{-\lambda t}$$
> 称该计数过程为**具有速率$\lambda$**的**Poisson过程**.  

我们将第一个特征称为**独立增量性**, 而把第二个特征称为**平稳性**.

考虑一个Poisson过程, 以$X_1$计首个事件的发生时间. 对$n \geqslant 1$, 以$X_k$计第$k-1$个事件和第$k$个事件之间的时间.我们来考察$\{X_k\}$的分布。  
首先，事件$X_1 > t$发生，当且仅当Poisson过程在区间$[0,t]$中没有事件发生，因此
$$P(X_1 > t) = P(\xi(t) - \xi(0) = 0) = e^{-\lambda t}$$
接下来考虑$X_2$：
$$
\begin{align}
P(X_2 > t \mid X_1 =s) &= P(\xi(s+t) - \xi(s) = 0 \mid \xi(s)=1) \notag\\ 
&= P(\xi(s+t) - \xi(s) = 0) \notag\\
&= e^{-\lambda t} \notag\\
\end{align}
$$
接下来由归纳法易证$X_k, k=1,2,\dots$独立同分布
$$P(X_k <t) = 1 - e^{-\lambda t}$$

这样一个连续型分布, 分布函数为
$$
F(x) = \begin{cases}
0, t < 0\\
1-e^{-\lambda t}, t \geqslant 0
\end{cases}
$$




相应的密度函数为
$$
p(t) = \begin{cases}
0, t < 0\\
\lambda e^{-\lambda t}, t \geqslant 0
\end{cases}
$$
称为参数为$\lambda$的指数分布, 记为$X \sim \mathcal{E}(λ)$

#### 4.3.2.3 正态分布
一般地, 设$\sigma \in \mathbb{R}, \sigma > 0$, 密度函数为
$$
p(x) = \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}
$$
的分布称为参数为$\mu, \sigma^2$的正态分布, 记为$\mathcal{N}(\mu, \sigma^2)$. 称$\mathcal{N}(0, 1)$为标准正态分布.

## 4.4 多维随机变量的分布函数

### 4.4.1 分布函数定义与性质
对多维随机变量, 同样可以考虑其分布函数. 我们以二维为例, 更高维的情况类似.

> 设$\xi, \eta$均为实值随机变量. 令
> $$F_{\xi, \eta}(x, y) := P(\xi \leqslant x, η \leqslant y)$$
> 称$F_{\xi, \eta}(x, y)$为$(\xi, \eta)$的分布函数. 

我们有
- $F_{\xi, \eta}(\infty, \infty) = 1$
- $F_{\xi, \eta}(x, \infty) = F_{\xi}(x), F_{\xi, \eta}(\infty, y) = F_{\eta}(y)$
- $F_{\xi, \eta}(x, -\infty) = 0, F_{\xi, \eta}(-\infty, y) = 0$
- 对固定的$x$而言, $y \mapsto F(x, y)$是单调上升函数, 且是右连左极的. 同理, 对固定的$y$一样.
- 对于$\forall x_1 \leqslant x_2, y_1 \leqslant y_2$, 有$F(x_2, y_2) - F(x_1, y_2) - F(x_2, y_1) + F(x_1, y_1)
= P(x_1 < \xi \leqslant x_2, y_1 < \eta \leqslant y_2) \geqslant 0$

### 4.4.2 多维随机变量分类
多维离散型与连续型随机变量可类似定义. . 我们还是以二维为例

### 4.4.2.1 离散型随机变量

> 一个二维随机变量$(\xi, \eta)$, 若其值域为可数集$\{(x_i
, y_j), i, j = 1, 2, \dots \}$, 则称为离散型的.  

> 此时, 令
> $$p_{ij} := P(\xi = x_i, \eta = y_j )$$
> 则$\{(x_i, y_j), p_{ij}\}$称为$(\xi, \eta)$的分布列.

例如. 多项分布
若每次试验的可能结果为$A_1, \dots , A_r$, 而$P(A_i) = p_i, i = 1, \dots , r, \sum_{i=1}^rp_i = 1$. 
重复这个试验$n$次, 并设这$n$次试验间是相互独立的. 以$\xi_1, \dots, \xi_r$分别记$A_1, \dots , A_r$出现的次数, 则
$$P(\xi_1 = k_1, \xi_2 = k_2, \dots , \xi_r = k_r) = \frac{n!}{\prod_{i=1}^rk_i!}\prod_{i=1}^rp_i^{k_i}$$
其中$k_i \geqslant 0, \sum_{i=1}^rk_i = n$.

### 4.4.2.1 连续型随机变量
而多维连续性随机变量就是, 简言之, 其分布函数可以表示为另一可积函数之不定积分的随机变量. 不过, 由于现在是多元函数, 所以我们得加上一些技术性条件以保证将要涉及的各种运算的通畅性. 具体地说, 我们有：

> 若存在$p: \mathbb{R}^2 \to \mathbb{R}$满足
> - (i) $p(x, y) \geqslant 0$
> - (ii) $p$的间断点只出现在有限多条简单曲线上
> - (iii) $\forall x, y \mapsto p(x, y)$分段连续, $\forall y, x \mapsto p(x, y)$分段连续
> - (iv) 除了有限个例外的u0与v0外, 有
>   $$\lim_{u \to u_0}\int_{-\infty}^{\infty}\lvert p(u, v) - p(u_0, v)\rvert dv = 0$$
>   $$\lim_{v \to v_0}\int_{-\infty}^{\infty}\lvert p(u, v) - p(u, v_0)\rvert du = 0$$
>   使得
>   $$F_{\xi, \eta}(x,y)=\int_{-\infty}^{x}\int_{-\infty}^{y}p(u,v)dudv$$
>   则$F$称为连续型分布, $(\xi, \eta)$称为连续型随机变量, $p$称为$F$或$(\xi, \eta)$的密度函数(或分布密度).

例如. 均匀分布
设$a < b, c < d$. 定义
$$
p(x,y)=\begin{cases}
\frac{1}{(b-a)(d-c)}, a\leqslant x \leqslant b, c\leqslant y \leqslant d\\
0, \text{otherwise}
\end{cases}
$$
则$p$所对应的分布称为$[a, b] \times [c, d]$上的均匀分布.



### 4.4.3 边沿分布
#### 4.4.3.1 定义
当$(\xi, \eta)$的分布函数$F_{\xi, \eta}$给定时, 我们有
$$F_{\xi}(x) = P(\xi \leqslant x, \eta \in \mathbb{R}) = F_{\xi, \eta}(x, \infty)$$
$$F_{\eta}(t) = P(\xi \in \mathbb{R}, \eta \leqslant y) = F_{\xi, \eta}(\infty, y)$$
因此$\xi$与$\eta$的分布也都确定下来了. $F_{\xi}$与$F_{\eta}$于是称为$F$的两个**边沿分布**. 相对应的, $(\xi, \eta)$本来的分布$F_{\xi, \eta}$也往往称为**联合分布**.

#### 4.4.3.2 离散型分布的边沿分布
若$(\xi, \eta)$是离散型的, 分布列为$\{(x_i, y_j ), p_{ij}\}$, 那么$\xi$的值域就是$\{x_i\}$, 且
$$p_{i}^{\xi} := P(\xi = x_i) = \sum_{j}P(\xi = x_i, \eta = y_j ) = \sum_{j}p_{ij}$$
所以$\xi$也是离散型的, 且分布列为$\{(x_i, p_{\xi,i})\}$. 同理$\eta$也是离散型的, 且分布列为$\{(y_j , p_{\eta,j})\}$, 其中
$$p_{j}^{\eta} = \sum_{i}p_{ij}$$

#### 4.4.3.2 连续型分布的边沿分布
若$(\xi, \eta)$为连续型的, 密度函数为$f$. 则$\forall x$,
$$
\begin{align}
F_{\xi}(x) &= P(\xi \leqslant x) \notag\\
&= P(\xi \leqslant x, \eta < \infty)\notag\\
&= \int_{-\infty}^{x}\int_{-\infty}^{\infty}f(u,v)dvdu\notag\\
&= \int_{-\infty}^{x}du\int_{-\infty}^{\infty}f(u,v)dv\notag\\
\end{align}
$$
所以$\xi$也是连续型的, 且密度函数为
$$
p_{\xi}(x) = \int_{-\infty}^{\infty}f(x,v)dv
$$
同理, $\eta$也是连续型的, 且密度函数为
$$
p_{\eta}(y) = \int_{-\infty}^{\infty}f(u,y)du
$$



### 4.4.4 多维正态分布

设$(\xi, \eta)$服从二维正态分布, 即$(\xi, \eta) \sim \mathcal{N}(\mu_1, \mu_2, \sigma_1^2, \sigma_2^2, \rho)$, 其密度函数为
$$
p(x,y) = \frac{1}{2\pi\sigma_1\sigma_2\sqrt{1-\rho^2}}\exp\{-\frac{1}{2(1-\rho^2)}\left[\frac{(x-\mu_1)^2}{\sigma_1^2}+\frac{(y-\mu_2)^2}{\sigma_2^2}-\frac{2\rho(x-\mu_1)(y-\mu_2)}{\sigma_1\sigma_2}\right]\}
$$
现在求其边沿分布. 为此将$p(x,y)$改写为
$$
\begin{align}
p(x,y) &= \frac{1}{\sqrt{2\pi}\sigma_1}\frac{1}{\sqrt{2\pi}\sigma_2\sqrt{1-\rho^2}}
\exp\{-\frac{(x-\mu)^2}{2\sigma_1^2}-\frac{1}{2(1-\rho^2)}\left[\frac{\rho^2(x-\mu_1)^2}{\sigma_1^2}+\frac{(y-\mu_2)^2}{\sigma_2^2}-\frac{2\rho(x-\mu_1)(y-\mu_2)}{\sigma_1\sigma_2}\right]\}\notag\\
&= \frac{1}{\sqrt{2\pi}\sigma_1}
\exp\{-\frac{(x-\mu)^2}{2\sigma_1^2}\}
\frac{1}{\sqrt{2\pi}\sigma_2\sqrt{1-\rho^2}}
\exp\{\frac{1}{2(1-\rho^2)}\left[\frac{\rho(x-\mu_1)}{\sigma_1}-\frac{(y-\mu_2)}{\sigma_2}\right]^2\}
\end{align}\notag\\
$$
则
$$
\begin{align}
p_{\xi}(x) &= \int_{-\infty}^{\infty}p(x,y)dy \notag\\
&=\frac{1}{\sqrt{2\pi}\sigma_1}
\exp\{-\frac{(x-\mu)^2}{2\sigma_1^2}\}
\int_{-\infty}^{\infty}
\frac{1}{\sqrt{2\pi}\sigma_2\sqrt{1-\rho^2}}
\exp\{\frac{1}{2(1-\rho^2)}\left[\frac{\rho(x-\mu_1)}{\sigma_1}-\frac{(y-\mu_2)}{\sigma_2}\right]^2\}
dy \notag\\
&=\frac{1}{\sqrt{2\pi}\sigma_1}
\exp\{-\frac{(x-\mu)^2}{2\sigma_1^2}\}
 \notag\\
\end{align}
$$
对$\eta$同理.

这就是说, 正态分布的边沿分布仍为正态分布, $\xi \sim \mathcal{N}(\mu_1, \sigma_1), \eta\sim\mathcal{N}(\mu_2, \sigma_2)$

注意这两个边沿分布都与$\rho$无关, 这就顺带举出了一个不同的联合分布有相同的边沿分布的例子.  

类似地, 多维正态分布的边沿分布也是正态分布. 但若还用上面的计算来验证这点就比较复杂, 而从后面的特征函数角度来看这就是显然的结论.



## 4.5 条件分布

设$\eta$是随机变量, $A$是事件, 则比对着条件概率, 给定$A$时$\eta$的条件分布很自然定义为
$$P(\eta \leqslant y \mid A) := P(\{\eta \leqslant y\} \cap A)P(A)$$

只要$P(A) > 0$. 受此启发, 假设$\xi$是另一个随机变量, 取$A = \{\xi = x\}$, 则给定$\xi = x$时$\eta$的条件分布理应定义为
$$P(\eta \leqslant y \mid \xi = x) = \frac{P(\{\eta \leqslant y\} \cap \{\xi = x\})}{P(\xi = x)}$$
然而$P(\xi = x)$极有可能等于零(例如当$\xi$为连续型时), 所以不能一概笼统地这样定义, 需要区分情况讨论.

### 4.5.1 离散情形
设$(\xi, \eta)$是离散型的, 分布列为$\{(x_i, y_j ), p_{ij}\}$. 则定义
$$p_{ji}^{\eta \mid \xi} := P(\eta = y_j \mid \xi = x_i) = \frac{P(\eta = y_j,\xi = x_i\})}{P(\xi = x_i)} = \frac{p_{ij}}{p_{i}^{\xi}}$$

称为给定$\xi = x_i$时$\eta$的**条件分布列**. 类似地
$$p_{ij}^{\xi \mid \eta} := P(\xi = x_i \mid \eta = y_j) = \frac{P(\xi = x_i,\eta = y_j\})}{P(\eta = y_j)} = \frac{p_{ij}}{p_{j}^{\eta}}$$

称为给定$\eta = y_j$时$\xi$的条件分布列.

### 4.5.2 连续情形
设$(\xi, \eta)$是连续型随机变量, 分布密度为$p(x, y)$. 此时贝叶斯公式中分式的分母为零, 因此需要通过极限定义其值.
$$
\begin{align}
P(η \leqslant y \mid \xi = x) &:= \lim_{\epsilon \downarrow 0}P(\eta \leqslant y \mid x - \epsilon < \xi < x + \epsilon) \notag\\
&= \lim_{\epsilon \downarrow 0}\frac{P(\eta \leqslant y, x - \epsilon < \xi < x + \epsilon)}{P(x - \epsilon < \xi < x + \epsilon)} \notag\\
&= \lim_{\epsilon \downarrow 0}\frac{\int_{x-\epsilon}^{x+\epsilon}du\int_{-\infty}^{y}p(u,v)dv}{\int_{x-\epsilon}^{x+\epsilon}du\int_{-\infty}^{\infty}p(u,v)dv} \notag\\

\end{align}
$$

当$x$满足$p_{\xi}(x)>0$且$\lim_{u \to x} \int_{-\infty}^{\infty}\lvert p(u,v)-p(x,v) \lvert dv = 0$时，上述极限等于
$$
\frac{\int_{-\infty}^{y}p(x,v)dv}{p_{\xi}(x)}
$$


称上式为给定$\xi=x$时，$\eta$的条件分布函数。

所以，给定$\xi=x$时，$\eta$的条件密度定义为
$$
p_{\eta \mid \xi}(y \mid x) := \begin{cases}\frac{p(x,y)}{p_{xi}(x)},p_{\xi}(x) \neq 0 \\ 0,p_{\xi}(x) = 0 \end{cases}
$$
其中，$p_{\xi}(x)$为$\xi$的边沿密度.



## 4.7 随机变量的函数

设$\xi$是随机变量, $\phi: \mathbb{R} \to \mathbb{R}$为Borel函数. 由4.1.5节的最后一个命题, $\phi(\xi)$仍是一个随机变量. 本节要考虑的问题是, $\xi$的分布能否唯一决定$\phi(\xi)$的分布? 怎么决定?

### 4.7.1 离散型随机变量的函数

首先, 如果$\xi$是离散型的, 那么$\phi(\xi)$也是离散型的. 以$S$记$\xi$的值域, 那么$\phi(\xi)$的值域就是$\phi(S)$. 对任意$y \in \phi(\xi)$,有
$$
P(\phi(\xi)=y) = P(\xi \in \phi^{-1}(\{y\})) = \sum_{x \in S: \phi(x)=y}P(\xi = x)
$$


### 4.7.2 连续型随机变量的函数

$\xi$是连续型时事情会麻烦一些, 也许是麻烦很多. 这时, 首先$\eta = \phi(\xi)$有可能是连续型的, 也有可能是离散型的, 也可能两者都不是 (请自己举个例子). 设$\xi$的密度函数是$p$, 我们来看两种情况及相应的具体例子.

1. 设$\phi(x) = -x$, 则
   $$
   P(\eta \leqslant x) = P(\xi \geqslant -x) = \int_{-x}^{\infty}p(u)du = \int_{-\infty}^{x}p(-u)du
   $$
   所以$\eta$也是连续型的,其分布密度为$p(-x)$.

2. 设$\xi$的值域为一区间$I$(有限或无限, 开或闭, 半开或半闭, 均不限). 设$\phi$是$I$上单调上升函数. (如果单调下降的话, 可先考虑$-\phi$, 然后用情形1的结果. 这时,
   $$
   P(\eta \leqslant x) = \begin{cases}1, x > \max \phi(I) \\ 0, x < \min \phi(I)\end{cases}
   $$
   而当$x \in \phi (I)$时
   $$
   P(\eta \leqslant x) = P(\xi \leqslant \phi^{-1}(x)) = \int_{-\infty}^{\phi^{-1}(x)}p(u)du
   $$
   一般情况下也只能到此而止了. 但如果$\phi$连续可导, 则由变上限积分
   $$
   F^{\prime}(x) = p(\phi^{-1}(x)) \cdot (\phi^{-1}(x))^{\prime}
   $$
   
   
   积分得到
   $$
   F(x) = \int_{-\infty}^x p\left(\phi^{-1}(u)\right)\left(\phi^{-1}(u)\right)^{\prime}du
   $$
   所以$\eta$也是连续型的,其分布密度为
   $$
   p_{\eta}(x) = \begin{cases}
   	0, x \notin \phi(I)\\
   	p\left(\phi^{-1}(u)\right)\left(\phi^{-1}(u)\right)^{\prime}, x \in \phi(I)
   \end{cases}
   $$
   

### 4.7.3 多维随机变量的函数

我们考虑多维情形. 设$\xi$是$\mathbb{R}^n$ -值随机变量, $\phi : \mathbb{R}^n \to \mathbb{R}^m$是Borel函数. 则$\eta := \phi(\xi)$是$\mathbb{R}^m$-值随机变量.

理论上说, $\eta$的分布是由$\xi$的分布和$\phi$唯一确定的. 不过理论是一回事, 实际计算则是另一回事. 要给出$\eta$分布的解析表达式, 只有在零星几种情况是可能的. 不过幸运的是, 这零星的几种情况是非常重要的. 其中最重要的是随机变量之和的分布.  

考虑离散型随机变量：

> 设$(\xi, \eta)$是二维离散型随机变量*.* 分布列为 $\{(x_i , y_j ), p_{ij}, i, j = 1,2,\dots\}$.令$\zeta := \xi + \eta$. 则$\zeta$也是离散型的, 值域为$\{x_i+y_j, i,j = 1,2, \dots\}$, 且对于$z \in \{x_i+y_j, i,j = 1,2, \dots\}$有
>
> 
> $$
> P(\zeta = z) = \sum_{x_i + y_j = z}P_{ij}
> $$

考虑连续型随机变量

> 设$(\xi, \eta)$是二维离散型随机变量, 密度函数为$p(x,y)$, 则$\zeta = \xi + \eta$也是连续型的，且密度函数为
> $$
> h(z) = \int_{\infty}^{\infty}p(x, z-x)dx
> $$
