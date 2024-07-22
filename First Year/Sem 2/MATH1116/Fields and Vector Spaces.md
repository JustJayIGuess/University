>[!def]
>A *field* is a set $F$ that has two operations, $$+ : F\times F \longrightarrow F,\quad\cdot : F\times F \longrightarrow F,$$where:
>- both operations are associative
>- both operations are commutative
>- the two operation are associated by the distributives law
>- an additive and multiplicative identity exists which are distinct
>- additive inverses exist for every element $a\in F$
>- multiplicative inverses exist for every element $a\in F\setminus \left\{0\right\}$.

>[!example]
>Prove that the real numbers is a field.

>[!remark]
>Classical mechanics takes place in $\mathbb{R}$, and quantum in $\mathbb{C}$, so these sets are mathematically very useful!

>[!example]
>Prove that $\mathbb{Q}(\sqrt{2}) = \left\{a+b\sqrt{2} \mid a,b\in \mathbb{Q}\right\}\subset \mathbb{R}$ is a field.
>Note that this means that we need to show that $\left(a+b\sqrt{2}\right)^{-1}\in \mathbb{Q}(\sqrt{2}).$
>>[!proof]
>>$$\begin{align*}
>>\left(a+b\sqrt{2}\right)^{-1} &= \frac{a-b\sqrt{2}}{a^{2} - 2b^{2}}\\
>>&= \frac{a}{a^{2} - 2b^{2}} - \frac{b}{a^{2}-2b^{2}}\sqrt{2}\in\mathbb{Q}(\sqrt{2})
> \end{align*}$$

>[!remark]
>We may also consider set of residues of integers $\mathbb{F}_{p} = \left\{[a] \mid a=0,1,\cdots,p-1\right\}$ for a prime $p$ or for $p=q^{k}$ for a prime $q$ and natural number $k$.
>If we define addition such that $[a]+[b]:=[a+b]$, and multiplication such that $[a]\cdot[b] = [a\cdot b]$, then $\mathbb{F}_{p}$ is a *finite field*.

>[!def]
>A *polynomial* over a field $\mathbb{F}$, $(a_{0},a_{1},\cdots, a_{n}, \cdots)$, with $a_{i}\in \mathbb{F}$ and finitely many $a_{i}\ne 0$, is a mathematical object $f(x) = a_{0}x^{0} + a_{1}x_{1}+\cdots+a_{n}x^{n} +\cdots$.
>Given a polynomial, we may make a *polynomial function* by declaring,
>$$\begin{align*}
>f(x)\in F[x]\mapsto f(b) &= a_{0}+a_{1}b+a_{2}b^{2}+\cdots\\
>f &: F \longrightarrow F.
\end{align*}$$

