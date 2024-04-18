>TODO Lec Catchup

# The Power Rule
>[!theorem]
>If $f(x) = x^n$, $f'(x) = nx^{n-1}$.
---
>[!proof]
>We will prove this by induction.
>**Base case.**
>We have as a base case that $\frac{d}{dx}(x^{1}) = x^{0}$
>**Inductive step.**
>$$\begin{align*}
\frac{d}{dx}(x^{k+1}) &= \frac{d}{dx}(x^{k}\cdot x)\\
&= x^{k} \frac{d}{dx}(x) + x \frac{d}{dx}(x^{k})\\
&= x^{k} + x\times kx^{k-1}\\
&= x^{k} + kx^{k}\\
&= (k+1)x^{k}\\
\ \tag*{$\blacksquare$}
\end{align*}$$

# The Chain Rule
>[!theorem]
>If $f$ is differentiable at $g(a)$, and $g$ is differentiable at $a$, then $(f\circ g)'(a) = f'(g(a))g'(a)$.
---
>[!proof]
>Do After
---
>[!corollary]
>Given that $\frac{d}{dx}(\sin(x)) = \cos(x)$, we have the following.
>$$\begin{align*}(\sin(x^{3}))' &= \cos(x^{3})\times3x^{2}\\
\frac{d}{dx}\left(\frac{f(x)}{g(x)}\right)&= \frac{d}{dx}\left(f(x)\times \frac{1}{g(x)}\right)\\
&= f(x) \frac{d}{dx}\left(\frac{1}{g(x)}\right) + \frac{f'(x)}{g(x)}\\
&= \frac{-f(x)g'(x)}{[g(x)]^{2}} + \frac{f'(x)g(x)}{[g(x)]^{2}}\\
&= \frac{f'(x)g(x)-f(x)g'(x)}{[g(x)]^{2}}
\end{align*}$$

# Local Suprema
>[!def]
>We define the following.
>$(x,f(x))$ is a *local maximum* if $\exists \delta>0\text{ s.t. }f(x)\ge f(y)\ \forall y\in(x-\delta, x+\delta)$.
>$(x,f(x))$ is a *local minimum* if $\exists \delta>0\text{ s.t. }f(x)\le f(y)\ \forall y\in (x-\delta, x+\delta)$.
---
>[!remark]
>These always occur at either places where $f'(x)=0$, or where $f'(x)$ is undefined (includes endpoints).

>[!theorem]
>If $x$ is an extreme point for $f$ and $f$ is differentiable at $x$, then $f'(x)=0$.
---
>[!proof]
>Suppose that $f$ is differentiable at $a$, for a local minimum $a$. We know the following limit must exist.
>$$\begin{align*}\lim_{h\longrightarrow 0}\frac{f(a+h)-f(a)}{h}\end{align*}$$
>We also know the following as $a$ is a local minimum.
>$$\begin{align*}f(a)&\le f(a+h)\text{ for small }h\end{align*}$$
>Then we know the following.
>$$\begin{align*}\lim_{h \longrightarrow 0^{+}}\frac{f(a+h)-f(a)}{h}\end{align*}$$
>This limit must exist and be non-negative, so $f'(a)\ge0$.
>By repeating this from the negative direction, we get that $f'(a)\ge 0$.
>The only way to satisfy both of these constraints is for $f'(a)$ to be $0$.
>$$\ \tag*{$\blacksquare$}$$

# Rolle's Theorem
>[!theorem]
>If $f$ is continuous on $[a,b]$ and differentiable on $(a,b)$, and $f(a)=f(b)$, then there exists some $c\in(a,b)$ such that $f'(c)=0$.
>![[Rolles Theorem.excalidraw]]
>Note that this is a special case of [[#The Mean Value Theorem]].
---
>[!proof]
>As $f$ is continuous, we know by the extreme value theorem that $f$ has some absolute maximum and absolute minimum on $[a,b]$.
>If either of these occur in $(a,b)$, then we are done by the previous theorem, as $f$ will be differentiable at that point. Therefore it will suffice to prove that there is an extremum somewhere in the interval.
>Note that if both extrema occur at endpoints, then we must have a constant function. In this case, we have that $f'(x)=0$ everywhere in $(a,b)$.
>In the other case, we have that one extremum is in $(a,b)$, and so at this point we have $f'(x_{0})=0$.
>$$\ \tag*{$\blacksquare$}$$
# The Mean Value Theorem
>[!theorem]
>The *mean value theorem* states that, if we have a function $f$ that is continuous on the open interval $[a,b]$ which is differentiable on the open interval $(a,b)$, there is some $c\in(a,b)$ such that,
>$$\begin{align*}f'(c) = \frac{f(b)-f(a)}{b-a}.\end{align*}$$
---
>[!proof]
>First, we define $h(x) = f(x)-k(x-a)$, for some $k$ that will make $h(a)=h(b)$. To do this, we take $k = \frac{f(b)-f(a)}{b-a}$.
>Note the following:
>$$\begin{align*}h(a) &= f(a) \\ h(x)&\text{ is continuous on }[a,b] \\ h(x)&\text{ is differentiable on }(a,b) \\ h(b) &= f(b)\end{align*}$$
>Now, by Rolle's theorem, there is some $c\in(a,b)$ such that $h'(c)=0$.
>However note that,
>$$\begin{align*}h'(x) &= f'(x) - k.\end{align*}$$
>So,
>$$\begin{align*}h'(c)=0&= f'(c)-k \\ f'(c)&= k \\ f'(c) &= \frac{f(b)-f(a)}{b-a}. \\ \ \tag*{$\blacksquare$}\end{align*}$$
