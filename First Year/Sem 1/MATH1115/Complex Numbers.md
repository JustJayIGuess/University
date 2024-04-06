>[!def]
>The complex numbers are defined as $\mathbb{C} = \left\{a+bi \mid a,b\in \mathbb{R}\right\},\ \text{where }i^{2}=-1$. Note that $\mathbb{C}$ is really just $\mathbb{R}^{2}$ equipped with a multiplication rule.
>$\mathbb{C}$ is an example of a field, which is a set equipped with addition and multiplication.

>[!lemma]
>For any $a+bi\ne 0$, there is,
>$$(a+bi)^{-1} = \frac{a-bi}{a^{2}+b^{2}}$$

>[!remark]
>$\mathbb{C}$ satisfies most of the [[Axioms for Numbers]], however there is no set $P$ for the positives, as it doesn't make sense to talk about which complex numbers are positive. Additionally there is no least upper bound for $\mathbb{C}$.

>[!theorem]
>*Fundamental Theorem of Algebra*
>All degree $n$ polynomials $p(z)=\sum\limits_{i=0}^{n}a_{i}z^{i}$ with $n\ge1\in\mathbb{N},\ a_{i}\in\mathbb{Z}$ and $a_{n}\ne 0$ have at least one root.

>[!cor]
>We can always factor $p(z)$ with $$\begin{align*}p(z)=a_{n}(z-z_{1})\cdots(z-z_{n})=a_{n}\prod_{j=1}^{n}(z-z_{j})\end{align*}$$.
---
>[!proof]
>By induction on the degree of $p(z)$, $n$.
>**Base case.**
>$n=0$ is clear.
>**Inductive step.**
>Consider some polynomial $p(z)$, $a_{n}\ne 0$, $n\ge 1$. By FTA, we have a root $z-z_{1}$.
>$$\begin{align*}\frac{p(z)}{z-z_{2}} &= q(z)+\frac{r}{z-z_{1}}\\p(z) &= (z-z_{1})q(z)+r\end{align*}$$
>Let $z=z_{1}$,
>$$\begin{align*}p(z_{1})=0=0+r \Rightarrow r=0\end{align*}$$
>So $q(z)$ divides $p(z)$. Now $q(z)$ can be factored by the inductive hypothesis.

# Conjugates
>[!def]
>Notice $i^{2} = (-i)^{2} = -1$. So $\mathbb{C}$ has a symmetry about $i \longmapsto -i$.
>We therefore define the *complex conjugate* of $z = a+bi$ as,
>$$\begin{align*}\bar{z} &= a-bi\end{align*}$$

>[!lemma]
>$$\begin{align*}z=\bar{z} \Rightarrow z\in\mathbb{R}\end{align*}$$
---
>[!lemma]
>$$\begin{align*}\overline{z+w} &= \bar{z}+\bar{w}\end{align*}$$
---
>[!lemma]
>$$\begin{align*}\overline{zw} &= \bar{z}\times\bar{w}\end{align*}$$
---
>[!lemma]
>$$\begin{align*}\overline{z^{-1}} &= \bar{z}^{-1}\end{align*}$$
---
>[!lemma]
>If $p(z)$ has real coefficients, then $p(z_{1})=0 \Leftrightarrow p(\overline{z_{1}})=0$, so roots come in pairs.

>[!example]
>Suppose $p(z)=z^{3}+1$.
>Notice that $z_{1}=-1$ is a root. So $(z+1)$ is a factor.
>![[Complex Numbers 2024-03-20 12.46.30.excalidraw]]
>So we therefore have that $p(z)=(z+1)(z^{2}-z+1)$. Now we can use the quadratic formula.
>$$\begin{align*}z &= \frac{ -b\pm \sqrt{b^{2}-4ac}}{2a}\\ z_{2} &= \frac{1-\sqrt{3}i}{2},z_3= \frac{1+\sqrt{3}i}{2}\end{align*}$$
>Therefore $p(z)=(z+1)\left(\frac{1-\sqrt{3}i}{2}\right)\left(\frac{1+\sqrt{3}i}{2}\right)$.

>[!def]
>Polar form is defined as comprising a modulus, $|z|$, and argument, $arg(z)$.
>So $z = |z|(\cos\theta + i\sin\theta)$.
>However $\theta$ is only well-defined up to an integer multiple of $2\pi$.
>We can define $e^{i\theta} = \cos\theta + i\sin\theta$.

>[!lemma]
>$$\begin{align*}(re^{i\theta})(se^{i\phi}) &= rse^{i(\theta+\phi)} \\ (re^{i\theta})^{n}&= r^{n}e^{in\theta}\end{align*}$$

>[!lemma]
>If $z = re^{i\theta}$ with $r \ne 0$, then $z$ has exactly $n$ $n^{th}$ roots.
>$$\begin{align*}w_{k} &= se^{i\phi_k}\end{align*}$$
>$$\begin{align*}
s &= \sqrt{r}\\
\phi_k &= \frac{\theta+2\pi k}{n},\ k\in\mathbb{Z}
\end{align*}$$
>Note that $k,k+n$ give the same $w$ so it is only required we use $k=0,1,...,n-1$.

>[!example]
>$$\begin{align*}
iz_{1}+ (1+i)z_{2} &= 3\\
(1-i)z_{1} + z_{2} &= 2i\\
\\
A &= \begin{bmatrix}i & 1+i\\
1-i & 1\end{bmatrix}\\
A^{-1}&= \frac{1}{i(1)-(1+i)(1-i)}\begin{bmatrix}1 & -1-i \\ -1+i & i\end{bmatrix}\\
&= \frac{-2-i}{5}\begin{bmatrix}1 & -1-i \\ -1+i & i\end{bmatrix}\\
&= \frac{1}{5}\begin{bmatrix}-2-i & 1+3i \\ 3-i & 1-2i\end{bmatrix}\\
\\
A^{-1}b &= \frac{1}{5}\begin{bmatrix}-12-i \\ 13-i\end{bmatrix}
\end{align*}$$
