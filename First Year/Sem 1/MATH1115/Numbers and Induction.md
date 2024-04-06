Consider the following commonly used sets of numbers (already covered in MATH2222)
![[Sets (MATH2222)#Standard Sets]]

# Adherence of common sets to the axioms
Many common sets of numbers do not follow the [[Axioms for Numbers]].
- $\mathbf{N}$ fails P3 and P2
- $\mathbf{Z}$ fails P7
- $Q$ satisfies all axioms
- $\mathbf{R}$ satisfies all axioms
- $\mathbf{C}$ satisfies all axioms

>[!remark]
>Additional axioms must be added to our list to differentiate between $\mathbf{Q}$ and $\mathbf{R}$, as currently, any argument that is made specifically for the set $\mathbf{R}$ must also be true for $\mathbf{Q}$, which defeats the purpose of constructing the set $\mathbf{R}$.

# Induction
$\mathbf{N}$ may be used to generalise the concept of mathematical induction.
>[!def]
>Given a set of statements $S=\{s_{n}\}_{n=1}^{\inf}$ index by $\mathbf{N}$. The principal of mathematical induction states that if $s_{1}$ is true, and $s_{k+1}$ is true given that $s_{k}$ is true, then all $s\in S$ are true.

Consider the following worked example.

$$\begin{align*}
\text{Show }\sum\limits_{i=1}^{n} (2i-1) &= n^{2}\ \forall\ n\in\mathbf{N}.\\
\end{align*}$$
>[!proof]
>We will use induction to prove this.
>First check base case, $n=1$.
>$$\sum\limits_{i=1}^{n}(2i-1) = \sum\limits_{i=1}^{1} = (2-1) = 1 = 1^{2} = n^{2}$$
>The statement holds for $n=1$.
>Now suppose that the statement holds for $n=k$.
>$$\sum\limits_{i=1}^{k} (2i-1) = k^{2}$$
>Consider now the case $n=k+1$, using the inductive hypothesis above.
>$$\begin{align*}
>\sum\limits_{i=1}^{k+1} (2i-1) &= \sum\limits_{i=1}^{k} (2i-1) + (2(k+1)-1)\\
&= k^{2} + (2k + 2 - 1)\\
&= k^{2}+2k+1\\
&= (k+1)^{2}
\end{align*}$$
>The statement holds for $n=k+1$ given that the statement holds for $n=k$.
>Therefore, by the principal of mathematical induction, the statement holds for all $n\in\mathbf{N}$.
>$$\begin{align*}
\ \tag*{$\blacksquare$}
\end{align*}$$





