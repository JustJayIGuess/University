# Continuity in Limits
Many physically interesting mathematical models are continuous, so analysis of these functions is especially important.

>[!def]
>$f$ is continuous at $a$ if,
>$$\begin{align*}\lim_{x \rightarrow a}f(x)=f(a)\end{align*}$$
>Note that this actually imposes three conditions:
>- the limit exists
>- $f$ is defined at $a$
>- equality

>[!example]
>Suppose we have the following function.
>![[Limits 2024-03-08 11.13.58.excalidraw|300]]
>It is continuous everywhere except $0$.

>[!def]
>$f$ is continuous on $[a,b]$ if $f$ is continuous at $c$ for all $c\in[a,b]$.

>[!def]
>$f$ is *uniformly continuous* on an interval $I$ if $\forall \epsilon>0, \exists \delta$ such that $0<|x-y|<\delta \Rightarrow |f(x)-f(y)|<\epsilon$.
>Note that in showing continuity, we pick an $x,\epsilon$ and find a $\delta$, while in showing uniform continuity, we pick $\epsilon$ and find a $\delta$.
## Theorems of Continuity
>[!theorem]
>Suppose $f,g$ are continuous at $a$.
>We have the following:
>- $f+g$ is continuous at $a$
>- $fg$ is continuous at $a$
>- $\frac{1}{g}$ is continuous at $a$ if $g(a)\ne 0$

>[!cor]
>Rational functions $\left(\frac{p}{q}\text{ for polynomials }p,q\right)$ are continuous where defined.

>[!theorem]
>Suppose $g$ is continuous at $a$, and $f$ is continuous at $g(a)$.
>Then $f\circ g$ is continuous.
>I.e.,
>$$\begin{align*}\lim_{x \rightarrow a}(f\circ g)(x) &= f(g(x))\end{align*}$$
---
>[!proof]
>We must show that for any $\epsilon_{0}>0$, we can find $\delta_{0}>0$ that controls $f(g(x))$, and for that $\delta_{0}$, we can find $\gamma_{0}>0$ that controls $g(x)$.
> $$\begin{gather*}
> \forall \epsilon>0,\exists \delta>0\text{ s.t.},\\
> 0<|x-g(a)|<\delta \Rightarrow |(f\circ g)(x)-f(g(a))|<\epsilon.\\
> \text{The above regards the continuity of }f.\\
> \\
> \forall \delta>0,\exists \gamma>0\text{ s.t.},\\
> 0<|x-a|<\gamma \Rightarrow |g(x)-g(a)|<\delta\\
> \text{The above regards the continuity of }g.
> \end{gather*}$$
> Fix $\epsilon_{0}>0$. Choose $\delta_{0}$ as allowed by the continuity of $f$, and for this $\delta_{0}$ choose a $\gamma_{0}$ as allowed by the continuity of $g$.
> Then,
> $$\begin{align*}
> |(f\circ g)(x) - f(g(a))|<\epsilon_{0}\tag*{$\blacksquare$}
> \end{align*}$$
> Therefore a composition of functions that are continuous at a point is continuous.

Note that the following theorems strictly requires a closed interval. These will also use the axioms of the existence of least upper bounds in $\mathbb{R}$ ([[Least Upper Bounds]]).

>[!theorem]
>If $f$ is continuous on $[a,b]$, then $f$ is uniformly continuous on $[a,b]$.

>[!proof]
>TODO

