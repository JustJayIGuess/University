>[!def]
>An infinite sequence is a function $S : \mathbb{N} \longrightarrow \mathbb{R}$.
>We usually write $S = S_{1}, S_{2}, S_{3}, ...$

>[!example]

$$\begin{gather*}
S = 1, 2, \pi, -4, 211, ...\\
T = 2, 4, 6, 8, ...\\
F\text{ defined by }f_{1} = 1, f_{2}=1,f_n=f_{n-1}+f_{n-2}
\end{gather*}$$

# Convergence
>[!def]
>$S$ *converges* to $L$ if for all $\epsilon>0$, there exists some $N\in \mathbb{N}$ such that for $n>N$ it is impled that $|s_{n}-L|<\epsilon$.
>We may equivalently write,
>$$\begin{align*}\lim_{n \rightarrow \infty}s_{n} = L\end{align*}$$

>[!example]
>$s_{n} = \frac{1}{n^{2}}$ converges to 0, as for any arbitrarily small number, such as $\frac{1}{1000}$, we can go along to a high enough $n$ such that for all higher terms, $s_{n}$ is within $\frac{1}{1000}$ of 0.

# Subsequences
Consider the sequence $1, \frac{1}{2}, 1, \frac{1}{3}, 1, \frac{1}{4},...$
This does not converge, however it does have convergent subsequences:
$$\begin{align*}
1, 1, 1, 1, 1, ... \longrightarrow 1\\
\frac{1}{2}, \frac{1}{3}, \frac{1}{4}, \frac{1}{5},... \longrightarrow 0
\end{align*}$$
>[!theorem]
> Suppose that $f$ is a function for which the limit $\lim_{x \rightarrow a}f(x)=b$. Let $S$ be any sequence such that for $a\ne s_{i}$ and $\lim_{i \rightarrow \infty}s_{i} = a$, then,
> $$\begin{align*}
> \lim_{i \rightarrow \infty}f(s_{i})=b.
> \end{align*}$$
