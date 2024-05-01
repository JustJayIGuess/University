# Linear Combinations
>[!def]
>A *linear combination* of $v_1,\cdots,v_{r}\in V$ is a sum,
>$$\begin{align*}
\sum\limits_{k=1}^{r}a_{k}v_{k},\ a_{i}\in F
\end{align*}$$

# Bases of Vector Spaces
>[!def]
>The set $B = \left\{v_{1},\cdots,v_{r}\right\}$ is a basis for $V$ if and only if every element $v\in V$ is a unique linear combination of $v_1,\cdots,v_r$.
>Uniticity is generally proven by showing that any vector can be written as a linear combination of the bases in at least one way, and at most one way.

---

>[!example]
> In $\mathbb{R}^{2}$, the set $\left\{e_{1}=\begin{bmatrix}1\\0\end{bmatrix}, e_{2}= \begin{bmatrix}0\\1\end{bmatrix}\right\}$ is a basis.
> Any $\begin{bmatrix}x\\y\end{bmatrix}\in\mathbb{R}^{2}$ is a linear combination written as,
> $$\begin{align*}
> \begin{bmatrix}x\\y\end{bmatrix} &= xe_{1} + ye_{1}.
> \end{align*}$$
> In this case, it is clear that each vector can only be written in terms of the bases in one way.
> This particular basis is called the *standard basis*.

---

>[!example]
> In $\mathbb{R}^{2}$, the set $\left\{v_{1}=\begin{bmatrix}2\\1\end{bmatrix}, v_{2}=\begin{bmatrix}-1\\1\end{bmatrix}\right\}$ is also a basis.
> Suppose that we have
> $$\begin{align*}
> \begin{bmatrix}x\\y\end{bmatrix} &= a_{1}\begin{bmatrix}2\\1\end{bmatrix} + a_{2}\begin{bmatrix}-1\\1\end{bmatrix}\\
> &= \begin{bmatrix}2 & -1 \\ 1 & 1\end{bmatrix}\begin{bmatrix}a_{1}\\a_{2}\end{bmatrix}
> \end{align*}$$
> This matrix is invertible, so then every vector may be written as one and only one linear combination of the bases.

# Span
>[!def]
>A set of vectors $\left\{v_1,\cdots,v_{r}\right\}$ *spans* $V$ if any $v\in V$ is a linear combination of $v_{1},\cdots,v_{r}$ in at least one way.

>[!example]
>$\left\{\begin{bmatrix}e\\\pi\end{bmatrix},\begin{bmatrix}5\\7\end{bmatrix},\begin{bmatrix}1\\3\end{bmatrix},\begin{bmatrix}2\\-2\end{bmatrix}\right\}$ spans $\mathbb{R}^{2}$.

# Linear Dependence
>[!def]
>The set of vectors $\left\{v_{1},\cdots,v_{r}\right\}$ are *linearly dependent* if any $v\in V$ is a linear combination in at most one way.

>[!example]
>Suppose that $v$ is a linear combination in two ways.
>Then $0=v-v=(a_{1}-b_{1})v_{1}+\cdots+(a_{r}-b_{r})v_{r}$.
>So a set of vectors are linear independent if and only if.
>$$c_{1}v_{1}+\cdots+c_{n}v_{n}=0\iff c_{1}=0,\cdots,c_{r}=0$$
# Proving Validity of Bases
>[!def]
>$B$ is a basis of $V$ if and only if $B$ spans $V$ and $B$ is linearly independent.

>[!example]
>$\left\{(1,2),(2,4)\right\}$ is not linearly independent, because $2e_{1}-e_{2}=0$.
>So this is not a basis.

# Notation
> [!def]
> If a set is a basis for $V$ and $v = a_{1}v_{1} + \cdots + a_{n}v_{n}$, we write,
> $$\begin{align*}
> [v]_{B} &= \begin{bmatrix}a_{1}\\\vdots\\a_{n}\end{bmatrix}
> \end{align*}$$

>[!example]
>Take the basis $\left\{\begin{bmatrix}2\\1\end{bmatrix},\begin{bmatrix}-1\\1\end{bmatrix}\right\}$
>We can write $\left[\begin{bmatrix}3\\3\end{bmatrix}\right]_{B}=\begin{bmatrix}2\\1\end{bmatrix}$.

