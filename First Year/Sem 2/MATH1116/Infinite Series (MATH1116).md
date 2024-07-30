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

>[!remark]
>$\sum\limits_{i=1}^{\infty}a_{n}$ converges if $\left\{s_{k}\right\}_{k=1}^{\infty}$ is Cauchy.
>So for all $\varepsilon$, there is some $N>0$ such that $m,n>N \Rightarrow |s_{n}-s_{m}|<\varepsilon$.
>
>>[!theorem]
>>A series of real numbers $\sum\limits_{i=1}^{\infty}a_{n}$ converges if and only if, for all $\varepsilon>0$ there is some $N$ such that $n\ge m\ge N \Rightarrow |a_{m+1}+\cdots+a_{n}|<\varepsilon$.
>>>[!corollary]
>>>If we take $m=n-1$, then we require that,
>>>$$\begin{align*}
>>>|a_{n}|<\varepsilon.
>>>\end{align*}$$
>>>In other words, if the series converges, we must have that $\lim_{n \longrightarrow \infty}a_{n} = 0$.
>>>The contrapositive of this is very useful for proving divergence.
>>>**Note that the converse does not necessarily hold.**
>>>Consider the harmonic series, $\sum\limits_{i=1}^{\infty} \frac{1}{n} = 1 + \frac{1}{2} + \frac{1}{3} + \cdots$. As all terms are positive, $\left\{s_{k}\right\}$ is monotone increasing, however as this is in fact unbounded, it does not converge.
>>>>[!proof]
>>>>Note that $s_{1}\ge \frac{1}{2}$, $s_{2}\ge \frac{1}{2}$, $s_{3}+s_{4}>\frac{1}{2}$, $s_{5}+s_{6}+s_{7}+s_{8}>\frac{1}{2}$, and so on. So we can find $N$ large enough that $s_{N}>M$ for any arbitrarily large $M$.

>[!example]
>Fix $-1< x< 1$ and consider the *geometric series*,
>$$\begin{align*}
>\sum\limits_{i=0}^{\infty}x^{n}.
>\end{align*}$$
>>[!theorem]
>>As long as $x\in(-1,1)$, this series converges to $\frac{1}{1-x}$.
>>>[!proof]
>>>Consider the $s_{k} = 1 + x + \cdots + x^{k}$. Then,
>>>$$\begin{align*}
>>>xs_{k} &= x + x^{2} + \cdots + x^{k} + x^{k+1}\\
>>>s_{k} - xs_{k} &= 1 - x^{k+1}\\
>>>s_{k} &= \frac{1-x^{k+1}}{1-x}.\\
>>>\end{align*}$$
>>>Now we may compute the limit of this sequence,
>>>$$\begin{align*}
>>>\lim_{k \longrightarrow \infty}s_{k} &= \frac{1}{1-x}.
>>>\end{align*}$$
>
>
>Note that if $x\ge 1$, $x^{n}\not\longrightarrow 0$, so the series does not converge.
>

>[!remark]
>The main non-trivial convergent series we will look at is the geometric series with $x\in(-1,1)$.
>Other than this, the most common way to show convergence is to compare to a known series (most commonly the geometric series).

