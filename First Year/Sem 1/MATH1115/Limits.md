# $\epsilon$-closeness
>[!def]
>We say that $f(x)$ is $\epsilon$-close to $b$ at $a$ if,
>$$\begin{align*}0<|x-a|<\delta \Rightarrow |f(x)-b|<\epsilon\end{align*}$$

>[!example]
>Show that $f(x)=x^{2}$ is $\frac{1}{2}$-close to 9 at 3.
>We must show that $0<|x-3|<\delta \Rightarrow |x^{2}-9|< \frac{1}{2}$.
# Definition of the Limit

>[!def]
>We define a limit as follows.

$$\begin{gather*}
\lim_{x \rightarrow a}f(x) = b\text{ if,}\\
\forall \epsilon >0,\ \exists \delta>0 \text{ s.t.,}\\
0<|x-a|<\delta \Rightarrow |f(x)-b|<\epsilon
\end{gather*}$$
# Limits of Discontinuous Functions
Consider the following discontinuous function,
$$\begin{align*}
g(x) &= \cases{x^{2}\text{ if }x\in \mathbb{Q} \\ 0\text{ if }x\notin \mathbb{Q}}.
\end{align*}$$
What is,
$$\lim_{x \rightarrow 0} g(x)?$$
Intuitively, we can see that it should approach 0.
>[!proof]
> Fix $\epsilon>0$.
> Suppose that $0 < |x| < \delta = \sqrt{\epsilon}$.
> Then,
> $$\begin{align*}
> |x|&<\sqrt{\epsilon}\\
> x^{2}&<\epsilon\\
> 0<x^{2}&<\epsilon
> \end{align*}$$
> Therefore, both branches of $g(x)$ are bounded by epsilon; $g(x)<\epsilon$ for $\delta = \sqrt{\epsilon}$. The limit exists.

# Limit Theorems
>[!theorem]
>Suppose we have,
> $$\begin{align*}
> \lim_{x \rightarrow a}f(x) = b,\ \lim_{x \rightarrow a}g(x)=c
> \end{align*}$$
> Then we also have that,
> $$\begin{align*}
> \lim_{x \rightarrow a}(f+g)(x)&= b+c,\\
> \lim_{x \rightarrow a}(fg)(x)&= bc,\\
> \lim_{x \rightarrow a} \frac{1}{f}(x)&= \frac{1}{b},\ b\ne 0.
> \end{align*}$$
> Note that **these do not apply in reverse**.
---

>[!proof]

First consider the statement about products.
First, fix $\epsilon>0$.
We already have that the limits for $f$ and $g$ exist.
$$\begin{align*}
|f(x)g(x)-bc| &= |f(x)g(x) + f(x)c - f(x)c - bc|\\
&= \left|f(x)\left[g(x)-c\right]+c\left[f(x)-b\right]\right|\\
&\le |f(x)|\left|g(x)-c\right| + |c|\left|f(x)-b\right|\\
\end{align*}$$
To make these products small, we can bound one factor from above and make the other factor sufficiently small. We will make each term $<\frac{\epsilon}{2}$.
We have the following already,
$$\begin{align*}
\lim_{x \rightarrow a}f(x)=b \Rightarrow \exists \delta_{1}\text{ such that }|f(x)-b|<\left|\frac{\epsilon}{2c}\right|=\epsilon_{1}
\end{align*}$$
This bound will ensure that $|c||f(x)-b|<\frac{\epsilon}{2}$.
Note now that,
$$\begin{align*}
|f(x)-b|<\left|\frac{\epsilon}{2c}\right|\\
|f(x)|-|b|<\left|\frac{\epsilon}{2c}\right|\\
|f(x)|< \left|\frac{\epsilon}{2c}\right|+|b|
\end{align*}$$
We now also have that,
$$\begin{align*}
\exists \delta_{2},\ 0<|x-a|<\delta_{2}\\
\Rightarrow |g(x)-b|< \frac{\epsilon}{2(|b|+\left|\frac{\epsilon}{2c}\right|)}=\epsilon_{2}
\end{align*}$$
So, if we choose $\delta < \min(\delta_{1}, \delta_{2})$. TODO

>[!cor]
>Every polynomial has a limit at every point.

>[!lemma]
>$$\begin{align*}\lim_{x \rightarrow a}x&= a,\\\lim_{x \rightarrow a}b&= b\end{align*}$$
---
>[!proof] Proof of corollary.
>Note that,
>$$\begin{align*}
\lim_{x \rightarrow 2}\left(3x^{2}-1\right) &= \left(\lim_{x \rightarrow 2} 3\right)\left(\lim_{x \rightarrow 2}x\right)^{2}-\left(\lim_{x \rightarrow 2}1\right)\\
&= 3(2)^{2}-1
\end{align*}$$
[[Continuity]]
### Intermediate Value Theorem
>[!theorem]
>Suppose that $f$ is continuous on $[a,b]$, and that $f(a)<f(b)$. Then for any $c\in(f(a),f(b))$ there is some $x\in(a,b)$ such that $f(x)=c$.
>Note that this clearly doesn't apply for some discontinuous functions.

### Extreme Value Theorem
>[!theorem]
>Suppose $f$ is continuous on $[a,b]$. Then there must exist $c\in[a,b]$ such that for all $x\in[a,b]$, $f(x)\le f(c)$. This is read "$f$ attains a maximum on $[a,b]$".

>[!lemma]
>An upper bound exists for this $f(x)$.

>[!proof]
>Consider the set $A = \left\{x \mid a\le x\le b,\ f\text{ bounded above on }[a,x]\right\}$.
>This is non-empty, as $[a,a]$ must be in the set.
>It is also bounded, as $b+23479283374$ (arbitrary number) bounds the set.
>Therefore there must be $\alpha = \sup(A)$.
>Note that if we can show that $\alpha = b$, then it would follow that $f$ is bounded on $[a,b]$.
>
>Suppose for the sake of contradiction that $\alpha<b$.
>As $f$ is continuous, for any $\epsilon>0,\ \exists\delta$ such that $0<|x-\alpha|<\delta$ implies that $|f(x)-f(\alpha)|<\epsilon$.
>So then if $x\in[a,\alpha+\delta)$, then $f(x)$ is bounded. But this means that our original $\alpha$ was not an upper bound!
>Therefore by contradiction, $\alpha=b$ is the least upper bound.
>
>So then $f$ is bounded on $[a,b)$. If $N$ is an upper bound for $f$ on $[a,b)$, then $\max(N,f(b))$ is an upper bound on $[a,b]$.

>[!proof]

Consider $A = \left\{f(x) \mid x\in[a,b]\right\}$, so $A$ is the range of $f$.
$A$ is non-empty as the function is defined for $a$, for instance.
We also know that $A$ is bounded, by the previous lemma.
**We now want to show that this bound is some $f(c)=\alpha$ on the interval.**

Suppose for the sake of contradiction that there is no $c$.
Now define $g(x) = \frac{1}{\alpha-f(x)}$, which is continuous on $[a,b]$ as $f(x)\ne \alpha$.
Since $\alpha$ is LUB, then we have that $\forall \epsilon>0\exists x\in[a,b]$ such that $\alpha-f(x)<\epsilon$.
This means that for all $n\in\mathbb{N}$, we can find an $x$ that brings $f(x)$ close enough to $\alpha$ so that $g(x)>n$, But this means that $g$ is not continuous!

Then by 
### Applications
Fixing a wobbly table!
Somewhere there's a place with the same temp and pressure as the place on the opposite side of the world!
*Showing a polynomial has roots!*
>[!proof]
>Suppose that $q(x)=x^{2n+1}+\cdots$
>Then as $x\longrightarrow -\infty$, $q\longrightarrow -\infty$, and as $x\longrightarrow \infty$, $q\longrightarrow \infty$. So there must be some closed interval $[-1,1]$. The intermediate value theorems says that there must then be some point where the polynomial passes through any given value, including 0.

### Proving these Theorems
Note that all of the first 12 axioms hold for $\mathbb{R}$ and for $\mathbb{Q}$. So these cannot be proven from axioms, as this proof would then apply to discontinuous functions in $\mathbb{Q}$.