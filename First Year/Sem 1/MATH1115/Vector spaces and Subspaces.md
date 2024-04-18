>[!def]
>Let $F = \mathbb{R}$ or $F = \mathbb{C}$. An element of $F$ is called a *scalar*.
>An *$F$-vector space* is a set $V$ with two operations, and elements of an $F$-vector space are called *vectors*.
>- Addition: $V\times V  \longrightarrow V$
>- Multiplication by scalars: $F\times V\longrightarrow V,\ (a,v)\longmapsto av$
>
>These operations will satisfy the following properties.
>1. Commutativity
>2. Associativity
>3. Existence of unique zero vector
>4. Existence of additive inverse
>5. Existence of multiplicative identity (scalar)
>6. Multiplicative associativity
>7. Distributive property one - $(ab)v = a(bv)$
>8. Distributive property two - $(a+b)v = av+bv$

---

>[!lemma]
>$0v=0\qquad\forall v\in V$
>Note that the left zero is the scalar zero, and the right zero is the zero vector.

>[!proof]
>$$\begin{align*}
0v &= (0+0)v\\
0v &= 0v + 0v\\
0v - 0v &= 0v + 0v - 0v\\
\vec{0} &= 0v\\
\vec{0} &= 0v
\end{align*}$$
>Note that the $\vec{0}$ symbol has been used to clarify zeroes.

---

>[!lemma]
>$$\begin{align*}
(-1)v &= -v
\end{align*}$$

>[!proof]
We will show that $v+(-1)v=0$.
>$$\begin{align*}
v+(-1)v &= 1v + (-1)v\\
&= (1+(-1))v\\
&= 0v\\
&= 0
\end{align*}$$

---

>[!example]
>The following are all vector spaces
>- $\mathbb{R}^{n}$ is a real vector space.
>- $\mathbb{C}^{n}$ is a complex vector space
>- All functions $f : \mathbb{R}\longrightarrow \mathbb{R}$ forms a vector space
>- The singleton set $\left\{0\right\}$
>- All polynomials
>- All degree $\le n$ polynomials
>- All continuous functions $[-1,1]\longrightarrow \mathbb{R}$
>- An $m$-dimensional hyperplane through the origin in $\mathbb{R}^{n}$
>- Set of matrices $\mathbb{R}^{m\times n}$
>- Sequences of real numbers

---

>[!def]
>A *subspace* of a vector space $V$ is a subset $W\subseteq V$ which is also a vector space, using the same addition and scalar multiplication in $W$ as in $V$.

To check if some subset $W\subseteq V$ is a subspace, it suffices to check these three things:
1. The zero vector is in the subspace
2. If two vectors are in the subspace then their sum is also in the subspace
3. For all $a\in F,w\in W$, we have $aw\in W$

>[!remark]
>This is sufficient as we can rebuild the properties of a vector space from this. For instance, using the third rule, we have that $(-1)w = -w\in W$.

>[!example]
>Note:
>- $\mathbb{Q}\subseteq \mathbb{R}$ is not a subspace, because we have $\pi\in\mathbb{R}$, but $\pi w\not\in\mathbb{Q}$ for $w\in\mathbb{Q}$
>- Any vector space $V$ is a subspace of itself.
>
>The following are subspaces of $\mathbb{R}^2$:
>- $\left\{0\right\}$
>- Any line through zero
>- $\mathbb{R}^{2}$
>
>The following are subspaces of $\mathbb{R}^{3}$:
>- $\left\{0\right\}$
>- Any line through zero
>- Any plane through zero
>- $\mathbb{R}^{3}$
>
>The symmetric $n\times n$ matrices is a subspace of $\mathbb{R}^{n\times n}$


