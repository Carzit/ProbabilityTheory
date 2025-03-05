# 5 期望与积分

[TOC]

## 5.1 简单随机变量

在离散概型下, 对随机变量$\xi$, 我们曾定义了其期望$\mathbb{E}[\xi]$. 即
$$
\mathbb{E}[\xi] = \mathbb{E}[\xi^{+}] - \mathbb{E}[\xi^{-}]
$$
如果等式右边的两项中至少一项有限.

在公理化框架下, 对只取可数个值的随机变量, 我们可以类似地定义期望. 



### 5.1.1 简单随机变量定义

给定概率空间$(\Omega, \mathscr{F}, P)$, 我们先引进简单随机变量的概念.

> 若随机变量$\xi$可表示为
> $$
> \xi = \sum_{i=1}^{\infty}x_iI_{A_i}, x_i\in \mathbb{R},A_i \in \mathscr{F}
> $$
> 其中$\{A_i, i = 1, 2, \dots\}$为$\Omega$的一个分割, 则称$\xi$为**简单随机变量**.
>
>  若还有$x_i \geqslant 0, \forall i$, 则称$\xi$为**非负简单随机变量**.



### 5.1.2 非负简单随机变量期望

我们先对非负简单随机变量定义期望.

> 设$\xi$为非负简单随机变量
> $$
> \xi = \sum_{i=1}^{\infty}x_iI_{A_i}, x_i\geqslant 0, \forall i
> $$
> 定义
> $$
> \mathbb{E}[\xi] := \sum_{i=1}^{\infty}x_iP(A_i)
> $$

注意在上述定义中, 等式右边是非负项级数, 所以收敛是肯定的, 无非是收敛到无限或有限的区别, 且其值与各项的排序无关. 若收敛到有限数, 则称$\xi$**可积**.



### 5.1.3 期望定义的合理性

我们必须说明这个定义的合理性, 即若还有另外一个分割$\{B_j, j = 1,2,\dots \}$使得$\xi$也可以表示为
$$
\xi = \sum_{j=1}^{\infty} y_jI_{B_j}, y_j \geqslant 0
$$
若$A_iB_j \neq \emptyset$, 则必有$x_i = y_j$. 因此，由概率的可列可加性得
$$
\begin{align}
\sum_{i=1}^{\infty}x_iP(A_i) &= \sum_{i=1}^{\infty}\sum_{j=1}^{\infty}x_iP(A_iB_j) \notag\\
&= \sum_{j=1}^{\infty}\sum_{i=1}^{\infty}x_iP(A_iB_j) \notag\\
&= \sum_{j=1}^{\infty}\sum_{i=1}^{\infty}y_iP(A_iB_j) \notag\\
&= \sum_{j=1}^{\infty}y_jP(B_j)
\end{align}
$$
其中两个求和号能交换次序是因为现在是正项级数.

因此，期望与分割方式无关.

### 5.1.4 简单随机变量的期望

对可正可负的随机变量, 期望是将其分解为正部负部分别定义期望. 具体地说, 设
$$
\xi = \sum_{i=1}^{\infty}x_iI_{A_i}
$$
则
$$
\xi = \xi^{+}-\xi^{-}
$$
其中
$$
\xi^{+}:=\sum_{i=1}^{\infty}x_i^{+}I_{A_i}, \xi^{-}:=\sum_{i=1}^{\infty}x_i^{-}I_{A_i}
$$
由于$\xi^{+}$与$\xi^{-}$均为非负简单随机变量, 所以其期望均有定义. 我们有

> 设$\xi$是简单随机变量*.* 若$\mathbb{E}[\xi^{+}]$与$\mathbb{E}[\xi^{-}]$中至少一个有限*,* 则称$\mathbb{E}[\xi]$**存在**, 且定义为
> $$
> \mathbb{E}[\xi] = \mathbb{E}[\xi^{+}] - \mathbb{E}[\xi^{-}]
> $$
> 若两者均有限*,* 则称$\xi$**可积**.

由定义直接得到:

> 简单随机变量$\xi = \sum_{i=1}^{\infty}x_iI_{A_i}$可积的充要条件是
> $$
> \sum_{i=1}^{\infty}\lvert x_i \rvert P(A_i) < \infty
> $$
> 此时
> $$
> \mathbb{E}[\xi]=\sum_{i=1}^{\infty}x_iP(A_i)
> $$



简单随机变量的期望有以下性质:

- 线性性*:* 设$a, b \in \mathbb{R}$, $\xi, \eta$可积, 则$a\xi + b\eta$也可积, 且

  $$\mathbb{E}[a\xi + b\eta] = a\mathbb{E}[\xi] + b\mathbb{E}[\eta]$$

- 单调性*:* 设$\xi, \eta$可积, 则
  $$
  \xi \leqslant \eta \Rightarrow \mathbb{E}[\xi] \leqslant \mathbb{E}[\eta]
  $$

- 三角不等式: 设$\xi$可积, 则
  $$
  \lvert \mathbb{E}[\xi] \rvert = \mathbb{E}[\lvert \xi \rvert]
  $$



## 5.2 一般随机变量

### 5.2.1 非负一般随机变量的期望

现在我们要对一般的随机变量也定义期望. 定义的方法是通过离散逼近. 具体地说就是:

> 设$\xi$是非负实值随机变量, $\xi_n$是简单随机变量列, 且
> $$
> \xi_n(\omega) \rightrightarrows \xi(\omega) ~\text{a.s.}
> $$
> 即在一个可略集外, $\xi_n$关于$\omega$一致收敛于$\xi$, 则定义
> $$
> \mathbb{E}[\xi] := \lim_{n \to \infty} \mathbb{E}[\xi_n]
> $$

>设$\xi$是非负随机变量, 且$P(\xi = \infty)>0$, 则定义
>$$
>\mathbb{E}[\xi] = \infty
>$$

为使这个定义合理, 我们要说明两件事情. 第一是对任意非负实值随机变量, 至少有一个简单随机变量序列$\xi_n$使得$ξ_n \rightrightarrows ξ a.s.$.第二是对一致收敛于$\xi$的$\xi_n$, 极限$\lim_{n\to\infty} \mathbb{E}[\xi_n]$的确存在且不依赖于$\xi_n$的选择.



### 5.2.2 一般随机变量

现在我们可以对一般的随机变量定义期望.

> 对一般的$\xi$, 若下面两式中至少之一成立*:*
> $$
> \mathbb{E}[\xi^{+}]< \infty, \mathbb{E}[\xi^{-}]< \infty
> $$
> 则定义
> $$
> \mathbb{E}[\xi] = \mathbb{E}[\xi^{+}] - \mathbb{E}[\xi^{-}]
> $$
> 若
> $$
> \mathbb{E}[\xi^{+}]+\mathbb{E}[\xi^{-}]< \infty
> $$
> 则称$\xi$可积.

由定义, 期望是一种和的极限, 因此是积分*,* 故也常常用积分符号表示期望, 即用
$$
\int_{\Omega}\xi(\omega)P(d\omega)=\int_{\Omega}\xi(\omega)dP(\omega)=\int_{\Omega}\xi dP
$$

> 设$\xi$是离散型随机变量, 分布列为$(x_n, p_n)$. 若$\sum_n \lvert x_n \rvert p_n < \infty$, 则
> $$
> \mathbb{E}[\xi] = \sum_n x_n p_n < \infty
> $$
> 
>
> 设$\xi$是连续型型随机变量, 密度函数为$p(x)$. 若$\int_{-\infty}^{\infty}\lvert x \rvert P(x)dx$, 则
> $$
> \mathbb{E}[\xi] = \int_{-\infty}^{\infty}x P(x)dx
> $$

###  5.2.3 期望的基本性质

现在我们研究期望的基本性质. 首先我们有:

> (期望的线性性)设$\xi, \eta$可积, $a, b$是常数, 则
> $$
> \mathbb{E}[a\xi + b\eta] = a\mathbb{E}[\xi] + b\mathbb{E}[\eta]
> $$

设$\xi$与$\eta$的期望均存在, 则我们有以下推论

> - $\xi \geqslant 0 \Rightarrow \mathbb{E}[\xi] \geqslant 0$
> - $\xi \leqslant \eta \Rightarrow \mathbb{E}[\xi] \leqslant \mathbb{E}[\eta]$
> - $\lvert \mathbb{E}[\xi] \rvert \leqslant \mathbb{E}[\lvert x \rvert]$



### 5.2.4 切比雪夫不等式和柯西-施瓦茨不等式

我们由此可以得到**Chebyshev不等式**:

> 设$\xi \geqslant 0$是随机变量, $a>0$是常数. 则
> $$
> P(\xi \geqslant \epsilon) \leqslant \frac{\mathbb{E}[\xi]}{\epsilon}
> $$

证明. 我们有

$$
\epsilon P(\xi \geqslant \epsilon) = \epsilon\mathbb{E}[I_{\xi\geqslant \epsilon}] \leqslant \xi\mathbb{E}[I_{\xi\geqslant \epsilon}] = \mathbb{E}[\xi I_{\xi\geqslant \epsilon}] \leqslant \mathbb{E}[\xi]
$$


此不等式很少有直接使用的, 使用得更多的是它的一些变体.

这里的总体想法是, 如果$f$是定义在 $[0, \infty)$上的单调上升函数, 且$x > 0$时$f(x) > 0$, 那么对任意(即不管是否非负)$\xi$有

$$
P(\lvert \xi \rvert \geqslant \epsilon) = P\left(f(\lvert \xi \rvert) \geqslant f(\epsilon)\right) \leqslant \frac{\mathbb{E}[f(\lvert \xi \rvert)]}{f(\epsilon)}
$$
由此可以得到推论:

> $$
> \mathbb{E}[\lvert\xi\rvert]=0 当且仅当 P(\xi=0)=1
> $$

证明.

由Chebyshev不等式，$P(\lvert\xi\rvert\geqslant \frac1n) \leqslant n\mathbb{E}[\lvert\xi\rvert] = 0$

又因为$\{\xi \neq 0\} = \bigcup_{n=1}^{\infty}\{\lvert\xi\rvert\geqslant \frac1n\}$

因此$P(\xi \neq 0) = \lim_{n\to\infty}P(\lvert\xi\rvert \geqslant \frac1n)=0$

即$P(\xi=0)=1$.



一个较为常见的使用是取随机变量为$|\xi-\mathbb{E}[\xi]|$，取$f(x)=x^2$, 则有
$$
P(|\xi-\mathbb{E}[\xi]|\geqslant\epsilon)\leqslant\frac{D[\xi]}{\epsilon^2}
$$
我们在大数定律中还会再遇见它。



我们还可以得到:

> 设$\xi^2, \eta^2$可积*,* 则成立**Cauchy-Schwarz不等式**
> $$
> (\mathbb{E}[\xi\eta])^2 \leqslant \mathbb{E[\xi^2]\mathbb{E}[\eta^2]}
> $$

## 5.3 计算期望的例子

前面我们定义了随机变量的期望并研究了它的一些基本性质. 至于它的计算, 在有些情况下该随机变量的分布是已知的, 此时期望就是一个级数或者是一个积分, 因此问题是比较明确的(明确地难或者明确地易); 另外一些情况则是其分布并不清楚, 此时就要利用期望的性质, 而不是死算; 还有一些情况应用中的问题, 这样的问题更具有挑战性, 当然也就更有趣.

1. 设$\xi \sim B(p)$, 即参数为$p$的Bernoulli分布
   $$
   \mathbb{E}[\xi] = 0 \cdot (1-p) + 1 \cdot p = p
   $$

2. 设$\xi_i \sim B(p_i), i=1,2,\dots$. 令$\xi = \sum_{i}^n \xi_i$
   $$
   \mathbb{E}[\xi] = \mathbb{E}[\sum_{i=1}^n \xi_i] = \sum_{i=1}^n \mathbb{E}[\xi_i] = np
   $$

3. 在$\{1, 2, · · · , n\}$中有放回地取$k$个数$(k \leqslant n)$，求取出的数字之和$\xi$的期望。

   记随机变量$\xi_i = \begin{cases}1, 如果数字i被取到\\0,else\end{cases}$, 则$\xi_i \sim B(\frac{k}{p})$

   我们有$\xi = \sum_{i=1}^n i\xi_i$
   $$
   \mathbb{E}[\xi] = \mathbb{E}[\sum_{i=1}^n i\xi_i]=\sum_{i=1}^n i\mathbb{E}[\xi_i]= \frac{k(n+1)}{2}
   $$

4. 设$\xi \sim P(\lambda)$, 即参数为$\lambda$的Poisson分布. 
   $$
   \mathbb{E}[\xi] = \sum_{i=0}^{\infty}i\frac{\lambda^i}{i!}e^{-\lambda} = \sum_{i=1}^{\infty}\frac{\lambda^i}{(i-1)!}e^{-\lambda}= \lambda e^{-\lambda}\sum_{i=1}^{\infty}\frac{\lambda^{i-1}}{(i-1)!} = \lambda
   $$

5. 设$\xi \sim Ge(p)$, 即参数为$p$的几何分布. 
   $$
   \mathbb{E}[\xi] = \sum_{i=1}^{\infty}i(1-p)^{i-1}p = p \frac{d}{d(1-p)}\sum_{i=1}^{\infty}(1-p)^{i}=p\frac{d}{d(1-p)}\frac{1-p}{p}=\frac1p
   $$

6. 设$\xi \sim U(a,b)$为均匀分布*,* 密度函数为$p(x) = \frac{1}{b-a}I_{[a,b]}(x)$
   $$
   \mathbb{E}[\xi] = \int_{a}^b \frac{x}{b-a} dx = \frac{a+b}{2}
   $$

7. 设$\xi \sim \mathcal{N}(\mu,\sigma)$为正态分布, 密度函数为$p(x) = \frac{1}{\sqrt{2\pi}}e^{-\frac{x^2}{2\sigma^2}}$
   $$
   \mathbb{E}[\xi] = \int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}xe^{-\frac{(x-\mu)^2}{2\sigma^2}}dx\stackrel{z:=\frac{x-\mu}{\sigma}}{=}\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}(z+\frac{\mu}{\sigma})e^{-\frac{z^2}{2}}dx = \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}(\sigma z+\mu)e^{-\frac{z^2}{2}}dz = \frac{\mu}{\sqrt{2\pi}}\int_{-\infty}^{\infty}e^{-\frac{z^2}{2}}dz = \mu
   $$
   注意高斯积分$\int_{-\infty}^{\infty}e^{x^2}dx = \sqrt{\pi}$.

8. 设$\xi \sim E(\lambda)$为指数分布, 密度函数为$p(x) = \lambda e ^{-\lambda x}I_{[0,\infty)}(x)$.
   $$
   \mathbb{E}[\xi] = \int_{0}^{\infty}\lambda x e^{-\lambda x}dx = -\int_{0}^{\infty} x d e^{-\lambda x} = -xe^{-\lambda x} \big|_{0}^{\infty} +\int_{0}^{\infty} e^{-\lambda x} dx = \frac{1}{\lambda}
   $$

9. 设$\xi$服从Cauchy分布, 密度函数为$p(x) = \frac{1}{\pi}\frac{1}{1+x^2}$
   $$
   \mathbb{E}[\xi^{+}] = \mathbb{E}[\xi^{-}] = \int_{0}^{\infty} \frac{1}{\pi} \frac{x}{1+x^2}dx = \frac{1}{2\pi} \ln(1+x^2) \big|_{0}^{\infty} = \infty
   $$
   所以, $\xi$的期望不存在.



## 5.4 随机变量列的收敛性

下节我们将研究积分号下取极限, 即极限和期望的交换顺序问题. 由于期望就是积分, 所以这个问题我们在数学分析里已经有所接触, 但那时的条件一般都是被积函数一致收敛, 这无疑是太强了. 实际上对随机变量来说, 逐点收敛都太强了, 所以我们将在本节寻找一些较弱的条件. 考察一下随机变量序列的各种不同的收敛性.



### 5.4.1 几乎必然收敛（逐点收敛）

设$\{\xi_n\}$是定义在概率空间$(\Omega, \mathscr{F}, P)$上的随机变量列. 在考察其收敛性时, 最容易想到的收敛性就是移植数学分析里面的逐点收敛, 即对每个$\omega$, $\xi_n(\omega)$都收敛. 但由于在概率论中,我们可以忽略概率为零的事件(可略集), 所以可以允许在某个可略集上不收敛. 因此, 我们有下面的定义:

> 设$\xi,\xi_n,n=1,2,\dots$为随机变量*.* 若存在$A \in \mathscr{F}, P(A) = 0$, 使得
> $$
> \lim_{n \to \infty}\xi_n(\omega) = \xi(\omega), \forall \omega \notin A
> $$
> 则称$\xi_n$**几乎必然收敛**于$\xi$, 记为$\lim_{n \to \infty}\xi_n = \xi,~a.s.$或$\xi_n \stackrel{a.s.}{\rightarrow} \xi$.



### 5.4.2 依概率收敛

几乎必然收敛当然是一件很美好的事情, 不过这个要求非常苛刻,往往难以达到. 再说概率论里面关心的往往不是每个样本的性质, 而是全局的性质. 这样, 就出现了下面的概念.

> 设$\xi,\xi_n,n=1,2,\dots$为随机变量*.* 若对于$\forall \epsilon > 0$都有
> $$
> \lim_{n \to \infty}P(\lvert\xi_n - \xi\rvert>\epsilon)=0
> $$
> 则称$\xi_n$**依概率收敛**于$\xi$, 记为$\lim_{n \to \infty}\xi_n = \xi,~(P)$或$\xi_n \stackrel{P}{\rightarrow} \xi$.



### 5.4.3 逐点收敛和依概率收敛的关系

这两种收敛性是什么关系呢?

> 若$\xi_n \stackrel{a.s.}{\rightarrow} \xi$, 则$\xi_n \stackrel{P}{\rightarrow} \xi$
>
> 若$\xi_n \stackrel{P}{\rightarrow} \xi$, 则存在子列$\xi_{n_k}$使$\xi_{n_k} \stackrel{a.s.}{\rightarrow} \xi$



![图片1](D:\Study\概率论\图片1.png)

我们顺便得到推论:

> 设$\xi_n \stackrel{P}{\rightarrow} \xi$, 且存在随机变量$\eta$使得$\lvert \xi_n \rvert \leqslant \eta,~\text{a.s.}, \forall n$. 则
> $$
> \lvert \xi \rvert \leqslant \eta,~\text{a.s.}
> $$
> 特别地, 当取$\eta \equiv C$时有
> $$
> \xi \leqslant C
> $$

## 5.5 积分**(**期望**)**号下取极限

现在我们就开始考虑积分号和极限的交换问题.即考虑在什么情况下，$\lim_{n\to\infty}\mathbb{E}[\xi_n] = \mathbb{E}[\lim_{n\to\infty} \xi_n]$



 我们固定一个概率空间$(\Omega,\mathscr{F}, P)$, 所有的随机变量均定义在这个空间上.



> (**有界收敛定理, 控制收敛的特殊情况**)设$\xi_n \stackrel{P}{\rightarrow} \xi$,且存在常数$C$使得$\lvert \xi_n \rvert \leqslant C,~\text{a.s.},~\forall n$, 则
> $$
> \lim_{n\to\infty}\mathbb{E}[\xi_n] = \mathbb{E}[\xi]
> $$

> **(单调收敛定理, Levi)**设$0 \leqslant \xi_n \uparrow \xi,~\text{a.s.}$, 则
> $$
> \lim_{n\to\infty}\mathbb{E}[\xi_n] = \mathbb{E}[\xi]
> $$

> **(逐项积分定理)** 设$\xi_n,n=1,2,\dots$是随机变量*,* $\xi=\sum_{n=1}^{\infty}\xi_n$
>
> 若$\sum_{n=0}^{\infty}\mathbb{E}[\lvert\xi_n\rvert] < \infty$, 则$\sum_{i=1}^n\xi_i$几乎必然收敛, $\xi$可积
> $$
> \lim_{n\to\infty}\mathbb{E}[\lvert\xi - \sum_{i=1}^n\xi_i\rvert] = 0
> $$
> 即
> $$
> \mathbb{E}[\sum_{i=1}^{\infty}\xi_i] = \sum_{i=1}^{\infty}\mathbb{E}[\xi_i]
> $$

> **(控制收敛定理)**设$\xi_n \stackrel{P}{\rightarrow} \xi$, 且存在$\eta \geqslant 0, \mathbb{E}[\eta] < \infty$, 使得对$\forall n,~ \lvert \xi_n\rvert \leqslant \eta~\text{a.s.}$. 则
> $$
> \lim_{n\to\infty}\mathbb{E}[\lvert\xi - \xi_n\rvert] = 0
> $$
> 且
> $$
> \lim_{n\to\infty}\mathbb{E}[\xi_n] = \mathbb{E}[\xi]
> $$

## 5.6 Fubini定理

### 5.6.1 富比尼定理

设$(\Omega_i, \mathscr{F}_i, P_i),i=1,2$为概率空间. 令
$$
(\Omega, \mathscr{F}, P) = (\Omega_1, \mathscr{F}_1, P_1)\times (\Omega_2, \mathscr{F}_2, P_2)
$$
就像数学分析里重积分可以化为累次积分进行计算一样, 期望也有这样的性质. 即我们有下面的

> **(Fubini定理)** 设$f$是$(\Omega, \mathscr{F}, P)$上的可积随机变量*.* 则
> $$
> \mathbb{E}[f(\omega_1, \omega_2)] = \mathbb{E}[\mathbb{E}[f(x, \omega_2)]|_{x=\omega_1}]
> $$
> 或者写为
> $$
> \mathbb{E}[f(\omega_1, \omega_2)] = \mathbb{E}_{\omega_2}[\mathbb{E}_{\omega_1}[f(\omega_1, \omega_2)]]
> $$
> 

特别地, 设$(\Omega_1, \mathscr{F}_1, P_1)$为任一概率空间, $\Omega_2 = [0,1], \mathscr{F}_2 = \mathscr{B}([0,1]), P_2 =\text{Lebesgue测度}$. 在此两空间的乘积空间上用上述定理, 就有
$$
\int_{[0,1]}\int_{\Omega}\xi(t,\omega)dP(\omega)dt = \int_{\Omega}\int_{[0,1]}\xi(t)dtdP(\omega)
$$
即
$$
\int_{0}^1\mathbb{E}[\xi(t)]dt = \mathbb{E}[\int_0^1\xi(t)dt]
$$
完全类似地, 考虑整个$\mathbb{R}$上的Lebesgue测度, 就有
$$
\int_{\mathbb{R}}\mathbb{E}[\xi(t)]dt = \mathbb{E}[\int_{\mathbb{R}}\xi(t)dt]
$$

### 5.6.2 含参期望

设$I = (t_0-\epsilon,t_0+\epsilon)$是$\mathbb{R}$上的开区间, 而对$\forall t \in I$, $\xi(t)$是随机变量且期望可积。

我们将研究函数$f(t) := \mathbb{E}[\xi(t)]$在$t_0$处的连续性与可微性问题.

我们先看连续性.

> 设 (i)对任意$t_n \to t_0,\xi(t_n) \stackrel{P}{\rightarrow} \xi(t_0)$
>
> ​     (ii)存在可积随机变量$\eta$使得$\lvert \xi(t)\rvert \leqslant \eta~\text{a.s.},\forall t\in I$.
>
> 则$f(t)$在$t_0$处连续.

由此可以得到积分与期望交换顺序的条件, 即Fubini定理的另一种形式. 注意这里涉及的对$t$的积分为普通的Riemann积分.

> **(Fubini定理)** 设$−\infty < a < b < \infty$,且
>
> (i) 对几乎所有的$\omega$, $t \in [a, b],~ t \mapsto \xi(t)$连续;
>
> (ii) 存在可积随机变量$\eta$使得$|\xi(t)| \leqslant \eta~\text{a.s.},\forall t \in [a,b]$
>
> 则
> $$
> \mathbb{E}[\int_a^b \xi(t)dt] = \int_a^b f(t)dt
> $$

如果*ξ*(*t*)具有更好的光滑性, 那么*f*(*t*)也具有更好的光滑性:

> (i)对几乎所有的$\omega$, $\xi^{\prime} (t) := \frac{\partial \xi(t)}{\partial t}$存在*,* $\forall t \in I$;
>
> (ii)存在可积随机变量$\eta$, 使得$\sup_{t \in I}\lvert \xi^{\prime}(t)\rvert \leqslant \eta~\text{a.s.}$
>
> 则$f$在$t_0$处可微, 且
> $$
> f^{\prime}(t_0) = \mathbb{E}[\xi^{\prime} (t_0)]
> $$

## 5.7 方差和矩

随机变量的期望直观上是反映随机变量取值的平均大小的数字特征, 基于随机变量函数的期望可以定义出反映随机变量其他特征的量. 比如方差, 协方差, 相关系数和各种矩.

### 5.7.1 方差的定义和性质

> 设随机变量$\xi$的期望有限, 方差定义为
> $$
> D[\xi] := \mathbb{E}[(\xi- \mathbb{E}[\xi])^2]
> $$
> 标准差定义为$\sqrt{D[\xi]}$

方差的另一个计算公式是:
$$
D[\xi] = \mathbb{E}[\xi^2] - (\mathbb{E}[\xi])^2
$$
若期望和方差均有限*,* 则期望是常数中最接近$\xi$的, 在下面的意义下:
$$
D[\xi] = \mathbb{E}[(\xi - \mathbb{E}[\xi])^2] \leqslant \mathbb{E}[(\xi - c)^2], \forall c \in \mathbb{R}
$$
该结论对$f(c) = \mathbb{E}[(\xi - c)^2]$求导即可得.

方差还有如下基本性质:

> - (i) 设$\xi = c$是常数, 则$D[\xi] = 0$
> - (ii) 设$c$是常数, 则$D[\xi + c] = D[\xi]$
> - (iii) 设$c$是常数, 则$D[c\xi] = c^2D[\xi]$

### 5.7.2 矩的定义

对$p \geqslant 1$, $\mathbb{E}[\lvert\xi\rvert^n]$称为$\xi$的**p-阶矩**



### 5.7.3 方差和矩的运算

设$\xi$的分布函数为$F$, 那么根据上节的结果*,* 我们有:
$$
D[\xi] = \int_{-\infty}^{\infty}(x-\mathbb{E}[x])^2dF(x)
$$
对于离散型变量$D[\xi] = \sum_{i=1}^{\infty}[(x_i-\sum_{i=1}^{\infty}x_ip_i)^2p_i]$

对于连续型变量$D[\xi] = \int_{-\infty}^{\infty}[(x-\int_{-\infty}^{\infty}xp(x))^2p(x)]dx$



类似地，我们有
$$
\mathbb{E}[\lvert\xi\rvert^n] = \int_{-\infty}^{\infty}\lvert x\rvert^ndF(x)
$$
我们看几个具体的例子.

1. Bernoulli分布$\xi \sim B(p)$.
   $$
   \mathbb{E}[\xi] = p
   $$
   
   $$
   \mathbb{E}[\xi^2] = p 
   $$
   
   $$
   D[\xi] = p(1-p)
   $$
   
2. 二项分布$\xi \sim B(n,p)$
   $$
   \mathbb{E}[\xi] = np
   $$

   $$
   d[\xi] = np(1-p)
   $$

3. Poisson分布$\xi \sim P(\lambda)$
   $$
   \mathbb{E}[\xi] = \sum_{k=0}^{\infty}\frac{\lambda^kk}{k!}e^{-\lambda} = \lambda
   $$

   $$
   \mathbb{E}[\xi^2] = \sum_{k=0}^{\infty}\frac{\lambda^kk^2}{k!}e^{-\lambda} = \sum_{k=1}^{\infty}\frac{\lambda^k}{(k-1)!}e^{-\lambda}+\sum_{k=2}^\infty\frac{\lambda^k}{(k-2)!}e^{-\lambda} = \lambda + \lambda^2
   $$

   $$
   D[\xi] = \lambda
   $$

4. 均匀分布$\xi \sim \mathcal{U}(a,b)$
   $$
   \mathbb{E}[\xi] = \int_{a}^b \frac{x}{b-a}dx = \frac{a+b}{2}
   $$

   $$
   \mathbb{E}[\xi^2] = \int_{a}^b \frac{x^2}{b-a}dx = \frac{a^2+ab+b^2}{3}
   $$

   $$
   D[\xi] = \frac{a^2+b^2-2ab}{12}
   $$

5. 正态分布$\xi \sim \mathcal{N}(\mu, \sigma)$
   $$
   \mathbb{E}[\xi] = \int_{-\infty}^{\infty}\frac{x}{\sqrt{2\pi}\sigma}e^{\frac{(x-\mu)^2}{2\sigma^2}} dx= \mu
   $$

   $$
   D[\xi] = \int_{-\infty}^{\infty}\frac{x^2}{\sqrt{2\pi}\sigma}e^{\frac{(x-\mu)^2}{2\sigma^2}} dx= \sigma^2
   $$

   

6. 二维正态分布$(\xi, \eta) = \mathcal{N}(\mu_1, \mu_2, \sigma_1^2, \sigma_2^2, \rho)$

   则$\xi \sim \mathcal{N}(\mu_1, \sigma_1), \eta\sim\mathcal{N}(\mu_2,\sigma_2)$ 

   所以$\mathbb{E}[\xi] = \mu_1, D[\xi] = \sigma_1^2, \mathbb{E}[\eta] = \mu_2, D[\eta] = \sigma_2^2$

   它们的协方差
   $$
   \begin{align}
   \text{Cov}(\xi,\eta)&=\mathbb{E}[(\xi-\mu_1)(\eta-\mu_2)]\notag\\
   &=\int_{\mathbb{R}}(x-\mu_1)(y-\mu_2)p(x,y)dxdy\notag\\
   & \stackrel{s=\frac{(x-\mu_1)}{\sigma_1},t=\frac{(y-\mu_2)}{\sigma_2}}{=}\sigma_1\sigma_2\int_{\mathbb{R}}st\frac{1}{2\pi\sqrt{1-\rho^2}}\exp\{-\frac{1}{2(1-\rho^2)}\left[s^2+t^2-2\rho st\right]\}dsdt\notag\\
   &=\sigma_1\sigma_2\rho
   \end{align}
   $$
   

### 5.7.4 协方差和相关系数

如果说方差是衡量一个随机变量波动的指标的话, 那么衡量两个随机变量联动的指标则是协方差. 

具体地说, 

> 二维随机变量$(\xi, \eta)$的**协方差**定义为
> $$
> \text{Cov}(\xi, \eta) := \mathbb{E}[(\xi - \mathbb{E}[\xi])(\eta - \mathbb{E}[\eta])] = \int_{\mathbb{R}^2}(x - \mu_\xi)(y - \mu_\eta)dF(x,y)
> $$
> 其中$F$是$(\xi, \eta)$的分布函数.



将$(\xi - \mathbb{E}[\xi])(\eta - \mathbb{E}[\eta])$乘开后分别对每项求期望, 易见协方差的另一种计算方式
$$
\text{Cov}(\xi, \eta) = \mathbb{E}[\xi\eta] - \mathbb{E}[\xi]\mathbb{E}[\eta]
$$


> $\xi$和$\eta$的相关系数定义为
> $$
> \rho := \frac{\text{Cov}(\xi,\eta)}{\sqrt{D[\xi]D[\eta]}}
> $$

由Cauchy-Schwartz不等式, 我们有
$$
\lvert \rho \rvert \leqslant 1
$$
若$\text{Cov}(\xi, \eta) = 0$, 称$\xi, \eta$**不相关**. 

易见$\xi, \eta$不相关的充要条件是
$$
\mathbb{E}[\xi\eta] = \mathbb{E}[\xi]\mathbb{E}[\eta]
$$
注意不相关不一定独立，但独立一定不相关。相关性衡量的是线性相关程度。



## 5.8 Riemann-Stieltjes积分

设$F$是$\mathbb{R}$上的单调上升右连续函数, $\phi$是$\mathbb{R}$上的函数. 我们将仿照Riemann积分定义所谓Riemann-Stieltjes积分. 这个积分粗略地说, 是以**Riemann-Stieltjes和**
$$
I_n(\mathscr{P}, \Theta) = \sum_{\max\{F(x_i)-F(x_{i-1})\}\to0}\phi(\theta_i)(F(x_i)-F(x_{i-1}))
$$
代替**Riemann和**
$$
\sum_{\max_\{x_i-x_{i-1}\}\to0}\phi(\theta_i)(x_i-x_{i-1})
$$
其中$\theta_i \in [x_{i-1}, x_i]$, 且这个极限必须不依赖于$\theta_i$和$x_i$的具体选择.

利用Riemann-Stieltjes积分, 我们有下面计算随机变量的函数的期望的公式, 统一了此前的离散型与连续型随机变量的公式

> 设$\xi$为随机变量, $F$为其分布函数, $\phi : \mathbb{R} \to \mathbb{R}$为连续函数. 则$\mathbb{E}[\phi(\xi)]$存在的充要条件是
>
> $\phi$对F的Riemann-Stieltjes积分存在
>
> 且此时有
> $$
> \mathbb{E}[\phi(\xi)] = \int_{\mathbb{R}}\phi(x)dF(x)
> $$

如果两个随机变量$\xi$和$\eta$同分布, 那么对任意有界连续函数$\phi$, $\phi(\xi)$和$\phi(\eta)$都有相同的期望. 反过来, 我们也可以证明, 如果对足够多的$f$, $f(\xi)$与$f(\eta)$ 的期望仍然相等, 那么$\xi$和$\eta$就没得选择, 必须同分布. 为精确地阐述这一结果, 我们引进函数类:

> $$
> C_0^{\infty}(\mathbb{R}^m) := \{f: \mathbb{R}^m\to\mathbb{R}: f无穷次可微且在某个有界集外恒等于0\}
> $$
>
> 



>  设对$\forall f \in C_0^{\infty}(\mathbb{R}^m)$, 若 
> $$
> \mathbb{E}[f(\xi)] = \mathbb{E}[f(\eta)]
> $$
> 那么$\xi$与$\eta$同分布*.*





## 5.9 几个等式与不等式

除了几个极少数的典型例子外, 一般来说具体算出期望是不可能的. 这时, 估计其值就是退而求其次的选择了. 因此, 不管理论上还是应用上, 我们都需要了解并娴熟地掌握估计期望值的基本工具.

### 5.9.1 矩-函数期望不等式

下面是我们要建立的第一个等式. 它的意义在于, 直观上$|\xi|$比较小时, $\mathbb{E}[|\xi|^p]$应该会比较小. 

而什么叫$|\xi|$比较小呢? 似乎应该是当$x$比较大时, $P(|\xi|>x)$比较小. 因此, 如果直接用
$$
\mathbb{E}[|\xi|^p] = \int_{-\infty}^{\infty}|x|^pdF(x)
$$
难以直接估计p-阶矩的话 (*这个确实比较难, 因为不可能通过估计$F(x)$即$P(\xi\leqslant x)$来估计它*), 那么可以尝试通过估计尾概率$P(\xi \geqslant x)$来估计它. 之所以这是可能的, 是因为有下面的

> 设$\xi$是随机变量, $p \geqslant 1$,
> $$
> \mathbb{E}[\xi^p] = \int_{0}^{\infty}pr^{p-1}P(\xi\geqslant r)dr
> $$
> 

推导是简单的
$$
\mathbb{E}[\xi^p] = \int_{0}^{\infty}P(\xi\geqslant r)dr^p = \int_{0}^{\infty}P(\xi^p\geqslant r^p)dr^p
$$


$P(|\xi|\geqslant x)$称为$\xi$的尾概率, 而估计尾概率常用的工具是前面证明了的**Chebyshev不等式**:
$$
P(|\xi|\geqslant x) \leqslant \frac{\mathbb{E}[f(|\xi|)]}{f(x)}
$$


其中$f$是$\mathbb{R}^{+}$上的正的单调上升函数. 

由此代入前式得到**矩-函数期望不等式**
$$
\mathbb{E}[\xi^p] \leqslant p\mathbb{E}[f(\xi)]\int_{0}^{\infty}\frac{r^{p-1}}{f(r)}dr
$$



### 5.9.2 琴生不等式

> **(Jensen不等式)**.设$\phi$为$\mathbb{R}$上的凸函数*.* 则
> $$
> \phi(\mathbb{E[\xi]}) \leqslant \mathbb{E}[\phi(\xi)]
> $$

借助于此引理, 我们可以证明两个重要的不等式. 为此引进**范数**定义: 

对于$p \geqslant 1$,
$$
||\xi||_p := (\mathbb{E}[|\xi|^p])^{\frac{1}{p}}
$$

而$|\xi|$的p阶矩则可以表述为
$$
\mathbb{}E[|\xi|^p] = ||\xi||_p^p
$$




> 设$\xi, \eta$是随机变量. 
>
> (1) **(Holder不等式)** 设$1 < p, q < \infty $满足$\frac{1}{p} + \frac{1}{q} = 1$, 则
> $$
> ||\xi\eta||_1 \leqslant ||\xi||_p ||\eta||_q
> $$
> (2) **(Minkowvski不等式)** $\forall p \geqslant 1$
> $$
> || \xi +\eta||_p \leqslant ||\xi||_p + ||\eta||_p
> $$
> (3) **(幂平均公式)** 设$1\leqslant p<q$
> $$
> ||\xi||_p \leqslant ||\xi||_q
> $$
> 

 Holder不等式在$p=q=2$的特殊情形即为**Cauchy-Schwarz不等式**.

