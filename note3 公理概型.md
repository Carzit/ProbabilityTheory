# 3 公理概型
[TOC]

## 3.1 动因

离散概型是不是已经够用了呢? 答案依然是否定的. 我们看两个简单的例子.  

### 3.1.1 可列重Bernoulli试验
**例1**(可列重Bernoulli试验). 反复投一枚硬币, 各次投掷相互独立, 每次得到正面的概率是$p$. 以$\tau$ 记第一次得到正面时投掷的次数. 求$P(\tau = n), n = 1, 2, \dots$.  
我们已经知道$\tau$服从几何分布, 即$P(\tau = n) = q^{n-1}p (q := 1 − p)$. 然而, 概率空间是什么呢?  

我们首先来看如何选取样本空间. 当$n$固定时, 样本空间似可取为
$$\Omega_n := \{(i_1, · · · , i_n) : i_k = 0, 1, k = 1, \dots, n\}.$$
但是, 这个样本空间描述的只是至多到第$n$次一定得到正面的试验, 且显然有
$$\sum_{k=1}^{n}P(\tau=k) = 1 - q^n \neq 1$$  
因此$\Omega_n$无法完整地描述该试验, 所以任何试图以$\Omega_n$为样本空间来建立概率空间的努力都注定是徒劳的.  

那么, 能建立一个能完整描述该试验的样本空间——概率空间吗?  
这个问题的关键是我们预先不知道到底投多少次才能得到正面, 因此有限重Bernoulli试
验的概型已经不能满足要求, 因为样本空间必须代之以
$$\Omega := \{(i_1, i_2, \dots) : i_k = 0, 1, \forall k\}.$$  

这个概型和可列概型的本质区别在于已不可能通过赋予每个$\omega$一个$P(\omega)$来定义概率. 因为若设单次投掷中正面出现的概率为$p, q := 1 − p$, 那么由独立性, 每个$\omega$出现的概率都为
$$P(\omega) = p^{\sum_{k=1}^{\infty}i_k}q^{\sum_{k=1}^{\infty}(1-i_k)} = 0$$

### 3.1.2 不可数集
**例2** 在[0, 1]上任取一点, 求这点落在某集合A中的概率.  
考虑这个问题时, 我们碰到的第一个难题是, 跟上一个例子一样, 我们依然不能通过对每
个$\omega$指定一个$P(\omega)$来确定$P$ , 因为每个$\omega$都是等可能出现的, 所以对任意$\omega$, $P(\omega)$必须是0, 但这个对确定落在$A$中的概率$P(A)$没有任何帮助.  
那好, 我们避开这个问题, 直接对$A$定义$P(A)$. 直观告诉我们, $P(A)$应该等于$A$的长度.但对区间我们可以谈长度, 对有限个区间的并集可以谈长度, 甚至对一般的Borel集也可以谈长度的推广——Lebesgue测度, 但终究不可测量长度的集合是存在的, 我们不可能对这些集合谈长度亦即Lebesgue测度. 这就给我们一个启示: 不是对$\Omega$的任何子集都可以谈概率. 这是与可列概型最大的不同, 在那里我们对Ω的所有子集A都定义了概率$P (A)$.  

### 3.1.3 勒贝格测度
此时, 既然不能对所有$\Omega$的子集定义概率, 那应该对哪部分子集定义概率呢? 一方面, 我们应该对感兴趣的子集(想要研究的事件)定义概率, 另一方面, 为了计算的便利, 我们也不可避免地会对这些兴趣中的子集进行运算, 因此也需要确保对运算后的子集也是有概率可言的.  

基于这样的考虑, 我们面临的任务往往是, 从Ω的某个包含感兴趣子集的集类出发, 构造一个包含该集类且关于某些运算封闭的更大的集类, 然后在这个大集类上定义概率.  
完成这个任务的可能性来自于Lebesgue测度论的启示: Lebesgue测度正是把长度的概念
从一些特殊的集合即区间的长度推广到一般Borel可测集的测度. 因此从某种意义上说, 概率的公理化是建立在Lebesgue的测度论的思想之上的.  
因此现在我们需要做的, 是研究由一个相对简单的集类出发, 如何获得包含该集类的关
于某些运算封闭的更大的集类. 这里可以分两步走: 
- 第一步先研究对有限次运算封闭的集类, 这就产生了$\pi$-类, $\lambda_0$-类和代数的概念. 这一步在上一章已完成了.
- 第二步, 是研究对无穷次运算封闭的集类. 这里的无穷是任意无穷吗? 不是！ 这里的无穷只能是可列无穷, 因为若指标集$I$是不可列的, 那么$\sum_{i \in I}P(A_i)$是无法定义的, 一如每个点的长度都是$0$, 而你无法把$[0, 1)$中所有点的长度加起来而得到整个区间的长度.

所以, 我们只需考虑对可列次运算封闭的集类.  

## 3.2 $\sigma$-代数, 单调类与$\lambda$-类
### 3.2.1 $\sigma$-代数
> 一个代数$\mathscr{F}$ , 若满足
> $$A_i \in \mathscr{F}, i=1,2,\dots\Rightarrow\bigcup_{i=1}^\infty A_i\in \mathscr{F}$$
> 则称其为$\sigma$-代数.

结合De Morgan法则直接推出$\sigma$-代数对可列交也是封闭的。



也就是说，检验一个集类是否为$\sigma$-代数，只需要检验:

- 包含$\Omega$
- 对余封闭
- 对可列并封闭



我们看一类$\sigma$-代数的证明.

设$E$是个有无穷多元素的空间$N(E) = \infty$
$$
\mathscr{A} = \{A \in E: \min\{N(A),N(A^c)\}<\infty \}
$$
证明. 首先$\emptyset = E^c, N(\emptyset)=0$，因此$\emptyset, E \in \mathscr{A}$.

其次，$A,A^c$中至少有一个有限，则全在集类中。易证其对余封闭。

最后证明其对可列并封闭：设有一列$\{A_i\in\mathscr{A}\}$, 

不妨设$\exist i_0$使$N(A_{i_0}^c)<\infty$，则
$$
\bigcap_iA_i^c=(\bigcup_iA_i)^c\subset A_{i_0}^c
$$

$$
N(\bigcap_iA_i^c)<\infty, A_i^c\in\mathscr{A,\forall i}
$$



否则若不存在即$\forall i, N(A_i)<\infty$,则
$$
N(\bigcup_iA_i)<\infty
$$
证完.



### 3.2.2 单调类
代数云云, 当然对有限并封闭. 由于
$$\bigcup_{i=1}^\infty A_i = \bigcup_{n=1}^\infty \left(\bigcup_{i=1}^nA_i\right)$$

而$\bigcup_{i=1}^nA_i$关于$n$是单调上升的, 故在上面的定义中, 对可列并封闭可换为对单调上升的可列并封闭. 这就引出了所谓单调类的概念:
> 一个集类$\mathscr{M}$, 若对单调极限封闭, 即若
> $$A_i ∈ \mathscr{M}, i = 1, 2, \dots , \{A_i\}单调 \Rightarrow \lim_{n\to\infty} A_i \in \mathscr{M}$$  
> 则称$\mathscr{M}$为单调类.

所谓单调, 无非是单调上升与单调下降两种情况. 因此上述定义又可复述为:
> $$A_i ∈ \mathscr{M}, i = 1, 2, \dots , A_i\uparrow \Rightarrow \bigcup_{i=1}^\infty A_i \in \mathscr{M}$$
> 且
> $$A_i ∈ \mathscr{M}, i = 1, 2, \dots , A_i\downarrow \Rightarrow \bigcap_{i=1}^\infty A_i \in \mathscr{M}$$

### 3.2.3  $\lambda$-类
前面所说的引入单调类的理由可写成下面简单的结果：
> 一个代数为$\sigma$-代数的充要条件是它是单调类.

证明. 必要性显然, 往证充分性.  
设代数$\mathscr{F}$是单调类, $A_i \in \mathscr{F}$.   
令$B_n = \bigcup_{i=1}^nA_i$.  
则$B_n \in \mathscr{F}$ 且$\{B_n\}\uparrow$.   
于是
$$\bigcup_{i=1}^\infty A_i= \lim_{n\to\infty}B_n\in\mathscr{F}$$

因此代数性质和单调类性质是σ-代数的两要素, 即我们有  
$\sigma$-代数 = 代数 + 单调类  
可以想象的是, 在此关系式中如果把代数的要求降低为π-类, 那么单调类的要求势必要
加强. 由于  
$\pi$-类 + $\lambda_0$-类 = 代数  
所以只要把λ0-类这个要求和单调类结合在一起, 上述关系式就应该还是成立的. 这就引导出了λ-类的概念.

> 非空集类$\mathscr{L}$如果满足以下条件则称为$\lambda$-类：
> - $\Omega \in \mathscr{L}$
> - $E, F \in \mathscr{L} , E \subset F \Rightarrow E \setminus F ∈ \mathscr{L}$  
> - $E_n \in \mathscr{L} , E_n \uparrow \Rightarrow \lim_{n\to\infty} E_n \in L$

λ-类一定也是单调类.

### 3.2.4 单调类定理
> - (i) 对任意集类$\mathscr{C}$ , 都存在唯一的$\sigma$-代数$\mathscr{F}$ , 使得对任意$\sigma$-代数$\mathscr{F}^\prime \subset \mathscr{C}$ , 均有$\mathscr{C} \subset \mathscr{F} \subset \mathscr{F}^\prime$.  
> - (ii) 对任意集类$\mathscr{C}$ , 都存在唯一的单调类$\mathscr{M}$ , 使得对任意单调类$\mathscr{M}^\prime \subset \mathscr{C}$, 均有$\mathscr{C} \subset \mathscr{M} \subset \mathscr{M}^\prime$.   
> - (iii) 对任意集类$\mathscr{C}$ , 都存在唯一的$\lambda$-类$\mathscr{L}$ , 使得对任意$\lambda$-类$\mathscr{L}^\prime \subset \mathscr{C}$ , 均有$\mathscr{C} \subset \mathscr{L} \subset \mathscr{L}^\prime$.  

上面的$\mathscr{F}$, $\mathscr{M}$与$\mathscr{L}$分别称为$\mathscr{C}$生成的$\sigma$-代数、单调类与$\lambda$-类, 记为$\sigma(\mathscr{C})$, $\mathscr{M}(\mathscr{C})$与$\lambda(\mathscr{C})$.

由于σ-代数一定是λ-类, 而λ-类一定是单调类, 所以下面的命题是显然的.
> 对任何集类$\mathscr{C}$有
> $$\mathscr{M}(\mathscr{C}) \subset \lambda(\mathscr{C}) \subset \sigma(\mathscr{C})$$

所以一般都是由π- 类或代数出发生成σ-代数. 这时我们有两个非常有用的结果——它们都称为单调类定理.

> **(单调类定理1)**. 代数生成的单调类即为它生成的$\sigma$-代数.
> $$\mathscr{M}(\mathscr{A}) = \sigma(\mathscr{A})$$

> **(单调类定理2, Dynkin定理)**. $\pi$-类生成的$\lambda$-类即为它生成的$\sigma$-代数.
> $$\lambda(\mathscr{P}) = \sigma(\mathscr{P})$$



### 3.2.5 博雷尔代数

考虑$\mathbb{R}$上的集类
$$\mathscr{S}_1 := \{(−\infty, b) : −\infty < b < \infty\}$$
$$\mathscr{S}_2 := \{[a, b) : −\infty < a \leqslant b < \infty\}$$
$$\mathscr{O} := \{O : O是开集\}$$
$$\mathscr{C} := \{C : C是闭集\}$$

> $$\sigma(\mathscr{S}_1) = \sigma(\mathscr{S}_2) = \sigma(\mathscr{O}) = \sigma(\mathscr{C})$$
> 这个集类称为$\mathbb{R}$上的Borel $\sigma$-代数, 记为$\mathscr{B}$, 而这个集类中的元素称为Borel集. 

## 3.3 概率的公理化

### 3.3.1 定义

> 设$\Omega$为一抽象空间, $\mathscr{F}$为$\Omega$的部分子集构成的$\sigma$-代数. 如果存在定义在$\mathscr{F}$上而取值于[0, 1]的函数$P$, 满足  
> - (i) 规范性: $P(\Omega) = 1$
> - (ii) 可列可加性: 对$A_i \in \mathscr{F}, i = 1, 2, \dots$ , 且$A_iA_j = \emptyset, i \neq j$, 有
> $$P\left(\sum_{i=1}^\infty A_i\right) = \sum_{i=1}^\infty P\left(A_i\right)$$
> 则称$\Omega$为样本空间, $\mathscr{F}$为事件域, $P$为概率, $P(A)$为事件$A \in \mathscr{F}$ 的概率, 三元组$(\Omega, \mathscr{F}, P )$为概率空间.  

若$A \in \mathscr{F}$且$P(A) = 0$, 则称$A$为可略集, 简称$A$可略.  
若$A \in \mathscr{F}$且$P(A) = 1$, 则称$A$几乎必然发生, 记为$A~a.s.$.

对于$A, B \in \mathscr{F}$，概率$P$有以下运算性质：  
> - (i) $P (\emptyset) = 0$  
>
> - (ii) 对$A_i \in \mathscr{F} , i = 1, 2, \dots , n$, 且$A_iA_j = \emptyset, i \neq j$, 有
>   $$
>   P\left(\sum_{i=1}^n A_i\right) = \sum_{i=1}^n P\left(A_i\right)
>   $$
>
> - (iii) $P(A^c) = 1 − P (A)$ 
>
> - (iv) $P(A \setminus B) = P (A) − P (AB)$  特别地, 若$A \subset B$, 则$P(B − A) = P (B) − P (A)$且$P (B) \geqslant P (A)$ 
>
> - (v) $P(A \cup B) = P (A) + P (B) − P (AB)$

此命题之(ii)说明, 从P 的可列可加性可以推出有限可加性. 那么, 有限可加性比可列可
加性究竟差了多少呢? 回答是: 差一个单调连续性. 我们先说明什么是单调连续性.

> 设$A_n, A \in \mathscr{F}$.  
>  若$A_n \uparrow A \Rightarrow P(A_n) \uparrow P(A)$则称$P$在$A$处下连续;   
>  若$A_n \downarrow A \Rightarrow P(A_n) \downarrow P(A)$则称$P$在$A$处上连续.  
>  若$P$在任意$A \in \mathscr{F}$处上(下)连续, 则称$P$上(下)连续.

> 设$P$是$\mathscr{F}$上的取值于$[0, 1]$的函数, 满足规范性和有限可加性.  
> 则$P$的可列可加性和下列条件中的任意一个等价:
>
> - (i) 下连续性;
> - (ii) 在$\Omega$处的下连续性;
> - (iii) 在$\emptyset$处的上连续性;
> - (iv) 上连续性.



### 3.3.2 命题

要证明两个概率测度 $P_1 $和 $ P_2 $ 在由一个 $\pi$-类 $\mathcal{P}$ 生成的 $\sigma$-代数 $\sigma(\mathcal{P})$上相等.

定义集合类$\mathcal{L} = \{ A \in \sigma(\mathcal{P}) : P_1(A) = P_2(A) \}$, 我们的目标是证明 $\mathcal{L} = \sigma(\mathcal{P})$。

为了应用 $\pi-\lambda$ 定理，我们需要验证 $\mathcal{L}$ 是$\lambda$-类的三个条件：
1. $\Omega \in \mathcal{L}$:
   因为 $P_1$ 和 $P_2$ 都是概率测度，所以$P_1(\Omega = P_2(\Omega) = 1$。因此，$\Omega \in \mathcal{L}$。

2. **闭合于补集:**
   如果 $A \in \mathcal{L}$，即 $P_1(A) = P_2(A)$，那么
   $$
   P_1(A^c) = 1 - P_1(A), \quad P_2(A^c) = 1 - P_2(A).
   $$
   因为 $P_1(A) = P_2(A)$，所以 $P_1(A^c) = P_2(A^c)$。

   因此，$A^c \in \mathcal{L}$。
   
3. **闭合于不交并:**
   如果 $\{A_n\}_{n=1}^\infty \subset \mathcal{L}$ 是一列不交集合$A_i \cap A_j = \emptyset$，且 $A_n \in \mathcal{L}$，则由概率测度的可列可加性
   $$
   P_1\left(\bigcup_{n=1}^\infty A_n\right) = \sum_{n=1}^\infty P_1(A_n), \quad P_2\left(\bigcup_{n=1}^\infty A_n\right) = \sum_{n=1}^\infty P_2(A_n).
   $$
   
   因为 $P_1(A_n) = P_2(A_n)$ 对所有 $n$ 成立，所以
   $$
   P_1\left(\bigcup_{n=1}^\infty A_n\right) = P_2\left(\bigcup_{n=1}^\infty A_n\right)因此，$\bigcup_{n=1}^\infty A_n \in \mathcal{L}$
   $$



根据假设，$\mathcal{P} \subseteq \mathcal{L}$.

由于 $\mathcal{P}$ 是一个 $\pi$-类，且 $\mathcal{L}$ 是一个包含 $\mathcal{P}$ 的$\lambda$-类，根据 $\pi-\lambda$ 定理，我们有
$$
\sigma(\mathcal{P}) \subseteq \mathcal{L}
$$
同时，显然 $\mathcal{L} \subseteq \sigma(\mathcal{P})$. 因此，
$$
\mathcal{L} \subseteq \sigma(\mathcal{P})
$$


## 3.4 条件概率、独立性与条件独立性

### 3.4.1 条件概率

设$(\Omega, \mathscr{F}, P)$为概率空间, $A, B \in \mathscr{F}, P(A) > 0$. 依据前面的经验, 定义$A$发生的条件下$B$发生的条件概率为
$$
P(B \mid A) = \frac{P(AB)}{P(A)}
$$
现设$P(A)P(B)>0$. 由于
$$
P(A \mid B)P(B) = P(B \mid A)P(A) = P(AB)
$$
所以
$$
P(B\mid A) = \frac{P(A \mid B)P(B)}{P(A)}
$$
这个公式称为**Bayes公式**. 它是离散概型时的Bayes公式的自然延伸.

设$\mathscr{P} ；= \{\Omega_1,\Omega_2,\dots,\Omega_n, \dots\}$构成$\Omega$的一个分割, 即
$$
\Omega = \sum_{i=1}^{\infty}\Omega_i, \Omega_i \in \mathscr{F}, P(\Omega_i)>0, \forall i
$$
则全概率公式依然成立. 即对于$\forall A \in \mathscr{F}$有
$$
P(A) = \sum_{i=1}^{\infty}P(A\mid \Omega_i)P(\Omega_i)
$$
以$\sigma(\mathscr{P})$记$\mathscr{P}$生成的σ-代数. 定义
$$
h(A, \omega) := \sum_{i=1}^{\infty}P(A \mid \Omega_i)I_{\Omega_i}(\omega)
$$
$h$称为给定$\sigma(\mathscr{P})$时$A$的条件概率. 

注意, $h$是二元函数：当固定$\omega$时, 它作为定义在$\mathscr{F}$上的函数, 是一个概率, 且对$\omega \in \Omega_n$就是给定$\Omega_n$时的条件概率；当固定$A$时, 作为$\omega$的函数是一个在每个$\Omega_i$上取常值$P(A \mid \Omega_i)$的函数. 当然, $h$还依赖于分割方式$\mathscr{P}$. 为完整地表示出这种依赖关系, 我们将用$P(A \mid \mathscr{P})(\omega)$表示这个函数.



### 3.4.2 独立性

独立性的概念和离散时也是一样的.

我们先定义事件的独立

> 设$A, B$是事件. 若
> $$
> P(AB) = P(A)P(B)
> $$
> 则称$A, B$独立.

> 设$A_1, A_2, \dots, A_n$是事件. 若对任意$2 \leqslant k \leqslant n$及任意$\{i_1,\dots,i_k\} \subset \{1,\dots ,n\}$, 有
> $$
> P(\prod_{j=1}^k A_{i_j}) = \prod_{j=1}^kP(A_{i_j})
> $$
> 则称$A_1, A_2, \dots, A_n$独立. 

> 设$A_1, A_2, \dots$是事件. 
>
> 若$\forall n \geqslant 2$, $A_1, A_2, \dots, A_n$独立
>
> 则称$A_1, A_2, \dots$独立. 

我们再定义（事件）集类的独立, 简单来说就是集类间所有事件均独立.

> 设$\mathscr{A}, \mathscr{B}$是集类, 若对于$\forall A \in \mathscr{A},B \in \mathscr{B}$有
> $$
> P(AB) = P(A)P(B)
> $$
> 则称$\mathscr{A}, \mathscr{B}$独立.

> 设$\mathscr{A}_1,\mathscr{A}_2,\dots$是集类, 若对于$\forall n \geqslant 2$, $\forall A_i \in \mathscr{A}_i \cap \Omega, 1\leqslant i\leqslant n $
> $$
> P(\prod_{i=1}^n A_{i}) = \prod_{i=1}^nP(A_{i})
> $$
> 则称$\mathscr{A}_1,\mathscr{A}_2,\dots$独立. 



下面的结论非常有用:

> 若$\mathscr{C}_i, \mathscr{C}_2$是$\pi$-类且相互独立, 则$\sigma(\mathscr{C}_1), \sigma(\mathscr{C}_2)$相互独立.



### 3.4.3 条件独立性 

如果在独立性的定义中以条件概率代替原概率, 则得到条件独立性的概念.

> 设$A, B, C$是事件, $P(A)>0$. 若
> $$
> P(BC\mid A) = P(B\mid A)P(C\mid A)
> $$
> 则称$B,C$在给定$A$时条件独立.

利用条件概率的定义, $B, C$在给定$A$时上述条件独立的等式即为
$$
P(ABC)P(A) = P(AB)P(AC)
$$
而$B, C$独立则为
$$
P(BC) = P(B)P(C)
$$
因此由独立不能得到条件独立, 反正亦然. 关于这一事实的解释是：条件独立性是限制在某种条件下的独立性, 和整体独立性没有直接的关系.
