>[!question]
>*How might we approximate a differentiable function $f$ at $a$?*
>Take $h(x) = f'(a)(x-a) + f(a)$. This gives a linear approximation of $f$ at $a$.
>>[!note]
>>If we translate by $(a,f(a))$, so that $h$ intersects the origin, then we call $h$ *affine*.

>[!remark]
>We can generalise these approximations to higher-dimensional spaces, e.g. for $f : \mathbb{R^{2}} \longrightarrow \mathbb{R}$.

>[!def]
>Suppose that $L(x)$ is affine. Then $L(x)$ is a *good approximation* of $f$ at $a$ if,
>$$\begin{align*}
>\lim_{x \longrightarrow a} \frac{f(x)-L(x)}{x-a} &= 0.
>\end{align*}$$

>[!theorem]
>Any function $f$ has a good approximation at $a$ **if and only if** $f'(a)$ exists.
>If $f$ has a good approximation at $a$, then,
>$$\begin{align*}
>L(x) &= f'(a)(x-a) + f(a).
>\end{align*}$$
>
>>[!proof]
>>Suppose that $f$ is differentiable.
>>$$\begin{align*}
>>\lim_{x \longrightarrow a} \frac{f(x)-L(x)}{x-a} &= \lim_{x \longrightarrow a} \frac{f(x) - (f(a)+f'(a)(x-a))}{x-a}\\
>>&= \lim_{x \longrightarrow a} \frac{f(x)-f(a)}{x-a} - \frac{f'(a)(x-a)}{x-a}\\
>>&= f'(a) - f'(a)\\
>>&= 0.
>>\end{align*}$$
>>So then $L(x)$ is a good approximation.
>>The other direction will be proven later.

>[!question]
>Can we do better than a linear approximation?

>[!theorem]
>Suppose that $f$ is $n$ times differentiable, and let $P_{n,a}$ be a degree $n$ polynomial such that $P^{(n)}(a) = f^{(n)}(a)$. I.e., $P$ and $f$ should match in the first $n$ derivatives.
>Then,
>$$\begin{align*}
>P_{n,a}(x) &= a_{0} + a_{1}(x-a) + a_{2}(x-a)^{2}+\cdots+a_{n}(x-a)^{n}\\
>a_{i} &= \frac{f^{(i)}(a)}{i!}\\
>\\
>\Rightarrow P_{n,a}(x) &= \sum\limits_{i=0}^{n} \frac{f^{(i)}(a)}{i!}(x-a)^{i}.
>\end{align*}$$
>In this case, we must have that,
>$$\begin{align*}
> \lim_{x \longrightarrow a} \frac{f(x)-P_{n,a}(x)}{(x-a)^{n}} &= 0.
>\end{align*}$$
>This is a strong statement, as $(x-a)^{-n}$ grows rapidly as $x \longrightarrow a$, so the numerator must more rapidly approach zero.

>[!def]
>The *$n^{th}$ Taylor Polynomial* of $f$ at $a$ is given by the above formula.
>
>>[!example]
>>Find the fourth Taylor polynomial of $e^{x}$ at $x=0$.
>>We have,
>>$$\begin{align*}
>>e^{0} &= 1\\
>>(e^{x})'|_{x=0} &= 1\\
>>\vdots\\
>>\\
>>\Rightarrow P_{4,0}(x) &= 1 + x + \frac{x^{2}}{2!} + \frac{x^{3}}{3!} + \frac{x^{4}}{4!}.
>>\end{align*}$$
>>```desmos-graph
>>f(x) = 1 + x + x^2/2! + x^3/3! + x^4/4!
>>g(x) = e^x
>>```
>>>$e^{x}$ in green, $P_{4,0}(x)$ in blue.

>[!theorem]
>The coefficients $a_{i}$ are the only correct coefficients.
>
>>[!proof]
>>Suppose that $P^{(i)}(a) = f^{(i)}(a)$.
>>$$\begin{align*}
>>P(a) &= a_{0} := f(a)\\
>>P'(x) &= b_{1} + 2b_{2}(x-a)+\cdots\\
>>P' (a) &= b_{1}\\
>>P''(x) &= \cdots\\
>>\vdots
>>\end{align*}$$
>>You can see where this is going :)

>[!theorem]
>Let $P_{n,a}$ be the $n^{th}$ Taylor polynomial of $f$ at $a$. Then,
>$$\begin{align*}
> \lim_{x \longrightarrow a} \frac{f(x)-P_{n,a}(x)}{(x-a)^{n}} &= 0.
>\end{align*}$$
>
>>[!proof] Sketch Proof.
>>We can rewrite the limit as,
>>$$\begin{align*}
>> \lim_{x \longrightarrow a} \frac{f(x) - P_{n-1,a}(x) - \frac{f^{(n)}(a)(x-a)^{n}}{n!}}{(x-a)^{n}} &= 0.
>>\end{align*}$$
>>We would therefore like to show (from the above). We can then use L'Hospital's rule repeatedly to show this to be true.
>>$$\begin{align*}
>> \lim_{x \longrightarrow a} \frac{f(x)-P_{n-1,a}(x)}{(x-a)^{n}} &= \frac{f^{(n)}a}{n!}.
>>\end{align*}$$
>>This is messy in notation, so i ain writing allat.
>>
