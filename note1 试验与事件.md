
# 1 试验及事件的运算

## 1.1 试验、基本事件与事件
对一个试验, 任何一个结果都称为一个基本事件(即不能进一步分解的事件). 将其所有可能的结果即基本事件放在一起, 就构成一个集合, 这个集合我们一般将用$\Omega$表示之. 传统上, 一个基本事件称为一个样本点$\omega$, 而$\Omega$则称为样本空间.

比如掷一枚骰子的试验, 其样本空间便是
$\omega = \{ 1, 2, 3, 4, 5, 6 \}$.
而如果将一枚骰子掷n次, 样本空间则是
$\omega = \{ (k_1, ..., k_n)\mid k_i \in \{ 1, 2, 3, 4, 5, 6 \}, i=1,...,n \}$.

将满足某些特定条件的基本事件放在一起, 就构成一个事件. 因此事件用集合论的语言来说
就是$\omega$的子集，常用大写字母如$A$, $B$, · · ·

概率论的研究对象是可以重复的试验, 因此很容易想象将一个简单的试验重复多次, 循环往复, 以致无穷, 虽然实际上做不到无穷次, 但有必要考虑试验次数趋于无穷时发生的各种现象, 这样样本空间就有无穷多个元素.
例如将一枚硬币抛无穷次, 样本空间为
$\Omega = \{0, 1\}^\infty := \{(a_1, ..., a_n, ...) \mid a_k= 0, 1, k=1,...,n,...\}$

## 1.2 事件的关系与运算
### 1.2.1
设$\Omega$为样本空间, $A, B, C, ...$ 均为$\Omega$的子集, 即事件；以$\emptyset$表示空集, 即不含任何元素的子集. 我们引进如下运算与术语.
- $\Omega$称为必然事件, $\emptyset$称为不可能事件.
- $A$与$B$的并是指这样一个事件: $A$与$B$中至少一个发生. 这个事件记为 $A \cup B $, 即$$A \cup B := \{ \omega \in \Omega : \omega \in A 或 \omega \in B \}$$
- $A$与$B$的交是指这样一个事件: $A$与$B$都要发生. 这个事件记为$A \cap B$, 即$$ A \cap B := \{ \omega \in \Omega \mid \omega \in A 且 \omega \in B\}$$,$A \cap B$也常写为$AB$; $AB = \emptyset$时, 称$A$与$B$互不相容或不相容. 此时, $A \cup B$常记为$A + B$. 或者反过来说, 写出$A + B$时, 就自动意味着$AB = \emptyset$.
- $A$与$B$的差是指这样一个事件: $A$发生而$B$不发生. 这个事件记为$A \setminus B$, 即$$A \setminus B := \{ \omega \in A 且 \omega \notin B\}.$$ $A \subset B$时, $B \setminus A$常记为$B - A$. 或者反过来说, 写出$B - A$时, 就自动意味着$A \subset B$.
- $A$与$B$的对称差定义为:$A \triangle B := (A \setminus B) \cup (B \setminus A)$ .
- $A$的余集, 或称逆事件, 定义为: $A^c := \Omega \setminus A$.显然
$\emptyset^c = \Omega$, $\Omega^c = \emptyset$.一般地有$(A^c)^c = A$.
- 两个事件$A$, $B$, 若$$\omega \in A \Rightarrow \omega \in B$$,
则称$A$包含于$B$, 或$B$包含了$A$, 记为$A \subset B$或$B \supset A$. 若$A \subset B$且$B \supset A$, 则称$A$等于$B$,记为$A = B$.
- 并与交均可对多个集合定义. 设$\{A_i, i \in I\}$是一族集合, 定义:$$\bigcup_{i \in I} A_i := \{ \omega \mid \exists i \in I, \; \text{使得} \; \omega \in A_i \}.$$
$$\bigcap_{i \in I} A_i := \{ \omega \mid \forall i \in I, \; 都有\omega \in A_i \}.$$
- 设$A_1, A_2, ...$为一列事件, 定义它们的上极限为$$\limsup_{n \to \infty} A_n := \bigcap_{n=1}^{\infty} \bigcup_{k=n}^{\infty} A_k.$$因此, $\omega \in \limsup_{n \to \infty} A_n$就意味着对任意$n$, 都有$k > n$使得$\omega \in A_k$. 这显然等价于有无限多个$n$使得$ω \in A_n$. 因此, $\omega \in \limsup_{n \to \infty} A_n$就表示$\{A_n\}$中有无限多个发生这一事件$\omega$;  
定义它们的下极限为$$\liminf_{n \to \infty} A_n := \bigcup_{n=1}^{\infty} \bigcap_{k=n}^{\infty} A_k.$$因此,$\omega \in \liminf_{n \to \infty} A_n$就意味着存在一个$n$, 使得对任意$k > n$都有$\omega \in A_k$. 这显然等价于最多只有有限多个$n$使得$\omega \notin A_n$. 因此, $\omega \in \liminf{n \to \infty} A_n$就表示$\{A_n\}$中至多有限个$A_n$不发生这一事件$\omega$.  
因此有$$\liminf_{n \to \infty} A_n \subset \limsup_{n \to \infty} A_n$$  
如果$\liminf_{n \to \infty} A_n = \limsup_{n \to \infty} A_n$, 则称$\{A_n\}$的极限存在, 并记为$\lim A_n$  
特别地,若$\{A_n\}$单调，则$\lim A_n$ 存在。  
若$\{A_n\}$单调上升，即$A_1 \subset A_2 \subset ...$时，有$$\lim A_n = \bigcup_{n=1}^{\infty}A_n;$$  
若$\{A_n\}$单调下降，即$A_1 \supset A_2 \supset ...$时，有$$\lim A_n = \bigcap_{n=1}^{\infty}A_n;$$

### 1.2.2  

事件的运算有下面的性质:  

- 交换律: $$A \cup B = B \cup A$$ $$AB = BA;$$

- 结合律: $$A \cup B \cup C = A \cup (B \cup C) = (A \cup B) \cup C;$$
$$ABC = A(BC) = (AB)C$$

- 分配律: $$(AB) \cup (AC) = A(B \cup C)$$
$$(A \cup B) \cap (A \cup C) = A \cup (BC)$$
$$\bigcup_{i \in I} (A \cap B_i) = A \cap (\bigcup_{i \in I} B_i)$$
$$\bigcap_{i \in I} (A \cup B_i) = A \cup (\bigcap_{i \in I} B_i)$$

集合的差和对称差有:
$$A \setminus B = A - AB$$
$$A \triangle B = A \cup B - AB$$

集合的加减运算有：
$$ A(B+C) = AB + BC$$
$$ A(B-C) = AB - BC$$

### 1.2.3
一个集合可以用一个函数来刻画，这就是所谓的示性函数:
设$A \subset \Omega$. 函数
$$
I(A)(\omega) := I_A(\omega) = 
\begin{cases} 
1 & \omega \in A, \\ 
0 & \omega \notin A 
\end{cases}
$$
称为$A$的示性函数.  
显然, 两个集合相等当且仅当其示性函数相等. 此外, 我们有下面的简单性质:  

- $$ I_A = 1 - I_{A^c} $$
- $$ A \subset B \Leftrightarrow I_A \leq I_B \Leftrightarrow I_{B \setminus A} = I_B - I_A$$
- $$ A = B \Leftrightarrow I_A = I_B $$
- $$ I_{A \cup B} = I_A + I_B - I_{AB} = I_A \vee I_B, {I_{\bigcup_{i \in I}A_i}} = \max_{i \in I} I_{A_i}$$
- $$ I_{AB} = I_A I_B = I_A \wedge I_B, {I_{\bigcap_{i \in I}A_i}} = \min_{i \in I} I_{A_i}$$

### 1.2.4

De Morgan原理:  
$I$是任意指标集, 则
$$ (\bigcup_{i \in I} A_i)^c = \bigcap_{i \in I} A_i^c $$
$$ (\bigcap_{i \in I} A_i)^c = \bigcup_{i \in I} A_i^c $$

使用示性函数进行证明：
$$ 
    \begin{align}
        I_{(\bigcup_{i \in I} A_i)^c} &= 1 - I_{\bigcup_{i \in I} A_i} \notag \\ 
        &= 1 - \max_{i \in I} I_{A_i} \notag \\
        &= \min_{i \in I} (1 - I_{A_i}) \notag \\
        &= \bigcap_{i \in I} A_i^c \notag 
    \end{align}
$$

