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
>with $(u_{1}, w_{1}) + (u_{2}, w_{2}) := (u_{1} + u_{2}, w_{1} + w_{2})$, and $\alpha(u, w) = (\alpha u, \alpha w)$.

>[!remark]
>If $Z$ is contained in $A$ and also contained in $B$, then it must be contained in $A\cap B$. Also, if $Z$ contains $A$ and contains $B$, then it must contain $A\cup B$. We call $A\cap B$ the *meet* and $A\cup B$ the *join*.
>
>Now take $Q(V) = \left\{W\subset V \mid W\text{ subspace}\right\}$.
>We can have the meet be $V\cap W$, so that any other subspace $U$ which is both in $V$ and $W$ must be in the meet.
>However, we cannot always have a join if defined as $V\cup W$, as this is not always a subspace. We can instead define the join to be $V+W$, and this in fact works.

>[!def]
>$T : V \longrightarrow W$, for vector spaces $V,W/F$ is a linear map if and only if:
>- $T(u+w) = T(u) + T(w)\quad\forall u,w\in V$
>- $T(\alpha\cdot v) = \alpha\cdot T(v)\quad\forall v\in V,\ \alpha\in F$.
> 
>>[!example]
>>$T_{A} : F^{n} \longrightarrow F^{m},\quad v\longmapsto Av,\ A\in M_{m\times n}(F)$.
>>$C'(\mathbb{R}) \longrightarrow C(\mathbb{R}),\quad f\longmapsto f'$.
>>$C[a,b] \longrightarrow \mathbb{R},\quad f\longmapsto \int_{a}^{b}f(x)dx$.
>>$F[x] \longrightarrow F,\quad p\longmapsto p(1)$.
>>$F\longrightarrow V,\quad \alpha\longmapsto \alpha v$.

>[!remark]
>If $T$ is linear, then $T(0_{V}) = T(0_{V}) + T(0_{V}) = 0_{W}$.

>[!def]
>The *kernel* of $T$ is $\ker(T) = \left\{v\in V \mid T(V)=0\right\}$, and the *image* of $T$ is $\text{im}(T) = \left\{w\in W \mid \exists v.T(v)=w\right\}$.


>[!theorem]
>$\text{im}(T)$ and $\ker(T)$ are subspaces.
>
>>[!proof]
>>This can be shown simply through demonstarting all subspace axioms in both cases/

>[!theorem]
>A linear map is injective if and only if $\ker(T) = \left\{0\right\}$, and is surjective if and only if $\text{im}(T) = W$.
>
>>[!proof]
>>If $\ker(T)=\left\{0\right\}$, then only zero may map to zero.
>>Now suppose that $T(v)=T(u)$.
>>$$\begin{align*}
>>T(v)-T(u)&= 0\\
>>T(v-u)&= 0\\
>>v-u&\in\ker(T)\\
>>v-u &= 0\\
>>v &= u.
>>\end{align*}$$
>>So then to show that $T$ is injective we need only show that $\ker(T)=\left\{0\right\}$.
>>The other parts of this proof are more simple.

>[!theorem]
>Suppose $V,W$ v.s. $/F$, and that $B = \left\{v_{1},\cdots,v_{n}\right\}\subset V$ is a finite basis.
>$$\begin{align*}
>f &: B \longrightarrow V\\
>f(v_{i}) &= w_{i}
>\end{align*}$$
>Then there exists a unique linear map $T : V \longrightarrow W$ such that $T|_{B} = f$.