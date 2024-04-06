>[!def]
>A function is a well-defined mapping from elements in a set $A$, called the *domain* to a set $B$, called the *codomain*. In MATH1115, functions will only be using sets of numbers. We may define functions using the following notation.
>$$\begin{align*}
f: X \rightarrow Y
\end{align*}$$
E.g.,
>$$\begin{align*}f : \mathbb{R} \longrightarrow \mathbb{R},\ f(x)=x^{2}\end{align*}$$
>Note that this function must map all elements in $X$ to **exactly one** element in $Y$.

>[!remark]
>In MATH1115, the domain and codomain will generally be subsets of $\mathbb{R}$.

>[!def]
>The *cartesian product* is defined between sets $A$ and $B$ as,
>$$\begin{align*}A\times B &= \left\{(a,b) \mid a\in A,\ b\in b\right\}\end{align*}$$

Note that for a function such as $f(x)=x^{2} : \mathbb{R} \longrightarrow \mathbb{R}$, we can consider the subset of $\mathbb{R}^{2}$ where the pairs $(x, f(x))$ exist. This is called the *graph* of $f$.
$$\begin{align*}
\text{graph of }f &= \left\{(x,f(x)) \mid x\in \mathbb{R}\right\}
\end{align*}$$
We may consider more complex cases of this, such as the function $f : \mathbb{R}^{2} \longrightarrow \mathbb{R}$, whose graph can be said to live in $\mathbb{R}^{2}\times \mathbb{R} = \mathbb{R}^{3}$.

# Function Operations
Consider the following functions.

![[Functions (MATH1115) 2024-02-29 12.17.16.excalidraw|150]]
I.e.,
$$\begin{align*}
f : X \longrightarrow Y\\
g : X \longrightarrow Y\\
h : Y \longrightarrow Z
\end{align*}$$

>[!def]
>We may define *function addition* as,
>$$\begin{align*}(f+g)(x) &:= f(x) + g(x)\\\\ f+g : X &\longrightarrow Y\end{align*}$$

>[!def]
>We may define *function multiplication* as,
>$$\begin{align*}(fg)(x) &:= f(x)g(x)\\\\ fg : X &\longrightarrow Y\end{align*}$$

>[!def]
>We may define *function composition* as,
>$$\begin{align*}(h\circ f)(x) &:= h(f(x))\\\\ h\circ f : X &\longrightarrow Z\end{align*}$$

# Range
>[!def]
>The *range* of $f : X \longrightarrow Y$ is defined as,
>$$\begin{align*}\left\{y\in Y \mid y=f(x)\text{ for some }x\in X\right\}\end{align*}$$
>The range is the same as the **image**.
>E.g., the range of $f(x)=x^{2}$ is $\left\{y\in \mathbb{R} \mid y\ge 0\right\}$.


# Continuity of Real-valued Functions
Consider the a function $f : \mathbb{R} \longrightarrow \mathbb{R}$, and an input $a\in \mathbb{R}$.
We may wonder,
- what is $f$ at $a$?
- what is $f$ near $a$?

>[!def]
>Let $\epsilon > 0$. We say that $f$ is *$\epsilon$-close* to $b$ at $a$ if there is a $\delta>0$ such that,
>$$\begin{align*}0 < |x-a| < \delta\Rightarrow \left|f(x)-b\right|<\epsilon\end{align*}$$

![[Functions (MATH1115) 2024-02-29 12.36.18.excalidraw|500]]

