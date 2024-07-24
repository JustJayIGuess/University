
>[!remark]
>We will use $\mathbb{F}[x]$ to refer to the set of all polynomial in $x$ over the field $\mathbb{F}$.
>We will use $\mathbb{F}_{\le n}[x]$ to refer to the set of all polynomials of degree at most $n$ in $x$ over the field $\mathbb{F}$.
>Note that the zero polynomial is the only polynomial with no degree.

>[!def]
>A *polynomial* over a field $\mathbb{F}$, $(a_{0},a_{1},\cdots, a_{n}, \cdots)$, with $a_{i}\in \mathbb{F}$ and finitely many $a_{i}\ne 0$, is a mathematical object $f(x) = a_{0}x^{0} + a_{1}x_{1}+\cdots+a_{n}x^{n} +\cdots$.
>Given a polynomial, we may make a *polynomial function* by declaring,
>$$\begin{align*}
>f(x)\in \mathbb{F}[x]\mapsto f(b) &= a_{0}+a_{1}b+a_{2}b^{2}+\cdots\\
>f &: F \longrightarrow F.
>\end{align*}$$
>Note that a polynomial itself is merely a mathematical object, and not necessarily a function. In the regular polynomial definition, a term such as $x^{2}$ does not yet have a formal meaning. Once we define a polynomial function we give this a meaning.

>[!def]
>We define addition of polynomials as follows:
>$$\begin{align*}
>(a_{n})+(b_{n}) &:= (a_{n}+b_{n})\\
>&\Updownarrow\\
>\sum\limits a_{i}x^{i} + \sum\limits a_{i}x^{i} &:= \sum\limits(a_{i}+b_{i})x^{i}.
>\end{align*}$$
>We similarly define multiplication as follows:
>$$\begin{align*}
>(a_{n})\cdot(b_{n}) &:= \sum\limits_{k=0}^{n}a_{k}b_{n-k}\\
>&\Updownarrow\\
>\left(\sum\limits a_{i}x^{i}\right)\left(\sum\limits b_{i}x^{i}\right) &:= \sum\limits_{i}\left(\sum\limits_{j}a_{j}b_{i-j}\right)x^{i}.
>\end{align*}$$
>These operations satisfy the conditions to form a field, so $\mathbb{F}_{\le n}[x]$ and $\mathbb{F}[x]$ form a fields.

