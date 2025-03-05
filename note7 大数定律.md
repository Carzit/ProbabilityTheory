# 7 大数定律

扔一枚硬币, 我们说正面出现的概率为$p$, 反面出现的概率为$q := 1 − p$, 根据在哪里? 为什么合理? 对这个问题, 物理学家和数学家的思维是不同的.

物理学家的办法是, 做几次试验, 每次扔它成千上万次, 如果每次正反面出现的次数之比都接近于$p : q$, 那么就代表这个假设是正确的, 合理的. 然后再给个误差范围, 基本上就可以了. 事实上, 实际操作中也只能是这个办法.

而数学家无法接受这种思维方式, 这简直是岂有此理嘛! 按这种方式, 哥德巴赫猜想早就证明了嘛, 孪生素数猜想也早就证明了嘛, 所以需要证明.

第一个给出严格证明的是Jacob Bernoulli. 他的证明实际上是说明了用频率(的极限)来定义概率的合理性, 即当重复试验的次数足够大时, 正反两面出现的次数之比会稳定在$p:q$附近. 这就是所谓的大数定理, 而这里的“大数”指的就是试验的次数很大.

## 7.1 Markov 大数定律

现在持续地抛上面的那枚硬币, 当第$i$次出现正面时记$\xi_i$为1, 反面时记为0. 则$\xi_1, \xi_2, \dots$独立, 且$\xi_i \sim B(p)$. 进行$n$次实验后, 正面出现的总次数为$\mu_n = \sum_{i=1}^n\xi_i$, 正面出现的频率为
$$
\frac{\mu_n}{n} = \frac{1}{n}\sum_{i=1}^n\xi_i
$$


上面的问题就是在问$\frac{1}{n}\sum_{i=1}^n\xi_i$收敛吗? 以什么方式收敛? 如果收敛, 极限是$p$吗?

诸如此类的问题构成了所谓大数定律的研究范畴. 由于随机变量序列收敛的方式有很多, 本节先从依概率收敛的大数定律讲起.

我们先明确什么是大数定律

> **(大数定律)**设$\{\xi_i\}$是一列随机变量. 记$S_n := \sum_{i=1}^n\xi_i$若
> $$
> \frac{S_n - \mathbb{E}[S_n]}{n} \stackrel{P}{\rightarrow} 0
> $$
> 则称$\{\xi_i\}$服从大数定律.

下面是Markov大数定律. 这个定理的证明现在看起来是如此直接和简短.

> **(Markov大数定律)**.若$\{\xi_i, i \geqslant 1\}$是一列随机变量序列, $D[\xi_i] < \infty, \forall i \geqslant 1$ 且
> $$
> \lim_{n\to\infty}\frac{D[\xi]}{n^2} = 0
> $$
> 则$\{\xi_i\}$服从大数定律.

证明*.* 取$f(x) = x^2$，由Chebyshev不等式有, $\forall \epsilon > 0$
$$
P(\frac{S_n - \mathbb{E}[S_n]}{n} \geqslant \epsilon) \leqslant \frac{\mathbb{E}[(S_n - \mathbb{E}[S_n])^2]}{n^2\epsilon^2} = \frac{D[S_n]}{n^2\epsilon^2} \to 0
$$


那么, 什么样的Markov大数定律满足呢?

> **(Chebyshev大数定律)**. 设$\{\xi_i, i \geqslant 1\}$是一列两两不相关的随机变量序列*,* 且$D[\xi_i] \leqslant C, \forall i \geqslant 1$, 
>
> 则$\{\xi_i, i \geqslant 1\}$服从大数定律*.*

证明. 
$$
\frac{D[S_n]}{n^2} = \frac{1}{n^2}\sum_{i=1}^nD[\xi_i] \leqslant \frac{C}{n} \to 0
$$

> **(Bernoulli大数定律)**. 设$\mu_n$是事件$A$在$n$次独立试验中出现的次数, $p$是$A$在每次试验中发生的概率*,* 则
> $$
> \frac{\mu}{n} \stackrel{P}{\rightarrow} 0
> $$
> 

证明. 在Chebyshev大数定律中, 取$\xi_i \sim B(p)$, $\{\xi_i\}$相互独立, 则
$$
D[\xi_i] = p(1-p) \leqslant \frac14, \forall i
$$
满足Chebyshev大数定律.



如果我们面对的是像上面这样的独立随机变量序列, 则有关方差的条件可以放宽.

> 设$\{\xi_i, i \geqslant 1\}$是一列独立随机变量序列*,* $\mathbb{E}[\xi_i]=0, \forall i \geqslant 1$, 且下列条件之一满足: 
>
> (1) $1 \leqslant p < 2$时
> $$
> \frac{1}{n^p}\sum_{i=1}^n||\xi_i||_p^p \to 0
> $$
> (2) $p \geqslant 2$时
> $$
> \frac{1}{n^2}\sum_{i=1}^n||\xi_i||_p^2 \to 0
> $$
> 则大数定律成立

证明. 因为$\mathbb{E}[\xi_i]=0$
$$
P(\frac{S_n-\mathbb{E}[S_n]}{n})=P(\frac{S_n}{n})
$$
取$f(x) = x^p$, 
$$
P(|\frac{S_n}{n}| \geqslant \epsilon) \leqslant \frac{\mathbb{}E[\frac{|S_n|^p}{n^p}]}{\epsilon^p} = \frac{1}{n^p\epsilon^p}||S_n||_p^p
$$
借助Chatterji不等式和Rio不等式
$$
\frac{1}{n^p\epsilon^p}||S_n||_p^p \leqslant 
\begin{cases}
\frac{2^{2-p}}{\epsilon^p}\frac{1}{n^p}\sum_{i=1}^n||\xi||_p^p, 1 \leqslant p < 2\\
\frac{p-1}{\epsilon^p}\frac{1}{n^p}\sum_{i=1}^n||\xi||_p^2, p \geqslant 2\\
\end{cases}
$$



最后, 我们来看看Bernoulli大数定律的一个有趣的应用, 即Weierstrass定理的概率证明.





## 7.2 强大数定律

如果把大数定律的结论
$$
\frac{S_n - \mathbb{E}[S_n]}{n} \stackrel{P}{\rightarrow} 0
$$
加强为
$$
\frac{S_n - \mathbb{E}[S_n]}{\phi(n)} \stackrel{\text{a.s.}}{\rightarrow} 0
$$
其中$\phi(n)=O(n)$, 则称为强大数定律.



本节恒设$\xi_1, \xi_2, \dots$独立同分布, 且$\mathbb{E}[\xi_i] = 0$. 记. 为得到强大数定律, 我们先准备两个分析引理. 第一个是:

> **(Toeplitz引理)**. 设$\{a_i\}$是非负数列, $a_i> 0, b_n := \sum_{i=1}^{n}a_i \uparrow \infty$, $\{x_i\}$是数列且$x_n \to \infty$. 则
> $$
> \lim_{n\to\infty}\frac{1}{b_n}\sum_{i=1}^{n}a_ix_i = x
> $$

> **(Kronecker引理)**. 设$\{x_i\}$是数列, $b_i > 0$且$b_n \uparrow \infty$. 若
> $$
> \sum_{i=1}^\infty\frac{x_i}{b_i}
> $$
> 收敛. 则
> $$
> \lim_{n\to\infty}\frac{1}{b_n}\sum_{i=1}^nx_n = 0
> $$

如果$\{\xi_i\}$独立同分布，则
$$
\frac{S_n}{n} \stackrel{\text{a.s.}}{\to}\mathbb{E}[\xi_i]
$$
