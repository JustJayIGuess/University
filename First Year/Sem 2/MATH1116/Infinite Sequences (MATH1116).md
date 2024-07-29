>[!def]
>An *infinite sequence* is a function $f : \mathbb{N} \longrightarrow \mathbb{R}$ (or to $\mathbb{C}$).

>[!remark]
>Given a sequence $\left\{a_{n}\right\}$, a basic question is whether the sequence will *converge*.

![[Infinite Sequences#Convergence]]

## Conditions for Guaranteed Convergence
>[!theorem]
>If $\left\{a_{n}\right\}$ is **bounded** and **monotone** then $\left\{a_{n}\right\}$ converges, recalling that:
>>[!def]
>>$\left\{a_{n}\right\}$ is *bounded* if there is an $R>0$ such that $\left\{a_{n}\right\}<R\quad\forall n$.
>
>>[!def]
>>$\left\{a_{n}\right\}$ is *monotone* increasing or decreasing if $a_{n+1}>a_{n}$ or $a_{n+1}<a_{n}$ for all $n$, respectively. $\left\{a_{n}\right\}$ can also be monotone nonincreasing or nondecreasing in the same way, with weak inequality instead.

>[!def]
>Given $\left\{a_{n}\right\}$, a *subsequence* $\left\{a_{n_{k}}\right\}_{k=1}^{\infty}$ is given by a subset $n\subset \mathbb{N}$.
>>[!example]
>>$b_{m} = \frac{1}{2^{m}}$ is a subsequence of $a_{n} = \frac{1}{n}$.

>[!theorem]
>*The Bolzano-Weierstrass Theorem.*
>Any **bounded** sequence has a convergent subsequence.
>>[!proof]
>>Given a bounded sequence, we can choose a monotone subsequence. Then the result follows from the previous theorem.

>[!remark]
>It is often difficult to show convergence by definition as the epsilon-delta definition requires us to know a candidate $L$ for the limit.
>It would be nice if there were a condition on $\left\{a_{n}\right\}$ itself that doesn't require $L$ to determine the divergence or convergence of the sequence.
>Then note the following:
> If $\lim_{n \longrightarrow \infty}a_{n} = L$, then there is $N>0$ such that $n>N \Rightarrow |a_{n} - L| < \frac{\varepsilon}{2}$.
> So if $m,n>N$, then $|a_{n} - a_{m}|\le |a_{n} - L| + |L - a_{m}| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} < \varepsilon$.
> So then $|a_{m}-a_{n}| < \varepsilon$.

>[!def]
>A sequence $\left\{a_{n}\right\}$ is *Cauchy* if for all $\varepsilon>0$, there is $N$ such that $m,n>N \Rightarrow |a_{m}-a_{n}|<\varepsilon$.

>[!def]
>The real numbers $\mathbb{R}$ are defined as the set of all [[Equivalence Relations#Equivalence Classes|equivalence classes]] of Cauchy sequences of rationals, where $\left\{a_{n}\right\} = \left\{b_{n}\right\}$ if $\lim_{n \longrightarrow \infty}(a_{n} - b_{n}) = 0$.

>[!theorem]
>$\left\{a_{n}\right\}$ converges if and only if $\left\{a_{n}\right\}$ is Cauchy.
>>[!proof]
>>We have already proven that all convergent sequences are Cauchy.
>>We now need only prove the converse.
>>Suppose that $\left\{a_{n}\right\}$ is Cauchy.
>>If we simply pick $\varepsilon=1$, then we have some $N>0$ such that $m,n>N$ implies $|a_{n} - a_{m}|<1$. Take $a_{m} = a_{N+1}$. Then $|a_{n} - a_{N+1}|<1$. Then $\left\{a_{n}\right\}$ is bounded for $n>N$. Then there are only $N$ points to add to this, so we can construct a maximum as $\max\left\{|a_{N+1}+1|,|a_{1}|,\cdots,|a_N|\right\}$ and similarly for the minimum.
>>Then we know by the Bolzano-Weierstrass theorem that there is a convergent subsequence. So there is $\left\{a_{n_{k}}\right\}_{k=1}^{\infty}$ such that,
>>$$\begin{align*}
>>\lim_{n \longrightarrow \infty}a_{n_{k}} &= L\in \mathbb{R}.
>>\end{align*}$$
>>We now claim that $\left\{a_{n}\right\}$ converges to $L$.
>>First, fix some $\varepsilon>0$. We have some $M>0$ so that $k>M \Rightarrow |a_{n_{k}} - L| < \frac{\varepsilon}{2}$.
>>Since $\left\{a_{n}\right\}$ is Cauchy, we can make $|a_{n}-a_{m}|$ as small as we would like by taking $m,n$ sufficiently large. If we make $|a_{n}-a_{n_{k}}|<\frac{\varepsilon}{2}$, then.
>>$$\begin{align*}
>>|a_{n} - L|\le |a_{n} - a_{n_{k}}| + |a_{n_{k}} - L| < \frac{\varepsilon}{2}+ \frac{\varepsilon}{2} < \varepsilon
\end{align*}$$
>>$$
>>\tag*{$\blacksquare$}
>>$$
>
>>[!remark]
>>This means that $\mathbb{R}$ is *complete*, where a *complete* metric space is a space where all Cauchy sequences converge. $\mathbb{C}$ is also a complete metric space, but $\mathbb{Q}$ is not.

>[!summary]
>We have two main tools for showing convergence of a sequence:
>- Show that $\left\{a_{n}\right\}$ is Cauchy
>- Show that $\left\{a_{n}\right\}$ is bounded and monotone

>[!question]
>What about finding limits explicitly?

>[!theorem]
>Suppose that $\lim_{x \longrightarrow c}f(x) = L$. If $\left\{a_{n}\right\}$ is a sequence that approaches $c$, then $\lim_{n \longrightarrow \infty}f(a_{n}) = L$.

>[!example]
>Compute the limit,
>$$\begin{align*}
>\lim_{n \longrightarrow \infty} \frac{n+1}{n^{2}+2}.
>\end{align*}$$
>>[!check] Solution
>>Exercise.

