# 2 离散概型
具有可数个基本事件的试验的概率模型, 称为离散概型; 离散概型中, 如果样本点只是有限个, 则称为有限概型; 有限概型中, 如果各样本点出现的概率相等, 则称为古典概型。

## 2.1 古典概型
### 2.1.1
一个试验, 如果有$n$个可能的结果, 而每个结果出现的可能性都是$\frac1n$ , 则称为古典概率模型, 简称古典概型.

我们将用$\omega_1, ... , \omega_n$表示这些结果, 用$\Omega$表示它们全体：
$$ \Omega := \{ \omega_1, ... , \omega_n \}$$  
用$P(\omega_i)$表示$\omega_i$出现的概率(即可能性), 即
$$P (\omega_i) = \frac1n , \forall i = 1, ... , n$$

### 2.1.2
设掷一枚均匀硬币, 用1表示出现正面, 0表示出现反面. 则
$$\Omega = \{0, 1\}, P (i) = \frac12 , i = 0, 1$$
这个模型称为Bernoulli概型, 这个试验称为Bernoulli试验.

设一枚均匀硬币掷n次, 还是用1表示出现正面, 0表示出现反面. 则
$$ \Omega = \{(i_1, i_2, ... , i_n), i_k = 0, 1, \forall k = 1, 2, ... , n\}, P((i_1, i_2, ... , i_n)) = 2^{−n}, \forall (i1, i2, · · · , in) \in \Omega $$
这个模型称为n重Bernoulli概型, 或依旧简称为Bernoulli概型. 这个试验称为n重Bernoulli试验. 

因为每个结果都是等可能的, 所以对事件$A \subset \Omega$, 定义$A$发生的概率为
$$P (A) := \frac{N(A)}{N (\Omega)} $$
其中$N(A)$表示集合$A$中的元素个数. 称$N(A)$为有利事件的样本点数, $N(Ω)$为总样本点数.

这样定义的概率有如下性质:
- $\forall A \subset \Omega, 0 \leqslant P (A) \leqslant 1$
- $ P(\Omega) = 1, P(\emptyset) = 0 $
- 设$ m \in N^+$, 且$\forall i = 1, ... , m, A_i \subset \Omega $且两两不交. 令$A := \sum_{i=1}^{m}A_i$, 则有加法公式$P(A) = \sum_{i=1}^{m}P(A_i)$  

古典概型从理论上讲是简单的, 关键是要计算$P(A)$, 这就归结为计算$N(A)$与$N(Ω)$. 从而古典概型的问题其实就是计数问题. 这个问题看起来简单, 但在具体问题中计算却可能十分困难.
当问题太复杂, 一时不能直接计算$N(A)$时, 有一个简单而往往相当实用的方法, 即, 可以考虑把A分成几部分,比如
$$A = A_1 + A_2 + ... + A_m$$
然后分别计算$N(A_i)$. 
由于
$$N(A) = N(A_1) + N(A_2) + ... + N(A_m)$$
所以由此可计算出N (A). 我们将这个方法称为加法原理.

### 2.1.3
无放回有顺序抽样:
> 从$/{1, 2, ... , n/}$中取出$m(\leqslant n)$个数, 依取出的顺序排列, 问一共有多少结果
$$A_n^m = \frac{n!}{(n-m)!}$$

有放回有顺序抽样:
> 从$/{1, 2, ... , n/}$中取出一个, 记录下号码, 放回, 再取出一个记录下号码, 再放回. 如此重复$m$次. 问一共有多少种不同的结果.
$$B_n^m = n^m$$

无放回无顺序抽样:
> 从$/{1, 2, ... , n/}$中取出$m(\leqslant n)$个数, 不计顺序, 问一共有多少结果
$$C_n^m = \frac{n!}{m!(n-m)!}$$

有放回无顺序抽样:
> 从$/{1, 2, ... , n/}$中取出一个, 记录下号码, 放回, 再取出一个记录下号码, 再放回. 如此重复$m$次. 但最后记录下的结果不计顺序. 问一共有多少种不同的结果.
$$D_n^m = C_{n+m-1}^m$$

## 2.2 有限概型
### 2.2.1
所谓有限概型, 其特点是试验只有有限个结果(这和古典概型一样), 但每个结果出现的概率不必一样.  

设一个试验可能的结果有$n$个:
$$\Omega = \{\omega_1, ... , \omega_n\}$$
设$\omega_i$出现的概率为$p_i$, $p_i > 0, \forall i = 1, ... , n$, $\sum_{i=1}^{n}p_i = 1$. 令
$$P(\omega_i) := p_i$$
而对任意$A \subset \Omega$, 令
$$P(A) := \sum_{\omega \in A} P(\omega)$$
则$(\Omega, P)$称为有限概型, 称$P(A)$为事件$A$的概率.

### 2.2.2
掷一枚可能未必均匀的硬币, 仍然用1表示出现正面, 0表示出现反面. 此时仍有
$$\Omega = {0, 1}$$
但
$$P(1) = p, P(0) = q, p, q > 0, p + q = 1$$
这个模型也称为Bernoulli概型.  

将上面那枚硬币掷n次, 则样本空间为
$$\Omega := \{(i_1, i_2, · · · , i_n), i_k = 0, 1, \forall k = 1, 2, ... , n\}$$
令
$$P((i_1, i_2, ... , i_n)) := p^{\sum_{k=1}^{n}i_k}q^{n−\sum_{k=1}^{n}i_k}, \forall (i_1, i_2, ... , i_n)$$
这个模型仍然称为n重Bernoulli概型, 或称为**二项概型**.

如果把硬币换为(未必均匀的)骰子, 那么每次可能出现的结果就不是两个而是六个.
此时可取
$$\Omega := {\omega = (\omega_1, ... , \omega_n) : \omega_i \in \{1, 2, ..., 6\}}, P(\omega) := \prod_{k=1}^{6}{p_k}^{\alpha_k(\omega)}$$
其中
$p_k > 0, \sum_{i=1}^{6}p_k = 1, α_k(\omega) = \sum_{i=1}^{n}\delta_{k,\omega_i}$, 即$\alpha_k(\omega)$是$\omega$的分量中等于$k$的个数.  
这个模型称为**多项概型**.

### 2.2.3

虽然不再是古典概型, 但由定义可以看出, 有限概型中的概率仍然保留有以下古典概率
所具有的基本性质:  

- $\forall A, 0 \leqslant P(A) \leqslant 1$
- $P(\Omega) = 1, P (\emptyset) = 0$
- 单调性: $A \subset B \Rightarrow P(A) \leqslant P(B)$
- 有限可加性: $\forall k$及$A_1, ... , A_k$, 若$A_iA_j = \emptyset$, $\forall i \neq j$, 则有加法公式
$$ P(\sum_{i=1}^{k}A_i) = \sum_{i=1}^{k}P(A_i)$$


## 2.3 随机变量

### 2.3.1

$\Omega$上的函数, 称为**随机变量**.  

每个随机变量都对应着一个重要的量, 即其期望.

> 设
> $$\Omega = \{\omega_1, \dots , \omega_n\}$$
> 为样本空间, $P$是其上的概率. 设$\xi$是其上的随机变量, 定义其期望为其(加权)平均值
> $$\mathbb{E}[\xi] := \sum_{i=1}^{n} \xi(\omega_i)P(\omega_i)$$

在古典概型的特殊情形, 期望$\mathbb{E}[\xi] := \frac{1}{n} \sum_{i=1}^{n} \xi(\omega_i)$
就是普通的算术平均值. 一般情形下则是一个加权平均值. 之所以要加权, 是因为每个$\omega_i$发生的概率不一样, 所以对不同的$i$, $\xi(\omega_i)$出现的概率也不一样, 因而在取平均值时占的比重也应该不一样

我们有:
- 设$\xi, \eta$是随机变量, $a, b \in \mathbb{R}$, 则
$$\mathbb{E}[a\xi + b\eta] = a\mathbb{E}[\xi] + b\mathbb{E}[\eta]$$
- 设$A \subset \Omega$, 则
$$\mathbb{E}[I_A] = P(A)$$
- 设$\xi$的值域为$\{x_1, \dots , x_m\}$, $f$为$\mathbb{R}$上的函数, 则$$\mathbb{E}[f(\xi)] = \sum_{i=1}^{n} f(x_k)P(\xi = x_k)$$
特别地, 当$f(x) = x$时,$$\mathbb{E}[\xi] = \sum_{i=1}^{n} x_kP(\xi = x_k)$$
这里及以后我们使用缩写$\{\xi = x\} = \{\omega : \xi(\omega) = x\}$  

从第三个结果我们看到, 随机变量的期望只与其值域$\{x_i\}$和概率$p_i := P(\xi = x_i)$有关, 也就是说只与$\{(x_i, p_i)\}$有关. 由于$\{(x_i, p_i)\}$描述了$\xi$的值是以怎样的概率分布在各处的, 所以我们给出下面的定义  

> 设$\xi$是随机变量, 值域为$\{x_1, \dots , x_m\}$. 令$p_i = P(\xi = x_i)$. 则
> $$\{(x_i, p_i), i =1, \dots , m\}$$
> 称为$\xi$的概率分布, 或概率分布列, 简称为$\xi$的分布或分布列, 也称$\xi$服从这个分布.  

注意这里$x_i, i = 1, 2, \dots , m$是互异的, 并且$\omega \mapsto \xi(\omega)$未必是单射, 即一个$\{\xi = x_i\}$中可能含有多个$\omega$.  

### 2.3.2
下面我们介绍几个常用的分布.

Bernoulli分布.   
考虑掷硬币的试验. 设出现正面的概率为$p \in (0, 1)$. 令$q = 1 − p$.以1表示出现正面, 0表示出现反面.  
则概率空间为
$$\Omega = {0, 1}, P(0) = q, P(1) = p$$
令$\xi(\omega) = \omega$.则$\xi$的分布为
$$\{(1, p), (0, q)\}$$
这个分布称为Bernoulli分布, 记为$B(p)$. 从此以后, 我们将用$\xi \sim B(p)$表示$\xi$服从Bernoulli分布.     
而
$$\mathbb{E}[\xi] = p$$

二项分布.   
将上面的硬币掷n次. 同样以1表示出现正面, 0表示出现反面, 则概率空间为
$$\Omega := \{\omega := (\omega_1, \dots , \omega_n), \omega_i \in \{0, 1\}\}$$
以$\xi$表示这$n$次试验中正面出现的次数, 也称为成功的次数, 即
$$\xi(\omega) = \sum_{i=1}^{n} \omega_i$$
则
$$P(\xi = k) = P\left((\omega_1, \dots , \omega_n) : \sum_{i=1}^{n} \omega_i = k\right) = C_n^k p^kq^{n−k}$$
所以$\xi$的分布为
$$\{(k, C_n^k p^kq^{n−k}), k = 0, 1, · · · , n\}$$
这个分布记为$B(n, p)$. 因此$\xi \sim B(n, p)$.  
下面我们求$\mathbb{E}[\xi]$.定义
$$\xi_i(\omega) = \omega_i$$
即$\xi_i$是只依赖于第$i$次试验的随机变量: 当第$i$次正面时, $\xi_i = 1$; 反面时, $\xi_i = 0$. 而
$$P (\xi_i = 1) = \sum_{\omega_i=1} p^{\sum_{j \neq i}\omega_j}q^{n - 1 - \sum_{j \neq i}\omega_j} p$$
其中$\sum_{\omega_i=1}\dots$是对所有可能的满足$\omega_i = 1$的$\omega$求和.  
因此
$$\sum_{\omega_i=1} p^{\sum_{j \neq i}\omega_j}q^{n - 1 - \sum_{j \neq i}\omega_j} = (p + q)^{n-1} = 1$$
从而
$$P(\xi_i = 1) = p, P(\xi_i = 0) = q$$
所以$\xi_i \sim B(p)$. 由于$\xi = \sum_{i=1}^{n} \xi_i$. 因此
$$\mathbb{E}[\xi] = \mathbb{E}[\sum_{i=1}^{n} \xi_i] = \sum_{i=1}^{n}\mathbb{E}[\xi_i] = np$$  

多项分布.   
样本空间为
$$\Omega = \{\omega = (\omega_1, \dots , \omega_n), \omega_i \in \{1, 2, \dots , m\}\}$$
设$p_i > 0, \sum_{i=1}^{n} p_i = 1$. 定义
$$p(\omega) = \prod_{k=1}^{m} p_k ^ {\sum_{i=1}^{n} \delta_{k, \omega_i}}$$
令$\xi_k$表示在$n$次试验中结果$k$出现的次数, 则
$$\xi_k(\omega) := \sum_{i=1}^{n} \delta_{k, \omega_i}, k = 1, 2, \dots, m$$ 
而对$j_k \in \mathbb{N}^+, \sum_{k=1}^{m} j_k = n$, 有
$$P(\xi_1 = j_1, · · · , \xi_m = j_m) = C_{n}^{j_1,···,j_m}p_1^{j_1} \dots p_m^{j_m} = C_{n}^{j_1,···,j_m} \prod_{k=1}^{m}p_k^{j_k}$$
其中$C_{n}^{j_1,···,j_m} = \frac{n!}{\prod_{k=1}^{m} (j_k!)}$.  

## 2.4 条件概率
### 2.4.1
任何概率都是在一定条件下考虑的.  
设A为事件. 如果我们现在确切地知道A已经发生, 而进一步问在此条件下, 某个事
件B发生的概率是多少?
怎么考虑这个问题呢? 

我们先看古典概型的情况.这时, 总样本的空间就缩小了,但还是运用一样的原则：用有利事件的样本点数除以总样本点数. 这时条件为A已发生, 同时又要B发生, 所以有利事件的样本点数是$N(AB)$, 而总样本点数是$N(A)$. 从而, 如果我们以$P(B \mid A)$记这个概率的话, 则
$$P(B \mid A) = \frac{N(AB)}{N(A)}$$
如果用原概率表示, 则有
$$P(B \mid A) = \frac{\frac{N(AB)}{N(\Omega)}}{\frac{N(A)}{N(\Omega)}} = \frac{P(AB)}{P(A)}$$

下面再看有限概型中条件概率的定义. 设$\Omega = \{\omega_1, \dots , \omega_n\}$, $A,B \subset \Omega$. 此时因为不再是古典概型, 所以不能通过数样本点的个数来定义条件概率. 不过基本原则还是适用的, 即这时样本空间缩小了, 即由$\Omega$变成了$A$, $A$变成必然事件了, 因而$A$的概率由$P(A)$变成了1. $A$成为样本空间后, 仍然是有限概型. 根据比例原则A中每个样本点的原概率乘以因子$\frac{1}{P(A)}$就形成了$A$上的一个概率. 这样, $AB$发生的(条件)概率也就变成了
$$P(B \mid A) = \sum_{\omega \in AB} \frac{1}{P(A)} P(\omega) = \frac{1}{P(A)} \sum_{\omega \in AB}P(\omega) = \frac{P(AB)}{P(A)}$$
形式上它和古典概型里的定义是一致的, 但摆脱了古典概型的束缚.  
总结起来, 便有了下面的定义.

> 设$A, B$为事件且$P(A)>0$. $A$发生的条件下$B$发生的条件概率定义为
> $$P(B \mid A) := \frac{P(AB)}{P(A)}$$

条件概率有如下性质:  

- $$P (A \mid A) = 1, P (\emptyset \mid A) = 0$$  

- $$ B \subset C \Rightarrow P(B \mid A) \leqslant P(C \mid A)$$  

- $$ A_i A_j = \emptyset, \forall i, j = 1, \dots , i \neq j \Rightarrow P(\sum_{i=1}^{n}A_i \mid A) = \sum_{i=1}^{n} P(A_i \mid A)$$  

- $$ P(\cup_{i=1}^{n}A_i \mid A) \leqslant \sum_{i=1}^{n} P(A_i \mid A) $$

### 2.4.2  

因为在计算$P(B \mid A)$时, 样本空间缩小了, 所以计算有可能方便些. 把定义条件概率的公式变一下形, 就成为
$$P(BA) = P(A)P(B \mid A)$$
这个公式提供了计算上的一种便利: 把一个可能比较复杂的$BA$的计算分解为分别计算$P (A)$及$P(B \mid A)$.  

反复利用这个公式, 我们可得到下面的一般乘法公式:
> $$ P(A_1 A_2 \dots A_n) = P (A_1) P(A_2 \mid A_1) P(A_3 \mid A_1A_2) \dots P (A_n \mid A_1 \dots A_{n−1})$$

### 2.4.3
贝叶斯公式.  
> 若$P(A)P(B) > 0$，有
> $$ P(AB) = P(A)P(B \mid A) = P(B)P(A \mid B) $$
因此
>$$ P(A \mid B) = \frac{P(A)P(B \mid A)}{P(B)} $$
这就是所谓的Bayes公式, 其中$P(A)$称为先验概率, $P(A \mid B)$称为后验概率. 其用处在于: 如果把$A$理解为原因, $B$理解为结果, 那么$P(B \mid A)$就是已知原因推测结果, 而$P(A \mid B)$就是知道结果, 推测导致该结果的原因.

## 2.5 全概率公式

### 2.5.1

上面是用概率来定义条件概率, 但在理论研究和实际问题中, 方向往往是相反的, 即我们往往是在各种不同的条件下搞清了条件概率, 然后综合起来就得到无条件的概率.  

> 如果样本空间可以分割为若干块
> $$\Omega = \Omega_1 + \dots + \Omega_n$$
> 那么对任意事件$A \subset \sum_{i=1}^{n}\Omega_i$, 都有
> $$ 
>    \begin{align}
>        P(A) &= P(A\Omega_1) + \dots + P(A\Omega_n) \notag \\
>        &= P(\Omega_1)P(A \mid \Omega_1) + \dots + P(\Omega_n)P(A \mid \Omega_n) \notag
>    \end{align}
>$$

这个公式称为全概率公式, 它告诉我们的是, 可以先分若干情况, 在每一种情况下分别计算条件概率(让我们姑且理解为部分概率或偏概率), 然后对这些概率加权平均, 即得到所求的概率. 相对于前面的限制于各部分的概率而言, 这是一个整体概率, 无条件的概率, 即全概率, 所以该公式就叫全概率公式了.  

我们应该注意到, 对给定的事件$A$, 并不需要
$$\Omega_1 + \dots + \Omega_n = \Omega $$
而只需要
$$\Omega_1 + \dots + \Omega_n \supset A $$
全概率公式就依然成立.  

这个公式背后的思想非常自然：如果直接计算一个概率有困难, 那么我们就分情况处理, 也就是先在各种额外的条件下计算, 然后将计算的结果通过加权平均综合起来, 而权重正是
诸$P(\Omega_i)$.

### 2.5.2

最后我们介绍全概率公式的一种推广的形式.  
此后, 我们说$\mathscr{P} = \{\Omega_1, \dots , \Omega_n\}$构成$\Omega$的一个分割, 是指
$$\Omega_1 + \dots + \Omega_n = \Omega$$
全概率公式提示我们, 对一个分割$\mathscr{P} = \{\Omega_1, \dots , \Omega_n\}, A \subset \Omega$, 需要同时考虑条件概率$P(A \mid \Omega_1), \dots , P(A \mid \Omega_n)$. 对此, 引进下面的概念是方便的：
$$ P(A \mid \mathscr{P})(\omega) := \sum_{i=1}^{n} P(A \mid \Omega_i)I_{\Omega_i}(\omega) $$
$P(A \mid \mathscr{P})$称为给定分割$\mathscr{P}$时$A$发生的条件概率.  
因此当$\omega, A$均变动时, 给定$\mathscr{P}$时的条件概率是一个二元函数:
$$(\omega, A) \mapsto P(A \mid \mathscr{P})(\omega)$$

易见, 对固定的$A$, $\omega \mapsto P(A \mid \mathscr{P})(\omega)$是取值于[0, 1]的随机变量, 并且在每个$\Omega_i$上为常数$P(A \mid \Omega_i)$. 也就是说, $\omega$其实是起了一个指示作用, 它在哪个$\Omega_i$里, $P(A \mid \mathscr{P})(\omega)$就是给定哪个$\Omega_i$时的条件概率. 
而对于固定的$\omega$, $A \mapsto P(A \mid \mathscr{P})(\omega)$是概率, 即它满足定理2.2.2中的四条性质.  

对固定的$\mathscr{P}$, 以简洁一点的记号$P(A, \omega)$表示这个函数, 并对任何一个随机变量$\xi$, 对固定的$\omega$, 定义
$$\mathbb{E}[\xi \mid \mathscr{P}] (\omega) := \mathbb{E}^{P(·,\omega)}[\xi(\omega^{\prime})] := \sum_{\omega^{\prime}} \xi(\omega^{\prime})P(\omega^{\prime}, \omega)$$
它称为关于$\mathscr{P}$的条件期望, 注意它仍是一个随机变量, 且在每个$\Omega_i$上恒等于常数. 特别地, 由于
$$\mathbb{E}[I_A|\mathscr{P}] (\omega) = \sum_{\omega^{\prime}} I_A(\omega^{\prime})P(\omega^{\prime} \mid \mathscr{P})(\omega) = \sum_{i=1}^{n} P(A \mid \Omega_i)I_{\Omega_i}(\omega) = P(A \mid \mathscr{P})(\omega)$$
所以全概率公式可以表示为
$$
    P(A) = \mathbb{E}[P(A \mid \mathscr{P})] = \mathbb{E}[\mathbb{E}[I_A \mid \mathscr{P}]]
$$
同理, 对于一般的$\xi$, 因为在$\omega \in \Omega_i$上$P(\omega^{\prime} \mid \mathscr{P})(\omega) = P(\omega^{\prime} \mid \Omega_i)$, 故有
$$
    \mathbb{E}[\xi \mid \mathscr{P}] (\omega) = \sum_{\omega^{\prime}} \xi(\omega^{\prime})P(\omega^{\prime} \mid \Omega_i)
$$
因为此物在每个$\Omega_i$上为常数, 故由期望公式有
$$
    \begin{align}
        \mathbb{E}[\mathbb{E}[\xi \mid \mathscr{P}]]
        &= \sum_{i=1}^{n} P(\Omega_i) \left(\sum_{\omega^{\prime}} \xi(\omega^{\prime})P(\omega^{\prime} \mid \Omega_i)\right) \notag \\
        &=  \sum_{\omega^{\prime}} \xi(\omega^{\prime}) \left(\sum_{i=1}^{n} P(\Omega_i)P(\omega^{\prime} \mid \Omega_i)\right) \notag \\
        &=  \sum_{\omega^{\prime}} \xi(\omega^{\prime}) P(\omega^{\prime}) \notag \\
    \end{align}
$$
因此有
$$
    \mathbb{E}[\xi] =\mathbb{E}[\mathbb{E}[\xi \mid \mathscr{P}]]
$$
这里讲得比较书卷气，可以参考2.9节的说法。

## 2.6 独立性

### 2.6.1

> 设$A, B$是事件, 若
> $$P(AB) = P(A)P(B)$$
> 则称$A, B$独立.  

显然, 一个不可能事件与任何事件都是独立的, 一个必然事件与任何事件也都是独立的.  

此外, 由条件概率的定义可直接推出  

>若$P(A) > 0$, 那么$A$与$B$独立就等价于
>$$P(B \mid A) = P(B)$$

这个命题说明, 独立就意味着无论有无$A$这个条件, $B$发生的概率都不受影响——这符合
独立这个词的含义, 即不依赖.  

由事件的独立性概念可衍生出事件类的独立性概念. 我们先定义什么叫事件类或者集类:  
> 设$\Omega$为一样本空间. 以$\Omega$的子集为元素的集合称为事件类或者集类

而所谓集类的独立性是指:  
> 设$\mathscr{A}, \mathscr{B}$为集类, 若$\forall A \in \mathscr{A} , B \in \mathscr{B}, A, B$都独立, 则称$\mathscr{A}, \mathscr{B}$独立.

### 2.6.2

现在我们问：如果$A, B$都与$C$独立, 那么$AB$、$A \cup B$及$A \setminus B$仍然与$C$独立吗?

首先容易证明:
> 如果$A, B$为事件, $A \supset B$且$A, B$都与$C$独立, 那么$A − B$也与$C$独立.  

$$
    \begin{align}
        P((A − B)C) &= P(AC − BC) \notag \\
        &= P(AC) − P(BC) \notag \\
        &= P(A)P(C) − P(B)P(C) \notag \\
        &= [P(A) − P(B)]P(C) \notag \\
        &= P(A − B)P(C) \notag \\
    \end{align}
$$

因为$\Omega$与所有事件都独立, 所以利用上述结果得到:
> 若$A, B$独立, 则$\{A, A^c\}$与$\{B, B^c\}$独立.

不幸的是, 下面的例子表明, 即A、B都与C独立时一般不能推出AB也与C独立.  
在抛2次均匀硬币的试验中, 样本空间为$\Omega = \{(1,1), (1,0), (0,1), (0,0)\}$. 令 $A =
\{(1,1), (1,0)\}, B = \{(1,1), (0,1)\}, C = \{(1,1), (0,0)\}$  
这是古典概型, 显然$P(A) = P(B) = P(C) = \frac12$, $P(AB) = P(BC) = P(AC) = \frac14$ 
因此, $A$, $B$都与$C$独立, 但$P((AB)C) = P(ABC) = \frac14$, $P(AB)P(C) = \frac18$
所以$AB$与$C$不独立. 同理可证$A \cup B$与$C$也不独立.

直观上可以这么理解这个反例. 事件$C$的发生与否不是没有影响事件$A$和$B$, 只是这种影
响没有改变其概率而已, 亦即$P(A \mid C) = P(A), P(B \mid C) = P(B)$, 这种影响造成的后果是事件$C$的发生却影响事件$AB$的概率了.  

进一步的思考发现, 在此类问题中, 关键是$AB$是否与$C$独立. 一旦$AB$与$C$独立, 那么不
光$A \setminus B$, 连$A \cup B$也都与$C$独立了, 因为我们有
$$
    \begin{align}
        P((A \cup B)C) &= P(AC \cup (B − AB)C) \notag \\
        &= P(AC) + P((B − AB)C) \notag \\
        &= P(A)P(C) + P(B − AB)P (C) \notag \\
        &= (P (A) + P (B) − P (AB))P (C) \notag \\
        &= P (A ∪ B)P (C) \notag \\
    \end{align}
$$
这就引导我们考虑更一般的问题: 在什么情况下可由两个集类的独立性推出更大的集类的独立性? 看来交集在这里会起到关键的作用. 为准确地回答这个问题, 我们需要准备一些集类方面的知识.  

## 2.7 集合论：$\pi$-类, $\lambda_0$-类与代数

我们曾经定义了事件间的各种运算. 本节我们定义对其中一些运算封闭的集类, 并讨论其基本性质. 我们将证明所谓的$\pi − \lambda_0$定理. 这个定理是后面要讲的$\pi − \lambda$定理的初级形式, 且前者的证明已经包含了后者的证明中最困难的部分.  
我们固定一个样本空间$\Omega$, 考虑在各种运算下封闭的集类.  

### 2.7.1 $\pi$-类

> 一个非空集类$\mathscr{P}$, 若对交封闭, 即满足
> $$A, B \in \mathscr{P} \Rightarrow AB \in P$$
> 则称为$\pi$-类.  

下面是几个例子:  

- 设 $\Omega = \mathbb{R}^n$ (实际上可以是任何一个拓扑空间), $\mathscr{P}$是所有开集(或闭集)全体. 则$\mathscr{P}$是$\pi$-类.  
- 设 $\Omega = \mathbb{R}$, $\mathscr{P} := \{(−\infty, a), a \in \mathbb{R}\}$, 则$\mathscr{P}$是$\pi$-类.  
- 设 $\Omega = [0, 1)$, $\mathscr{P} := \{[0, a), a \in [0, 1]\}$, 则$\mathscr{P}$是$\pi$-类.  
- 设 $\Omega = \mathbb{R}^n$, $\mathscr{P} := \{[a_1, b_1) \times \dots [an, bn), −\infty < a_i \leqslant b_i < \infty, \forall i = 1, \dots , n\}$. 则$\mathscr{P}$是$\pi$-类.

### 2.7.2 $\lambda_0$-类

> 一个集类$\mathscr{L}_0$, 若包含$\Omega$且对真差封闭, 即满足
> $$ A, B \in \mathscr{L}_0, A \subset B \Rightarrow B − A \in \mathscr{L}_0 $$
> 则称为$\lambda_0$-类.  

当然, 一个$\lambda_0$-类里既有$\Omega$(这个是定义)也有空集$\emptyset$($\Omega-\Omega$).

下面是几个例子:  

- 设$\Omega = [0, 1)$. 令$\mathscr{L}_0 := \{\sum_{i=1}^{n}[a_i, b_i), 0 \leqslant a_1 \leqslant b_1 \leqslant a_2 \leqslant b_2 \leqslant \dots \leqslant a_n \leqslant b_n \leqslant 1, n = 1, 2, \dots\}$. 则$\mathscr{L}_0$为$\lambda_0$-类.  
- 设$\Omega$为任一空间, $A, B \subset \Omega$, $AB \neq \emptyset$. 令
$\mathscr{L}_0 := \{\Omega, \emptyset, A, B, A^c, B^c\}$. 则$\mathscr{L}_0$为$\lambda_0$-类.  
此外容易看出, 任何一个包含了$\{A, B\}$的$\lambda_0$-类都包含了这个$\mathscr{L}_0$. 所以$\mathscr{L}_0$为包含了$A$与$B$的最小的$\lambda_0$-类.
- 设$A$是事件, 令$\mathscr{L}_0 := \{B, B与A独立\}$. 则$\mathscr{L}_0$为$\lambda_0$-类. 这是因为, 当$B, C \in \mathscr{L}_0$且$B \subset C$时, 有$C − B \in \mathscr{L}_0$.
- 设$P$, $Q$都是定义在$\Omega$的子集上的函数, $P(\Omega) = Q(\Omega)$且$AB = \emptyset \Rightarrow P(A + B) = P(A) + P(B), Q(A + B) = Q(A) + Q(B)$.令$\mathscr{L}_0 := \{A : P(A) = Q(A)\}$. 则$\mathscr{L}_0$为$\lambda_0$-类.  

显然, 若$\mathscr{L}_0$为$\lambda_0$-类, 则$A \in \mathscr{L}_0$时有$A^c = \Omega − A \in \mathscr{L}_0$, 即它对余封闭.

我们还可以证明：
> 一个包含了$\Omega$的集类为$\lambda_0$-类的充要条件是它对不交并及余封闭.  

必要性：设$\mathscr{L}_0$为$\lambda_0$-类. 设$A, B \in \mathscr{L}_0$且$AB = \emptyset$. 则$B \subset A^c$. 因此
$$A^cB^c = A^c − B \in \mathscr{L}_0$$
于是
$$A + B = (A^cB^c)^c \in \mathscr{L}_0$$
充分性：设$\mathscr{L}_0$含有$\Omega$且对不交并及余封闭. 设$A, B \in \mathscr{L}_0$且$A \subset B$. 则$AB = \emptyset$. 故
$$B^c + A \in \mathscr{L}_0$$
因此
$$B − A = (B^c + A)^c \in \mathscr{L}_0$$
证完.

### 2.7.3 代数

因此, 我们可将$\lambda_0$-类理解为含有$\Omega$且对不交并与余封闭的集类. 若去掉“不交”的限制, 加强为对任意两个集合的并封闭, 则得到代数的概念.

> 一个集类 $\mathscr{A}$ , 若满足  
> (i) $\Omega \in \mathscr{A}$ ;  
> (ii) 对并与余封闭: $A, B \in \mathscr{A} \Rightarrow A \cup B \in \mathscr{A}, A^c \in \mathscr{A}$  
> 则称为代数.  

所以$\lambda_0$-类与代数的差别就在于对并封闭的要求中, 有无不交的前提.  

下面是几个例子:  

- $\Omega$的所有子集构成的集类为代数.
- 集类$\{\emptyset, \Omega\}$构成代数.
- 设$N(\Omega) = +\infty$, 令$A := \{A \subset \Omega : N(A) \wedge N(A^c) < \infty\}$.则A是代数. 

我们立即有：

> 代数对交与差均封闭.

证明. 设$\mathscr{A}$为代数, $A, B \in \mathscr{A}$ . 则
$$AB = (A^c \cup B^c)^c \in \mathscr{A}$$
$$B \setminus A = BA^c \in \mathscr{A}$$

在验证一个非空集类是否为代数时, 下面的结果常常很方便.

> 一个非空集类若对余与交两种运算封闭, 则为代数.

证明. 设这集类是$\mathscr{A}$ , 并设$A \in \mathscr{A}$ . 因为$\mathscr{A}$对余封闭, 所以$A^c \in \mathscr{A}$ .  
因为$A$对交封闭, 所以$\emptyset = AA^c \in \mathscr{A}$.  
再用一次对余封闭, 得$\Omega = (\emptyset)^c \in \mathscr{A}$.  
设$A, B \in \mathscr{A}$ , 则$A^c, B^c \in \mathscr{A}$ .  
因此$A \cup B = (A^cB^c)^c \in \mathscr{A}$ .  
所以A 为代数.  

显然, 我们还有
> 一个集类$\mathscr{A}$为代数的充要条件是它既是$\pi$-类又是$\lambda_0$-类.  

由此我们也可以认为, 比之于代数, $\lambda_0$-类差的就是对交封闭. 

### 2.7.4 $\pi$ - $\lambda_0$ 定理

我们下面将要证明本节最重要的结果, 即从一个$\pi$-类出发扩张而得到的$\lambda_0$-类依然保留对交封闭这个重要的性质, 因此也就一定是代数. 为此先引入两个概念.  
> 任给一个非空集类$\mathscr{D}$, 一定存在一个代数$\mathscr{A_0}$, 使得对任意代数$\mathscr{A} \supset \mathscr{D}$, 都有
> $$\mathscr{D} \subset \mathscr{A_0} \subset \mathscr{A}$$

证明. 我们容易找到
$$\mathscr{A_0} = \bigcap \mathscr{A}$$
其中右边的交跑遍所有包含了$\mathscr{D}$的代数. 注意这个定义是有意义的, 因为至少有一个代数包含了$\mathscr{D}$, 这就是由$\Omega$的所有子集构成的代数. 作为诸代数的交, $\mathscr{A_0}$自然也是代数, 且是包含了$\mathscr{D}$的最小的代数.

由此，

> 上面命题中的$\mathscr{A_0}$称为$\mathscr{D}$生成的代数, 记为$\alpha(\mathscr{D})$.  

类似地, 我们有:
> 任给一个集类$\mathscr{D}$, 存在一个$\lambda_0$-类$\mathscr{L}_0$, 使得对任意$\lambda_0$-类$\mathscr{L} \supset \mathscr{D}$, 都有
> $$\mathscr{D} \subset \mathscr{L}_0 \subset \mathscr{L}$$

以及

> 上面命题中的$\mathscr{L}_0$称为$\mathscr{D}$生成的$\lambda_0$-类, 记为$\lambda_0(\mathscr{D})$.  

由于代数皆为$\lambda_0$-类, 所以对任意一个集类$\mathscr{C}$ , 皆有$\lambda_0(\mathscr{C}) \subset \alpha(\mathscr{C})$. 然而一般说来反过来是不成立的. 不过若$\mathscr{C}$是$\pi$-类, 反过来就成立, 即我们有  

> ($\pi$ - $\lambda_0$ 定理). 若$\mathscr{C}$为$\pi$-类, 则$\lambda_0(\mathscr{C}) = \alpha(\mathscr{C})$  

这个定理能够成立的理由是下面这个关键事实：一个$\pi$-类生成的$\lambda_0$-类仍然是$\pi$-类. 证明如下:  

证明. 显然$\lambda_0(\mathscr{C}) \subset \alpha(\mathscr{C})$, 因此只需证明$\lambda_0(\mathscr{C})$为代数.  
又因为一个集类$\mathscr{A}$为代数的充要条件是它既是$\pi$-类又是$\lambda_0$-类, 又只需证明它是$\pi$-类.  
构造一个集类$\mathscr{B}_1$满足
$$ \mathscr{B}_1 := \{B \in \lambda_0(\mathscr{C}) : BA \in \lambda_0(\mathscr{C}), \forall A \in \mathscr{C} \}$$  
显然取$B = A$一定满足, 则$\mathscr{C} \subset \mathscr{B}_1 \subset \lambda_0(\mathscr{C})$;
显然取$B = \Omega$一定满足, 则$\Omega \in \mathscr{B}_1$.  
再设
$$ B_1, B_2 \in \mathscr{B}_1, B_1 \subset B_2$$
则$\forall A \in \mathscr{C}$有
$$ B_1A, B_2A \in \lambda_0(\mathscr{C}), B_1A \subset B_2A $$
从而
$$(B_2 - B_1)A = B_2A - B_1A \in \lambda_0(\mathscr{C})$$
故
$$B_2 - B_1 \in \mathscr{B}_1$$
因此$\mathscr{B}_1$是(包含了$\mathscr{C}$的)$\lambda_0$-类. 从而证得  
$$\mathscr{B}_1 = \lambda_0(\mathscr{C})$$  
再令
$$ \mathscr{B}_2 := \{B \in \lambda_0(\mathscr{C}) : BA \in \lambda_0(\mathscr{C}), \forall A \in  \lambda_0(\mathscr{C}) \}$$  
由刚刚证明的结论, 有$\mathscr{C} \subset \mathscr{B}_2$. 再将刚刚用的证明方法如法泡制, 可证 B2为λ0-类. 因此$\mathscr{B}_2 = \lambda_0(\mathscr{C})$, 而这就是说$\lambda_0(\mathscr{C})$是$\pi$-类.

## 2.8 重温独立性

### 2.8.1

现在可以回答前面的问题了,即是否可以从较小的事件类间的独立性推出较大的事件类
间的独立性的问题.我们有:

> 设$\mathscr{C}_1$与$\mathscr{C}_2$是$\pi$-类. 若$\mathscr{C}_1$与$\mathscr{C}_2$独立, 那么$\alpha(\mathscr{C}_1)$与$\alpha(\mathscr{C}_2)$独立.  

证明. 令 
$$\mathscr{B} := \{ B \in \alpha(\mathscr{C}_2): B与A独立, \forall A \in \mathscr{C}_1\}$$
则$\mathscr{C}_2 \subset \mathscr{B}$.  
下证$\mathscr{B}$是$\lambda_0$-类.  
首先, 显然$\Omega \in B$. 其次,设$B_1,B_2 \in \mathscr{B}, B_1 \subset B_2$, 则
$$ \forall A \in \mathscr{C}_1, P((B_2 - B_1)A) = P(B_2A) - P(B_1A) = P(B_2)P(A) - P(B_1)P(A) = P(B_2 - B_1)P(A)$$  
因此$B_2 - B_1 \in \mathscr{B}$. 所以$\mathscr{B} \supset \lambda_0(\mathscr{C}_2)$.  
由$\pi$ - $\lambda_0$ 定理, $\lambda_0(\mathscr{C}_2) = \alpha(\mathscr{C}_2)$. 所以$B =\alpha(\mathscr{C}_2)$.  
再令
$$\mathscr{A} := \{ A \in \alpha(\mathscr{C}_1): A与B独立, \forall B \in \alpha(\mathscr{C}_2)\}$$
用同样的方法可证$\mathscr{A} = \alpha(\mathscr{C}_1)$.  
这就证明了任取$A \in \alpha(\mathscr{C}_1), B \in \alpha(\mathscr{C}_2)$, $A$与$B$都是独立的.  

### 2.8.2

前面定义了两个事件、两个集类的独立. 自然地要问, 该如何定义三个事件、多个事件
独立, 以及多个集类的独立呢? 下面就是定义.  

> 设$I$为任意指标集, $\{A_i,i \in I\}$为一族事件. 若对任意有限的$J \subset I$及$A_i$, $i \in J$, 都有
> $$ P\left(\bigcap_{i \in J} A_i\right) = \prod_{i \in J} P(A_i) $$
> 则称$\{A_i,i \in I\}$独立.  

> 设$\{\mathscr{A_i},i \in I\}$为一族事件类. 若对任意有限的$J \subset I$及$A_i \in \mathscr{A}_i,i \in J$都有
> $$ P\left(\bigcap_{i \in J} A_i\right) = \prod_{i \in J} P(A_i) $$
> 则称$\{\mathscr{A}_i,i \in I\}$独立.  

类似于两个集类的情形, 我们可以证明:  
> 设$\forall i \in I$, $\mathscr{C}_i$是$\pi$-类.  
> 若$\{\mathscr{C}_i,i \in I\}$独立, 那么$\{\alpha(\mathscr{C}_i),i \in I\}$独立.  

可以看出, 多个事件独立的定义不仅仅要求事件是两两独立的, 而且要求从中任意选择任意有限个都满足交的概率等于概率的乘积这个性质.  
比如$A_1, \dots , A_n$独立就意味着  
$$ P(A_{i_1} \dots A_{i_k}) = \prod_{j=1}^{k} P(A_{i_j}), \forall 2 \leqslant k \leqslant n, i_1 < i_2 < \dots < i_k$$ 

因此, 在2.6节中举出的反例满足了三个事件两两独立
$$P(AB) = P(A)P(B), P(AC) = P(A)P(C), P(BC) = P(B)P(C)$$
但$AB$与$C$却不独立
$$P(ABC) \neq P(AB)P(C)$$

同样,也有例子说明,有满足
$$P(ABC) = P(A)P(B)P(C)$$
但不独立的三个事件——例如,考虑其中一个为空集的情形.  

## 2.9 可列概型

本节我们将考虑可列概型. 和有限概型相比, 不同之处就是样本空间中样本点的个数是可列个的, 我们主要关注它们的不同之处.  
例如,考虑n重Bernoulli概型$B(n,p)$. 以$\xi$表示成功的次数. 我们知道
$$P(\xi = k) = C_{n}^{k}p^{k}q^{n−k}$$

问题在于实际计算中, 只要n稍微大一点, 计算量就非常惊人. 因此人们就设法找一些近似计算方法. 就找到了一个后来证明是非常重要的分布,即Poisson分布.

> 若$\lim_{n \to \infty} np_n = \lambda$, 则
> $$\lim_{n \to \infty} C_{n}^{k}p_{n}^{k}q_{n}^{n−k} = \frac{\lambda^{k}}{k!}e^{−\lambda}, \forall k = 0, 1, 2, \dots$$
> 其中$q_n =1 − p_n$.  

证明. 因为$np_n \to \lambda$,所以$p_n \to 0$. 固定$k$,直接计算给出:  
$$
    \begin{align}
    lim_{n \to \infty} C_{n}^{k}p_{n}^{k}q_{n}^{n−k} 
    &= lim_{n \to \infty} \frac{n!}{k! (n-k)!} p_{n}^{k}q_{n}^{n-k} \notag \\
    &= lim_{n \to \infty} \frac{n^k}{k!} p_{n}^{k} \frac{(1 - p_{n})^{n}}{(1 - p_{n})^{k}} \notag \\
    &= lim_{n \to \infty} \frac{(np_{n})^{k}}{k!} (1 - p_{n})^{n} \notag \\
    &=  \frac{\lambda^{k}}{k!} lim_{n \to \infty} e^{n\ln{(1 - p_{n})}} \notag \\
    &=  \frac{\lambda^{k}}{k!}  e^{ lim_{n \to \infty} -np_n \frac{\ln{(1 - p_{n})}}{-p_n}} \notag \\
    &=  \frac{\lambda^{k}}{k!}  e^{-\lambda} \notag \\
    \end{align}
$$

这个近似计算使人们发现了一个非常重要的分布,即所谓Poisson分布.
事实上,稍微留心一下,我们就会注意到
$$ \sum_{k=0}^{\infty} \frac{\lambda^{k}}{k!}  e^{-\lambda} = 1 $$
所以一个自然的问题是,有没有一个概型,即有没有一个样本空间$\Omega$及其上的概率$P$,使得
$$P(\omega_k) = \frac{\lambda^{k}}{k!}  e^{-\lambda}$$

这样的样本空间是有的,且当然要包含可列个样本点.比如说我们可取
$$\Omega = \{0, 1, \dots\}$$
并赋予概率
$$P(k) = \frac{\lambda^{k}}{k!}  e^{-\lambda}$$
这就引导出可列概型的概念.

### 2.9.1 可列概型的概率

> 设一个试验可能的结果有可列个: 
> $$\Omega=\{\omega_1, \omega_2, \dots\}$$
> 设$\omega_i$出现的概率为 $p_i, 0 < p_i <1, \sum_{i=1}^{\infty} p_i = 1$. 令
> $$P(\omega_i) := p_i$$
> 且对任意$A \subset \Omega$,令
> $$P(A):= \sum_{\omega \in A} P(\omega)$$
> 则$(\Omega, P)$称为可列概型, $P(A)$称为事件$A$的概率.  

可列概型也有类似于有限概型的基本性质、有条件概率、全概率公式、独立性、随机变量、分布列、分布函数和期望之类的概念, 等等. 这些结果中主要的不同是原来的有限个样本点变成可列个样本点, 因而有限和会相应地变成级数. 但除此之外, 它们没有什么差别, 因此我们将有限概型和可列概型统称为**离散概型**.  

> 概率$P$具有如下性质:   
> (i)非负性：$\forall A, P(A) \geqslant 0$;  
> {ii}规范性：$P(\Omega) = 1, P(\emptyset) = 0$;  
> (iii)单调性：$A \subset B \Rightarrow P(A) \leqslant P(B)$;   
> (iv)可列可加性:若$A_1, A_2, \dots$是一列事件,且$A_iA_j=\emptyset,\forall i\neq j$, 则有加法公式
> $$ P(\sum_{i=1}^{\infty} A_i) = \sum_{i=1}^{\infty} P(A_i)$$
> (v)次可列可加性:若把上款中的两两不交条件去掉,则
> $$ P(\bigcup_{i=1}^{\infty} A_i) \leqslant \sum_{i=1}^{\infty} P(A_i)$$  

我们只证(v),其它都是显然的.  
证明. 令
$$\tau(\omega) := \inf\{i: \omega \in A_i\} (\inf \emptyset = \infty)$$
$$B_i := \{\tau = i\} = A_1^c \dots A_{n-1}^cA_i (A_0 := \emptyset)$$
则$B_1, B_2, \dots$两两不交, $\forall i, B_i \subset A_i$且
$$ \bigcup_{i=1}^{\infty} B_i = \bigcup_{i=1}^{\infty} A_i$$
因此
$$
\begin{align}
    P(\bigcup_{i=1}^{\infty} A_i) &= P(\bigcup_{i=1}^{\infty} B_i) \notag \\
    &= \sum_{i=1}^{\infty} P(B_i) \ (由(iv)) \notag \\
    &\leqslant \sum_{i=1}^{\infty} P(A_i) \ (由(iii)) \notag \\
\end{align}
$$

### 2.9.2 条件概率

条件概率的定义和有限概型时是完全一样的:
> 设$A$, $B$是两事件, $P(B)>0$.定义:
> $$P(A \mid B) := \frac{P(AB)}{P(B)}$$
> 称为在$B$发生的条件下$A$的条件概率.  

条件概率是将样本空间$\Omega$缩小为$B$后的概率,因此有与概率一样的性质,兹罗列如下:  

> 概率$P(· \mid B)$具有如下性质:  
> (i)非负性：$\forall A, 0 \leqslant P(A \mid B) \leqslant 1$;  
> {ii}规范性：$P(B \mid B) = 1, P(\emptyset \mid B) = 0$;   
> (iii)单调性：$A \subset C \Rightarrow P(A \mid B) \leqslant P(C \mid B)$;   
> (iv)可列可加性:若$A_1, A_2, \dots$是一列事件,且$A_iA_j=\emptyset,\forall i\neq j$, 则有加法公式
> $$ P(\sum_{i=1}^{\infty} A_i \mid B) = \sum_{i=1}^{\infty} P(A_i \mid B)$$
> (v)次可列可加性:若把上款中的两两不交条件去掉,则
> $$ P(\bigcup_{i=1}^{\infty} A_i \mid B) \leqslant \sum_{i=1}^{\infty} P(A_i \mid B)$$  

以及
> 设$\mathscr{P}=\{\Omega_1, \Omega_2, \dots\}$为$\Omega$的一个分割.  
> 全概率公式为
> $$P(A) = \sum_{i=1}^{\infty} P(A\Omega_i) = \sum_{i=1}^{\infty} P(\Omega_i)P(A \mid \Omega_i)$$  
> Bayes公式为
> $$ P(\Omega_j \mid A) = \frac{P(A\Omega_j)}{P(A)} = \frac{P(A \mid \Omega_j)P(\Omega_j)}{\sum_{i=1}^{\infty} P(\Omega_i)P(A \mid \Omega_i)}

### 2.9.3 分布列、分布函数

在可列概型上也可以定义随机变量.  
> $\Omega$上的实值函数称为随机变量.  

同样地,随机变量$\xi$的分布列定义为
$$(x_i, p_i, i=1,2,\dots)$$
其中$p_i = P(\xi=x_i) = \sum_{k: \xi(\omega_k)=x_i} P(\omega_k)$.  
在必要时即有可能产生混淆时, 将把$p_i$写为$p_{\xi, i}$以明确它是$\xi$的分布列. 

现在可以写出Poisson分布的定义了.
> 设$\lambda > 0$. 若$\xi$的分布为
> $$P(\xi = n) = \frac{\lambda^{n}}{n!} e^{-\lambda}, n = 0, 1, 2, \dots $$
> 则称$\xi$服从Poisson分布, 记为$\xi \sim P(\lambda)$.  

若$\xi$是随机变量, $B$是事件, $P(B)>0$. 定义给定$B$时$\xi$的条件分布列为
$$(x_i, p_i^B , i = 1,2, \dots)$$
其中$p_i^B := P(\xi = x_i \mid B)$.  

若$\xi,\eta$是两个随机变量, 定义给定$\eta = y_j$时$\xi$的分布列为
$$(x_i, p_i^j, i = 1,2, \dots)$$
其中$p_i^j := P(\xi = x_i \mid \eta = y_j)$.

定义$(\xi, \eta)$的联合分布列为
$$((x_i, y_j), p_{ij}, i, j = 1,2, \dots)$$
其中$p_{ij} = P(\xi = x_i, \eta = y_j)$.  

注意别把条件分布列和联合分布列搞混. 它们的关系是：
$$p_{ij} = p_{\xi,i}^jp_{η,j} = P(\xi = x_i \mid \eta = y_j)P(\eta = y_j)$$

描述概率的分布情况的另一个工具是分布函数,其定义为
$$ F(x) := \sum_{i: x_i \leqslant x} p_i = \sum_{\omega:\xi(\omega) \leqslant x} P(\omega)$$  
显然, F是定义在R上的右连续函数, 且它和分布列是相互唯一确定的.  

### 2.9.4 期望、方差

像有限概型一样, 随机变量$\xi$的期望定义为其平均值. 但这时涉及到无穷项级数的求和, 因此有一个收敛性问题.为此,我们将ξ的正部和负部分开考虑,即分别定义: 
$$ \mathbb{E}[\xi^+] = \sum_{\omega \in \Omega} \xi^+(\omega)P(\omega)$$
$$ \mathbb{E}[\xi^-] = \sum_{\omega \in \Omega} \xi^-(\omega)P(\omega)$$
若至少其中之一有限,则定义
$$\mathbb{E}[\xi] := \mathbb{E}[\xi^+] - \mathbb{E}[\xi^-]$$
当两个都有限时,称$\xi$可积. 显然$\xi$可积的充要条件是
$$\sum_{\omega \in \Omega} \lvert \xi(\omega)\rvert P(\omega) < \infty $$
此时
$$ \mathbb{E}[\xi] = \sum_{\omega \in \Omega} \xi(\omega)P(\omega)$$

当$\mathbb{E}[\xi^+]$与$\mathbb{E}[\xi^-]$均为无限时, 差式$\mathbb{E}[\xi^-]$没有意义, 此时称$\xi$没有期望.  
当可积时,期望有下列基本性质:
- (i)和概率的关联性:若$A \subset \Omega$,则$\mathbb{E}[I_A] = P(A)$;  
- (ii)单调性: $\xi \leqslant \eta \Rightarrow \mathbb{E}[\xi] \leqslant \mathbb{E}[\eta]$;
- (iii)线性性:设$a,b$为常数,则$\mathbb{E}[a\xi+b\eta] = a\mathbb{E}[\xi]+b\mathbb{E}[\eta]$;  
- (iv)若$\xi$的分布列为$\{(x_i,p_i), i=1,2,\dots\}$,则$\xi$可积的充要条件是$$\sum_{i=1}^{\infty} \lvert x_i \rvert p_i < \infty$$
且此时有$$\mathbb{E}[\xi] = \sum_{i=1}^{\infty} x_i p_i$$

证明. (i)$\mathbb{E}[I_A] = \sum_{\omega \in A} P(\omega) = P(A)$  
(ii) $\mathbb{E}[\xi] = \sum_{\omega} \xi(\omega) P(\omega) \leqslant \sum_{\omega} \eta(\omega) P(\omega) = \mathbb{E}[\eta]$  
(iii)$\mathbb{E}[a\xi+b\eta] = \sum_{\omega}(a\xi(\omega)+b\eta(\omega))P(\omega) = a\sum_{\omega}\xi(\omega)P(\omega)+b\sum_{\omega}\eta(\omega)P(\omega) = a\mathbb{E}[\xi]+b\mathbb{E}[\eta]$  
(iv)由于正项级数可任意交换求和顺序,故有
$$\sum_{\omega} \lvert \xi(\omega) \rvert P(\omega) = \sum_{i} \lvert x_i \rvert p_i$$
而当它们有限时,有
$$
\begin{align}
\mathbb{E}[\xi] &= \sum_{\omega} \xi(\omega) P(\omega) \notag \\
&= \sum_{i} \sum_{\omega:\xi(\omega)=x_i} \xi(\omega) P(\omega) \notag \\
&= \sum_{i}x_i \sum_{\omega:\xi(\omega)=x_i} P(\omega) \notag \\
&= \sum_{i}x_i p_i \notag \\
\end{align}
$$

要描述一个随机变量的总体状况,除了期望,就是波动了.  
> $D[\xi]$称为$\xi$的方差.  
> $$ D[\xi] := \mathbb{E}[(\xi - \mathbb{E}[\xi])^2] = \sum_{\omega} (\xi(\omega) - \mathbb{E}[\xi])^2 P(\omega)$$  
注意这里涉及的是正项级数,所以它要么收敛,要么发散到无穷大. 后面这种情况我们也依然认为方差存在, 等于无穷大.  

### 2.9.5 期望方差和关于分割的条件期望

设$B$为事件,$P(B)>0$. 将给定$B$时$\xi$的条件期望定义为
> $$\mathbb{E}[\xi \mid B] := \mathbb{E}[\xi^+ \mid B] − \mathbb{E}[\xi^− \mid B]$$
只要等式右边的两项中至少一项为有限数,其中  
$$ \mathbb{E}[\xi^+ \mid B] := \sum_{\omega} \xi^+(\omega) P(\omega \mid B)$$
$$ \mathbb{E}[\xi^- \mid B] := \sum_{\omega} \xi^-(\omega) P(\omega \mid B)$$  
当这两项均有限时,易见  
$$ \mathbb{E}[\xi \mid B] := \sum_{\omega} \xi(\omega) P(\omega \mid B)$$  
且右边的级数绝对收敛. 显然有
$$ \mathbb{E}[\xi \mid B] := \sum_{i=1}^{\infty} x_i P(\xi = x_i \mid B) = \sum_{i=1}^{\infty} x_i p_i^B$$  

至于$\mathbb{E}[\xi \mid B]$何时有限, 我们有下面的简单结果:  
> 若$\mathbb{E}[\xi]$有限, 则对任意$B \subset \Omega, P(B)>0$, $\mathbb{E}[\xi \mid B]$有限, 且
> $$\mathbb{E}[\xi \mid B] = \frac{E[\xi I_B]}{P(B)}$$  

证明. 因为$P(\omega \mid B) = P(B \mid \omega) \frac{P(\omega)}{P(B)} \leqslant \frac{P(\omega)}{P(B)}$,   
所以$\mathbb{E}[\lvert \xi \rvert] < \infty$时有
$$ \mathbb{E}[\lvert \xi \rvert \mid B] = \sum_{\omega \in \Omega}\lvert \xi(\omega) \rvert P(\omega \mid B) \leqslant \sum_{\omega \in \Omega}\lvert \xi(\omega) \rvert \frac{P(\omega)}{P(B)}= \frac{1}{P(B)}\mathbb{E}[\lvert \xi \rvert] < \infty$$ 
所以$\mathbb{E}[\xi \mid B]$有限, 且
$$
\begin{align} 
\mathbb{E}[\xi \mid B] &= \sum_{\omega \in \Omega}\xi(\omega)P(\omega \mid B) \notag \\
&= \sum_{\omega \in \Omega}\xi(\omega)P(B \mid \omega) \frac{P(\omega)}{P(B)} \notag \\
&= \frac{1}{P(B)}\sum_{\omega \in \Omega}\xi(\omega)I_B(\omega) P(\omega) \notag \\
&= \frac{E[\xi I_B]}{P(B)} \notag \\
\end{align}
$$

现在设$\mathscr{P} = \{ \Omega_1, \Omega_2, \dots \}$构成$\Omega$的一个分割, 即
$$ \sum_{i=1}^{\infty} \Omega_i = \Omega$$
如同有限概型的情况一样,引进下面的概念是方便的：
> 定义
> $$P(A \mid \mathscr{P})(\omega) := \sum_{i=1}^{\infty}P(A \mid \Omega_i)I_{\Omega_i}(\omega) $$
> $P(A \mid \mathscr{P})$称为给定分割P时的条件概率.  

它的含义是, 当$\omega \in \Omega_i$时, $P(A \mid \mathscr{P})(\omega) = P(A \mid \Omega_i)$, 因此它是一种简单实用的记号,用单独一个记号表示了所有的条件概率$P(A \mid \Omega_i), i=1,2,\dots$. 同时我们知道, $P(\omega \in \Omega_i \mid \mathscr{P}) = P(\Omega_i \mid \mathscr{P})$. 

当$A={\omega^\prime}$时, 我们将$P(A \mid \mathscr{P})(\omega)记为P(\omega^{\prime}, \omega)$. 这样, 当$\omega \in \Omega_i$时, 就有
$$P(\omega^{\prime}, \omega) = P(\omega^{\prime} \mid \Omega_i)$$
显然有
$$P(A \mid \mathscr{P})(\omega) = \sum_{\omega^{\prime}\in A} P(\omega^{\prime}, \omega)$$
就像有限概型的情况一样, 对固定的$A$, $\omega \mapsto P(A \mid \mathscr{P})(\omega)$是随机变量, 而对于固定的$\omega$, $A \mapsto P(A \mid \mathscr{P})(\omega)$是概率, 它满足非负性、规范性与可列可加性.  

对任何一个随机变量$\xi$,对固定的$\omega$,定义
> $$\mathbb{E}[\xi \mid \mathscr{P}](\omega) := \mathbb{E}^{P(·,\omega)}[\xi(\omega^{\prime})] := \sum_{\omega^{\prime}} \xi(\omega^{\prime}) P(\omega^{\prime}, \omega) = \sum_{i=1}^{\infty}\mathbb{E}[\xi \mid \Omega_i]I_{\Omega_i}(\omega)


关于分割的条件期望依然有一个是否有限的问题.我们有:
> 若$\mathbb{E}[\lvert\xi\rvert] < \infty$, 则对任意分割$\mathscr{P}$, $\mathbb{E}[\xi\mid\mathscr{P}]$对每一个$\omega$都有限.  

事实上, 当命题的条件满足时, 对$\forall i$, $\mathbb{E}[\xi\mid\Omega_i]$有限, 因此$\mathbb{E}[\xi\mid\mathscr{P}]$有限.  

> 当$\mathbb{E}[\xi]$有限时有
> $$\mathbb{E}[\mathbb{E}[\xi\mid\mathscr{P}]] = \mathbb{E}[\xi]$$
> 特别地, 当$\xi := I_A$时, 我们得到全概率公式另一种简洁表达式:
> $$P(A) = \mathbb{E}[\mathbb{E}[I_A\mid\mathscr{P}]] = \mathbb{E}[P (A\mid\mathscr{P})]$$

证明. 
$$ \begin{align} 
\mathbb{E}[\mathbb{E}[\xi\mid\mathscr{P}]] &= \sum_{i=1}^{\infty}\mathbb{E}[\xi\mid\Omega_i]P(\Omega_i) \notag \\
&= \sum_{i=1}^{\infty}\mathbb{E}[\xi I_{\Omega_i}]\notag \\
&= \sum_{i=1}^{\infty}\sum_{\omega\in \Omega_i}\xi(\omega)P(\omega)\notag \\
&= \sum_{\omega\in \Omega}\xi(\omega)P(\omega)\notag \\
&= \mathbb{E}[\xi]\notag \\
\end{align}
$$

整体平均等于局部平均后再加权平均, 这就是上面这个公式背后的简单思想.

### 2.9.6 独立性
最后我们要谈的是独立性. 这个概念是有限概型时同一概念的自然延申.  
> (i) 设$A, B$是事件. 若$P(AB) = P(A)P(B)$, 则称$A$与$B$独立.  
> 设$\{A_i, i \in I\}$是事件族, 其中$I$是任意指标集. 若对任意有限$J \subset I$, 都有
> $$ P\left( \bigcap_{i\in J} A_i\right) = \prod_{i \in J}P(A_i)$$
> 则称$\{ A_i, i \in I\}$独立. 

> (ii) 设$\xi, \eta$是随机变量. 如果
> $$P(\xi = x_i, \eta = y_j ) = P(\xi = x_i) P(\eta = y_j), \forall i, j$$
> 则称$\xi$与$\eta$独立;  
> 设$\{\xi_i, i \in I\}$是随机变量族, 其中$I$是任意指标集. 若对任意有限$J \subset I$都有
> $$P\left(\bigcap_{i \in J} \{\xi_i = x_i\}\right) = \prod_{i \in J}P(\xi_i = x_i)$$
> 其中$x_i$跑遍$\xi_i$的值域, 则称$\{\xi_i, i \in I\}$独立.  

独立性是概率论中最重要的概念之一. 我们有下列重要结果:  
> 设$\xi, \eta$独立, 且$\mathbb{E}[\xi], \mathbb{E}[\eta]$存在, 则$\mathbb{E}[\xi\eta]$也存在且
> $$\mathbb{E}[\xi\eta] = \mathbb{E}[\xi]\mathbb{E}[\eta]$$  

证明. 设$\xi$的分布列为$\{(x_i, p_i)\}$, $\eta$的分布列为$\{(y_j , q_j )\}$. 若$\sum_{\omega} \xi(\omega)\eta(\omega)P(\omega) < \infty$, 则
$$
\begin{align}
\mathbb{E}[\xi\eta] &= \sum_{\omega}\xi(\omega)\eta(\omega)P(\omega) \notag\\
&= \sum_{i,j}\sum_{\omega: \xi(\omega)=x_i, \eta(\omega)=y_j}\xi(\omega)\eta(\omega)P(\omega) \notag\\
\end{align}
$$



