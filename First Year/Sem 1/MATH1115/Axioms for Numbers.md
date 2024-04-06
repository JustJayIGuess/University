The axioms for numbers describe the structure of how numbers can add and multiply. From these axioms, any other true property of numbers may be derived.

| Number | Property                                           | Description             |
| ------ | -------------------------------------------------- | ----------------------- |
| P1     | $a+(b+c) = (a+b)+c$                                | Associative             |
| P2     | $a + 0 = 0+a = a$                                  | Additive Identity       |
| P3     | $\forall a\exists(-a),\ a+(-a)=(-a)+a=0$           | Additive Inverse        |
| P4     | $a+b = b+a$                                        | Commutative             |
| P5     | $a(bc)=(ab)c$                                      | Associative             |
| P6     | $a1 = 1a = a, 1\ne 0$                              | Multiplicative Identity |
| P7     | $\forall a\ne 0\exists a^{-1},\ aa^{-1}=a^{-1}a=1$ | Multiplicative Inverse  |
| P8     | $ab=ba$                                            | Commutative             |
| P9     | $a(b+c)=ab+ac$                                     | Distributive            |
From these properties, we may already prove things such as $a0 = 0$.
>[!proof]
>$$\begin{align*}a0 &= a(0+0)\tag{P2}\\
a0 &= a0 + a0\tag{P9}\\
a0 + (-a0) &= a0 + a0 + (-a0)\tag{P3}\\
a0 + (-a0) &= a0 + (a0 + (-a0))\tag{P1}\\
0 &= a0 + 0\tag{P3}\\
0 &= a0 \tag{P2}\\
\ \tag*{$\blacksquare$}\end{align*}$$

There are some additional axioms for inequality.
First, let $P$ be the set of positive numbers.

| Number | Property                                                                                                     |
| ------ | ------------------------------------------------------------------------------------------------------------ |
| P10    | $$\begin{align*}\forall a,\text{ exactly one of the following holds} \\ a=0,\ a\in P,\ -a\in P\end{align*}$$ |
| P11    | $\text{If }a,b\in P\text{, then }a+b\in P$                                                                   |
| P12    | $\text{If }a,b\in P\text{, then }ab\in P$                                                                    |
For notating this, we define that $a < b$ means that $b-a\in P$. Note that this means that $c>0\Rightarrow c-0\in P \Rightarrow c\in P$.
# New Axioms for the Reals
>[!def]
>If $A$ is a non-empty set of real numbers and there exists some $n\in \mathbb{R}$ such that $a<n$ for all $a\in A$. Then there exists $x\in \mathbb{R}$ such that $a\le x$ for all $a\in A$ and if $a\le y$ for all $a\in A$, $y\ge x$.

