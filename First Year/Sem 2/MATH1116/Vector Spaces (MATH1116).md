>[!def]
>$V$ is a vector space over a field $F$ with addition, multiplication and respective identities (written $V\text{ v.s. } / (F,+,\cdot,0,1)$) if:
>- $V$ is nonempty
>- $+ : V\times V \longrightarrow V\quad (v,w) \longmapsto v+w$
>- $\cdot : F\times V \longrightarrow V\quad (\alpha,v) \longmapsto a\cdot v$
>- Addition of vectors is commutative
>- Addition of vectors is associative
>- $(\alpha\cdot \beta) \cdot v = \alpha\cdot(\beta\cdot v),\quad\alpha,\beta\in F,\ v\in V$
>- $(\alpha+\beta)\cdot v = \alpha\cdot v + \beta\cdot v$
>- $\alpha\cdot(u+v) = \alpha\cdot u + \alpha\cdot v$
>- $\exists 0\in V$ such that $v+0=v\quad\forall v\in V$
>- $\forall v\in V,\quad \exists w,\ v+w=0$
>- $1\cdot v = v\quad\forall v\in V$
> 
>>[!example]
>>$F^{n}$ is a vector space when $F$ is a field.
>>We define addition to be coordinate-wise, and scalar multiplication to be scaling of all coordinates.
>>$$\begin{align*}
>>F^{n} = \left\{(a_{1},\cdots,a_{n}) \mid a_{i}\in F\right\}\\
>>(a_{1},\cdots,a_{n})+(b_{1},\cdots,b_{n}) &= (a_{1}+b_{1},\cdots,a_{n}+b_{n})\\
>>\vdots
> \end{align*}$$
> 
>>[!example]
>>$F[x]$, the set of all polynomials over $F$ with the symbol $x$ is a vector space.
> 
>>[!example]
>>$M_{m\times n}(F)$, the set of all $m\times n$ matrices over $F$ is a vector space.
> 
>>[!example]
>>If $X$ is a set, and $F$ is a field, then $F^{X} = \left\{\text{functions }X\longrightarrow F\right\}$ is a vector space.
>>If we have $f,g\in F^{X}$, then we can define:
>>- $(f+g)(x) := f(x) + g(x)$
>>- $(c\cdot f)(x) := c\cdot(f(x))$
>>
>>This forms a vector space.
> 
> 
>>[!example]
>>Take a set $X$, and a vector space $V/ F$.
>>Then $V^{X}$ is the set of all functions $X \longrightarrow V$.
>>$V$ is still a field, so we can define a vector space the same as previously.

>[!def]
>A *subspace* of a vector space $V$ is a subset $W$ that is a vector space in its own right, using the same operations as $V$.
>We can prove $W$ is a subspace of $V$ by showing that:
>- $W$ is closed under addition
>- $W$ is closed under scalar multiplication
>- $0$ is in $W$

>[!def]
>The *spanning set* $Y\subset V$ if,
>$$\begin{align*}
>\forall v\in V&\quad \exists n,\\
>a_{1},a_{2},\cdots,a_{n}\in F&,\ v_{1},v_{2},\cdots,v_{n}\in Y\\ v=a_{1}v_{1}+&\cdots+a_{n}v_{n}
>\end{align*}$$
>If there is a finite spanning set, then we say that $V$ is *finitely generated*.

>[!def]
>Vectors $v_{1}\cdots,v_{n}\in V$ with $v_{1}\ne 0,\cdots,v_{n}\ne 0$ are *independent* if,
>$$\begin{align*}
>\alpha_{1}v_{1}+\cdots+\alpha_{n}v_{n}=0 \Rightarrow \alpha_{1}=\cdots=\alpha_{n}=0.
>\end{align*}$$

>[!def]
>A *basis* of $V$ is a spanning and independent set of vectors in $V$.
> 
>>[!remark]
>>If $B = \left\{v_{1},\cdots,v_{n}\right\}$ is a basis, then,
>>$$\begin{align*}
>>\forall v\in V&\quad \exists! a_{1},\cdots,a_{n}\quad s.t.\\
>>v &= a_{1}v_{1}+ \cdots+a_{n}v_{n}
>>\end{align*}$$
> 

>[!theorem]
>If $V\ v.s. / F$, $X\subset V$ is independent and finite, and $Y$ is a finite spanning set, then $|X|\le|Y|$.
>I.e., an independent set will always have less than or an equal number of elements than a spanning set.
>
>>[!corollary]
>>If $V$ is finitely generated, then any two bases of $V$ have the same number of elements. We define this number to be the dimension of the vector space.
>>$$\begin{align*}
>>\dim(V) &= |B|,\quad B\text{ basis of }V.
>>\end{align*}$$
>
>>[!corollary]
>>If $W$ is a subspace of $V$, and $\dim(W) = \dim(V)$, then $W=V$.

>[!remark]
>$\mathbb{C}$ is a vector space over $\mathbb{R}$. We have a $\mathbb{R}$-basis of $\mathbb{C}$, $\left\{1, i\right\}$, so then $\dim_\mathbb{R}(\mathbb{C}) = 2$.

>[!theorem]
>If $V$ is finite dimensional and a vector space over $F$, $W\subset V$ is a subspace and $B\subset W$ is a basis, then $B$ can be extended to a basis $C$ of $V$.
>>[!proof]
>>We prove this by induction on $\dim(V)-\dim(W)=k$. If $k=0$ we are done.
>>Now if $k\ge 1$, $W$ is a strict subset of $V$, so there is some $v\in V\setminus W$. We add this to our set.
>>$$\begin{align*}
>>W\subsetneq \text{span}_{F}(W\cup \left\{v\right\})\subseteq V.
>>\end{align*}$$
>>Now we have a new basis with an extra element, so the dimension is increased. So $k$ is decreased and we may apply induction.

>[!theorem]
>Let $V$ be a vector space, and $U,W\subset V$ be subspaces.
>Then $U+W := \left\{u+w \mid u\in U,w\in W\right\}$.
>Then $U+W$ is a subspace of $V$.
>
>>[!proof]
>>We can simply show that all $u+w$ follow the subspace axioms.

>[!theorem]
>$\dim(U+W) = \dim(U) + \dim(W) - \dim(U\cap W)$.
>
>>[!proof]
>>We first have some basis $B$ of $W\cap U$. We may extend this to a new basis $C$ of $W$, and a new basis $D$ of $U$.
>>Now let $E = C\cup D$. We can show that $E$ is a basis of $U+W$.
>>From here the proof is clear.

>[!def]
>If $U\cap W = \left\{0\right\}$ we say that $U+W$ is a *direct sum*, denoted $U\oplus W$.
>
>We can also construct the direct sum of any two spaces.
>$$\begin{align*}
>U\oplus W := \left\{(u,w) \mid u\in U,w\in W\right\},
>\end{align*}$$
>with $(u_{1}, w_{1}) + (u_{2}, w_{2}) := $