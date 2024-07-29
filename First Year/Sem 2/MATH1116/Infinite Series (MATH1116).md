>[!notation]
>If we have $p\le q$ positive integers,
>$$\begin{align*}
>\sum\limits_{n=p}^{q}a_{n} &= a_{p}+a_{p+1}+\cdots+a_{q}.
>\end{align*}$$

>[!def]
>Given a sequence $\left\{a_{n}\right\}_{n=1}^{\infty}$ we associate another sequence $\left\{s_{n}\right\}_{n=1}^\infty$, where,
>$$\begin{align*}
>s_{k} &= \sum\limits_{n=1}^{k}a_{n}.
>\end{align*}$$
>This is called the sequence of *partial sums*.
>We can now write,
>$$\begin{align*}
>\sum\limits_{n=1}^{\infty}a_{n} &= \lim_{m \longrightarrow \infty}s_{m},
>\end{align*}$$
>to denote the limit of the partial sums $\left\{s_{n}\right\}_{n=1}^{\infty}$ when this sequence converges.

>[!remark]
>We can easily construct $\left\{s_{n}\right\}$ from $\left\{a_{n}\right\}$, but we can also reconstruct $\left\{a_{n}\right\}$ from $\left\{s_{n}\right\}$ using $a_{k} = s_{k} - s_{k-1}$. So no information is lost in this transformation.

>[!example]
>$$\sum\limits_{n=1}^{\infty}1.$$
>This does not converge, so we say that it *diverges*.
>We denote $s_{k} = k$, which is not bounded, so then $s_{k}$ does not converge.

>[!example]
>$$\sum\limits_{n=1}^{\infty}(-1)^{n}$$
>This diverges, as $s_{k}$ is not Cauchy.

>[!question]
>How can we determine whether or not a series converges?
>If a series converges, to what real number does it converge?

>[!example]
>