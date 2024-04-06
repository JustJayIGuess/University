>[!def]
>Consider the set $\mathbb{C}^{n}$, the set of all $n$-tuples with the complex numbers. We can interpret this as the set of all $n$ dimensional vectors.
>Consider also the set $\mathbb{C}^{m\times n}$, which we interpret as the set of all matrices with entries in $\mathbb{C}$.

The majority of the rules derived about matrices in real numbers also applies to matrices in $\mathbb{C}^{m\times n}$.

>[!def]
>For any $x,y\in\mathbb{R}^{n}$, we define their *dot product* as,
>$$\begin{align*}x\cdot y &= x^{T}y = \sum\limits_{j=1}^{n}x_{j}y_{j}\end{align*}$$
>For complex numbers, we define the following,
>$$\begin{align*}z\cdot w &= \bar{z}^{T}w = \sum\limits_{j=1}^{n}\bar{z}_{j}w_{j}\end{align*}$$

>[!def]
>We can then define the *norm* (or length) of a vector (real or complex) as,
>$$\begin{align*}|\lvert{x}\rvert| &= \sqrt{x\cdot x}\end{align*}$$

Note the following properties of the dot product for real numbers.
- $x\cdot y = y\cdot x$
- $(cx)\cdot y = c(x\cdot y)$
- $x\cdot(cy) = c(x\cdot y)$
- $||n||\ge 0,\ ||x|| = 0 \Leftrightarrow x=0$

The following are similar properties for complex valued matrices.
- $z\cdot w = \overline{w\cdot z}$
- $(cz)\cdot w = \bar{c}(z\cdot w)$
- $z\cdot (cw) = c(z\cdot w)$
- $||z||\ge 0,\ ||z|| = 0\Leftrightarrow z=0$

>[!def]
>We may define two vectors (real or complex) as being orthogonal if $x\cdot y = 0$.

>[!theorem]
>*Cauchy-Schwartz Inequality*
>For $z, w\in\mathbb{C}^{n}$, we have that,
>$$\begin{align*}|z\cdot w|&\le \|z\|\ \|w\|\end{align*}$$

>[!example]
>$z = (1,i),\ w=(2i,i)$
>$$\begin{align*}
|z\cdot w| &= |-2i + 1| = \sqrt{5}\\
\|z\| &= \sqrt{2}\\
\|w\| &= \sqrt{5}\\
\sqrt{5}&\le \sqrt{10}
\end{align*}$$

>[!proof]
>Both sides are positive, so we can square both sides.
>$$\begin{align*}|z\cdot w|^{2}&\le \|z\|^2\|w\|^{2}\end{align*}$$
>If $z=0$ or $w=0$, then both sides are zero and the statement holds, so now assume $z\ne 0$, $w\ne 0$.
>Now for any $c\in\mathbb{C}$, we have $\|z+cw\|^{2} \ge0$. I.e.,
>$$\begin{align*}\|z+cw\|^{2} &= (z+cw)\cdot(z+cw)\\
&= z\cdot z + z\cdot(cw) + (cw)\cdot z + (cw)\cdot(cw)\\
&= \|z\|^{2} + cz\cdot w + \bar{c}\ \overline{z\cdot w} + |c|^{2}\|w\|^2\\
c &= d\ \overline{z\cdot w},\ d\in \mathbb{R}\\
&\text{Then the middle terms are real}.\\
&= \|z\|^{2}+d|z\cdot w|^{2} + d|z\cdot w|^{2} + d^{2}|z\cdot w|^{2}\|w\|^{2}\\
&\text{Now, let }d=\frac{1}{\|w\|^{2}}.\\
&= \|z\|^{2} - \frac{|z\cdot w|^{2}}{\|w\|^{2}}\ge 0\\
&\text{Then we can rearrage to get the original statement}.\\
\ \tag*{$\blacksquare$}
\end{align*}$$

>[!def]
>Given $z,w\in \mathbb{C}^{n}$, with $z\ne 0$, we can write,
>$$\begin{align*}w &= w_{1} + w_{2} \\ w_{1}\text{ parallel to }z&,\ w_{2}\text{ orthogonal to }z\end{align*}$$
>This is an *orthogonal projection*

>[!proof]
>$$w_{1} = \frac{z\cdot w}{\|z\|^{2}}z$$
