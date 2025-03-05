# 8 特征函数

本章我们介绍一个研究随机变量的重要工具——特征函数.

当然, 这个工具并不是概率论所特有的. 从分析的角度看, 一个随机变量的特征函数其实就是其分布函数的Fourier变换. 不过, 和分析中Fourier变换的一般理论相比, 它具有强烈的概率特点. 

这表现在作为Riemann-Stieltjes积分或Lebesgue-Stieltjes积分, 它既不可归类于光滑函数或$L^p$函数的Fourier变换这么一个狭小的范围内, 又不必放在广义函数的Fourier变换这么一个庞大的框架中, 表现在它在研究独立随机变量之和时发挥的巨大作用, 表现在有时候甚至连定义分布(例如退化的多维正态分布)这么一个“很概率”的事情也无法回避它.



[TOC]



## 8.1 复随机变量

研究特征函数会涉及到取复数值的随机变量, 所以我们需要在这方面做些准备工作. 我们迄今为止接触到的随机变量都是取实数值的, 所以就无修饰地用随机变量称呼之. 以后我们也保持这个习惯, 即单说随机变量时, 指的就是实值随机变量, 或至多是广义实值的, 即可以取*±∞*的随机变量, 而虚随机变量则是随机变量乘以虚数单位$i$, 而复随机变量就是由实随机变量和虚随机变量组成的东西, 即我们有:

> 设$\xi, \eta$是随机变量*,* 则
> $$
> \zeta := \xi +i\eta
> $$
> 称为复随机变量.

若$\xi, \eta$的期望均存在, 那么$\zeta$的期望定义为
$$
\mathbb{E}[\zeta] = \mathbb{E}[\xi] + i\mathbb{E}[\eta]
$$
显然, 这样定义的期望保持了线性性, 即
$$
\mathbb{E}[z_1\zeta_1+z_2\zeta_2] = z_1\mathbb{E}[\zeta_1] + z_2\mathbb{E}[\zeta_2]
$$
复随机变量$\zeta$的共轭为
$$
\bar{\zeta} := \xi -i\eta
$$
$\zeta$的模为
$$
|\zeta| = \sqrt{\xi^2+\eta^2}
$$
显然
$$
\text{Re}(\mathbb{E}[\zeta]) = \mathbb{E}[\text{Re}(\zeta)], \text{Im}(\mathbb{E}[\zeta]) = \mathbb{E}[\text{Im}(\zeta)]
$$


我们有如下的**Minkowski不等式**:

> **(Minkowski不等式)** 若$\mathbb{E}[|\zeta|] < \infty$，则$\mathbb{E}[\zeta]$存在，且
> $$
> |\mathbb{E}[\zeta]| \leqslant \mathbb{E}[|\zeta|]
> $$



## 8.2 特征函数的定义

### 8.2.1 基本定义

> 设$F$为分布函数. 对于$t \in \mathbb{R}$，定义
> $$
> f(t) = \int_{-\infty}^{\infty}e^{itx}dF(x)
> $$
> 称为$F$的**分布函数**. 
>
> 若$\xi$是随机变量*,* 以$F$为分布函数*,* 则$f$也称为$\xi$的特征函数. 此时
> $$
> f(t) = \mathbb{E}[e^{it\xi}]
> $$

若$\xi$是离散型随机变量, 分布列为$\{(x_i, p_i)\}$, 则
$$
f(t) = \sum_{i=1}^{\infty}e^{itx_i}p_i = \sum_{i=1}^{\infty}p_i(\cos(tx_i)+i\sin(tx_i))
$$
若$\xi$是连续型随机变量, 密度函数为$p(x)$, 则
$$
f(t) = \int_{-\infty}^{\infty}e^{itx}p(x)dx = \int_{-\infty}^{\infty}p(x)(\cos(tx)+i\sin(tx))dx
$$


### 8.2.2 常见分布的特征函数

下面我们计算一些常用随机变量的特征函数.

1. 单点分布: 设*ξ*服从单点分布: 即有*a* *∈* R使
   $$
   P(\xi = a) = 1
   $$
   则
   $$
   f(t) = e^{ita}
   $$

2. Bernoulli分布: *ξ* *∼* *B*(*p*), *q* = 1 *−* *p*.
   $$
   f(t) = e^{it}p + e^0(1-p) = 1-p+pe^{it}
   $$

3. 二项分布: *ξ* *∼* *B*(*n, p*).
   $$
   f(t) = \mathbb{E}[e^{it(\sum_{i=1}^n\xi_i)}] = \mathbb{E}[\prod_{i=1}^ne^{it\xi_i}] = \prod_{i=1}^n\mathbb{E}[e^{it\xi_i}] = (1-p+pe^{it})^n
   $$

4. Poisson分布: *ξ* *∼* *P*(*λ*)
   $$
   f(t) = \sum_{k=0}^{\infty}\frac{\lambda^ke^{itk}}{k!}e^{-\lambda} = e^{\lambda(e^{it}-1)}
   $$

5. 设$\xi$的分布列为: $P(\xi=-1)=P(\xi=1)=\frac12$ , 则
   $$
   f(t) = \frac{e^{-it}+e^{it}}{2} = \cos(t)
   $$
   
6. 几何分布: $\xi \sim Ge(p)$
   $$
   f(t) = \sum_{k=1}^{\infty}e^{itk}p(1-p)^{k-1} = pe^{it}\sum_{k=0}^{\infty}[e^{it}(1-p)]^k = \frac{pe^{it}}{1-e^{it}(1-p)}
   $$

7. 均匀分布: $\xi \sim \mathcal{U}(a,b)$
   $$
   f(t) = \int_{a}^{b}e^{itx}\frac{1}{b-a}dx = \frac{1}{(b-a)it}e^{itx}\big|_{a}^{b} = \frac{e^{itb}-e^{ita}}{(b-a)it}
   $$
   特别地，当$a=-b$时
   $$
   f(t) = \frac{2i\sin(bt)}{2bit}=\frac{\sin(bt)}{bt}
   $$

8. 指数分布: $\xi \sim E(\lambda)$
   $$
   f(t) = \int_{0}^{\infty}e^{itx}\lambda e^{-\lambda x}dx = \frac{\lambda}{it-\lambda}e^{(it-\lambda)x}\big|_{0}^{\infty} = \frac{\lambda}{\lambda-it}
   $$

9. 正态分布: $\xi \sim \mathcal{N}(\mu,\sigma)$
   $$
   \begin{align}
   f(t)&=\int_{-\infty}^{\infty}e^{itx}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx \notag\\
   &= \frac{1}{\sqrt{2\pi}\sigma}\int_{-\infty}^{\infty} \exp\{-\frac{x^2-2(\mu+it\sigma^2)x+(\mu^2+2\mu it\sigma^2-t^2\sigma^4)-(2\mu it\sigma^2-t^2\sigma^4)}{2\sigma^2}\} dx\notag\\
   &= \exp\{it\mu-\frac{t^2\sigma^2}{2}\}\frac{1}{\sqrt{2\pi}\sigma}\int_{-\infty}^{\infty} \exp\{-\frac{(x-(\mu+it\sigma^2))^2}{2\sigma^2}\}dx\notag\\
   &= \exp\{it\mu-\frac{t^2\sigma^2}{2}\}\notag\\
   \end{align}
   $$
   特别地，对于标准正态分布$\xi \sim \mathcal{N}(0,1)$
   $$
   f(t) = e^{-\frac{t^2}{2}}
   $$
   

## 8.3 特征函数的基本性质

本节我们将证明特征函数的一些基本性质.

### 8.3.1 有界性

首先

> $$
> |f(t)| \leqslant f(0) = 1
> $$

证明. 
$$
|\mathbb{E}[e^{it\xi}]| \leqslant \mathbb{E}[|e^{it\xi}|] = \mathbb{E}[1] = 1
$$

### 8.3.2 对称共轭

其次有

> $$
> f(-t) = \bar{f(t)}
> $$

显然.



### 8.3.3 线性相关

对于具有线性关系的随机变量$\eta = a\xi + b$

> $$
> f_{\eta}(t) = \mathbb{E}[e^{it\eta}] = \mathbb{E}[e^{it(a\xi+b)}] = e^{ibt}\mathbb{E}[e^{iat\xi}] = e^{ibt}f_{\xi}(at)
> $$

乘数直接体现在函数体内，偏置常数则作为函数值的乘数。



### 8.3.4 独立卷积简化

对于独立随机变量$\xi, \eta$有

> 若$\xi, \eta$独立*,* 则
> $$
> f_{\xi,\eta}(t) = f_{\xi}(t)f_{\eta}(t)
> $$

证明. 因为$\xi, \eta$独立，因此$e^{it\xi}, e^{it\eta}$独立，所以
$$
\mathbb{E}[e^{it(\xi+\eta)}] = \mathbb{E}[e^{it\xi}]\mathbb{E}[e^{it\eta}]
$$

我们知道, 两个独立的随机变量之和的分布函数等于它们的分布函数的卷积, 而卷积是比较复杂的. 而本命题说明, 此和的特征函数等于它们的特征函数的乘积, 这就简单多了——这是特征函数的优点之一.



### 8.3.5 一致连续性

我们先证明

> 对$\forall t, s \in \mathbb{R}$
> $$
> |f(t)-f(s)| \leqslant \mathbb{E}[|e^{i(t-s)\xi}-1|]
> $$

证明.
$$
|f(t)-f(s)| \leqslant |\mathbb{E}[e^{it\xi}]-\mathbb{E}[e^{is\xi}]| = |\mathbb{E}[e^{is\xi}(e^{i(t-s)\xi}-1)]| \leqslant \mathbb{E}[|e^{is\xi}(e^{i(t-s)\xi}-1)|] \leqslant \mathbb{E}[|e^{i(t-s)\xi}-1|]
$$


我们化简$|e^{i(t-s)\xi}-1|$
$$
|e^{i(t-s)\xi}-1| = \sqrt{[\cos((t-s)\xi)-1]^2+\sin^2((t-s)\xi)} = \sqrt{2-2\cos((t-s)\xi)}=2|\frac{\sin((t-s)\xi)}{2}|
$$
同时有不等式
$$
2|\sin(\frac{(t-s)\xi}{2})| \leqslant |t-s||\xi|
$$
因此
$$
|f(t)-f(s)| \leqslant \mathbb{E}[|e^{i(t-s)\xi}-1|] = \mathbb{E}[2|\sin(\frac{(t-s)\xi}{2})|] \leqslant |t-s|\cdot\mathbb{E}[|\xi|]
$$
所以对于$\forall \epsilon>0$，取$\delta = \frac{\epsilon}{\mathbb{E}[|\xi|]}$, 当$|t-s|<\delta$时
$$
|f(t)-f(s)| < \epsilon
$$
即

> 特征函数$f$在$\mathbb{R}$上**一致连续**。

我们可以用这条性质排除哪些函数不可能为特征函数：在$\mathbb{R}$上不一致连续。



###  8.3.6 多次可导性

#### 8.3.6.1 从随机变量可积性到特征函数可导性 

如果*ξ*具有较好的可积性, 那么其特征函数也具有较好的光滑性. 更精确地说, 我们有

> 若$||\xi||_n = \mathbb{E}[|\xi|^n] < \infty$，则$f(t)$至少$n$次可导，
>
> 并有
> $$
> f^{(k)}(t) = i^k\mathbb{E}[\xi^ke^{it\xi}], \forall k \leqslant n
> $$
> 且$f^{(k)}(t)$一致连续. 

证明.
$$
|f^{(k)}(t)-f^{(k)}(s)| \leqslant i^k\mathbb{E}[|\xi|^k|e^{i(t-s)\xi}-1|] \leqslant |t-s|\mathbb{E}[|\xi|^{k+1}]
$$
这个公式也揭示了如何使用特征函数求分布的$k$阶矩
$$
\mathbb{E}[\xi^k] = \frac{f^{(k)}(0)}{i^k}
$$




将上述结果应用到**Taylor公式**, 有

> 设$\mathbb{E}[|\xi|^n]<\infty$, 则
> $$
> f(t) = \sum_{k=0}^\infty\frac{f^{(k)}(0)}{k!}(t)^k=\sum_{k=0}^\infty\frac{(it)^k}{k!}\mathbb{E}[\xi^k]
> $$





#### 8.3.6.2 从特征函数可导性到随机变量可积性

以上都是由$\xi$的可积性导出$f$的光滑性; 若反过来, 要从$f$的光滑性判断$\xi$的可积性, 则有：

> 若$f^{(2n)}(t)$存在且有限*,* 则
> $$
> \mathbb{E}[\xi^{2n}] < \infty
> $$

推论：

> 若$f^{(2n)}(0)$存在且有限*,* 则对$\forall t$, $f^{(2n)}(t)$存在且有限.

我们可以用这条性质排除哪些函数不可能为特征函数：在$t=0$处$2n$次可导，但在其他的某个$t=t_0$处不可导. 



我们来看几个应用.

1. $$
   f(t) = \begin{cases}\sqrt{1-t^2}, |t| < 1\\
   0, |t| \geqslant 1\\\end{cases}
   $$

   $|t|<1$时, $f^{\prime}(t)=\frac{-2t}{\sqrt{1-t^2}}$. 故$f^{\prime}$在$t=0$处存在，但$t=1$处不存在. 故该函数不可能是特征函数.

2. $$
   f(t) = |\cos(t)|
   $$

   易见$f$在$t=0$处无穷次可导，但在$t=k\pi$处不可导. 故该函数不可能是特征函数.

3. $$
   f(t) = 1 - e^{-\frac{1}{|t|}}
   $$

   $f^{\prime}(t) = -\frac{e^{-\frac{1}{|t|}}}{t^2}$, 因此$f^{\prime}(0)=\mathbb{E}[\xi]=0$. 同时$f^{\prime\prime}(0)=0$, 故$D[\xi]=0$. 所以$\xi$的分布为$\xi = 0~\text{a.s.}$ 但是这样会导致$\xi$的特征函数为$f(t) \equiv 1$, 与原特征函数矛盾. 故该函数不可能是特征函数.



## 8.4 唯一性定理

### 8.4.1 唯一性定理

特征函数之所以有用, 植根于它和概率分布是一一对应的, 即我们有下面的唯一性定理.

> 设$\xi$与$\eta$是随机变量. 若
> $$
> f_{\xi}(t) = f_{\eta}(t)
> $$
> 即
> $$
> \mathbb{E}[e^{it\xi}] = \mathbb{E}[e^{it\eta}]
> $$
> 则$\xi, \eta$同分布.

### 8.4.2 高斯积分和狄利克雷积分

> **(高斯积分)**
> $$
> \int_{-\infty}^{\infty}e^{x^2}dx = \sqrt{\pi}
> $$

证明. 计$I = \int_{-\infty}^{\infty}e^{-x^2}dx$
$$
\begin{align}
I^2 &= \int_{-\infty}^{\infty}e^{-x^2}dx\int_{-\infty}^{\infty}e^{-y^2}dy \notag\\
&= \int_{-\infty}^{\infty}\int_{-\infty}^{\infty}e^{-(x^2+y^2)}dxdy \notag\\
&\stackrel{x=r\cos(\theta), y=r\sin(\theta)}{=} \int_{0}^{\infty}\int_{0}^{2\pi}re^{-r^2}d\theta dr \notag\\
&= \frac{1}{2}\int_{0}^{\infty}e^{-r^2}dr^2\int_{0}^{2\pi}d\theta \notag\\
&= \pi \notag\\
\end{align}
$$
因此$I= \sqrt{\pi}$

同理，对于类似标准正态分布的密度函数的积分
$$
\int_{-\infty}^{\infty}e^{\frac{x^2}{2}}dx \stackrel{t = \frac{x}{\sqrt{2}}}{=} \sqrt{2}\int_{-\infty}^{\infty}e^{t^2}dt = \sqrt{2\pi}
$$


> **(Dirichlet积分)**
> $$
> \int_{0}^{\infty}\frac{\sin(x)}{x}dx = \frac{\pi}{2}
> $$

特别地还有
$$
\int_{0}^{\infty}\frac{\sin(ax)}{x}dx = \frac{\pi}{2}\text{sgn}(a)
$$




### 8.4.3 反演公式

下面证明反演公式. 我们先证明这个公式的初级版. 我们知道特征函数是有界连续函数,因此在每个有限区间上都是可积的. 所谓初级版是在额外的条件
$$
\int_{-\infty}^{\infty}|f(t)|dt<\infty
$$
下考虑.



> **(反演公式)** 若$\int_{-\infty}^{\infty}|f(t)|dt<\infty$，则$F$是连续型分布函数*,* 且其密度函数为
> $$
> p(x) = \frac{1}{2\pi}\int_{-\infty}^{\infty}e^{itx}f(t)dt
> $$
