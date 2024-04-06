Cardinality addresses the question of *how big is a set?*
To do this, we will use some properties of functions.

# Surjective Functions
>[!def]
>Consider two sets $A$ and $B$. Recall that for a function $f : A \longrightarrow B$, if $E\in A$, then the **image of $E$ under $f$** is the set,
>$$\begin{align*}f(E) &= \left\{f(x) \mid x\in E\right\}\end{align*}$$
>If $f(A) = B$, we say that $f$ is *surjective* (or *onto*). I.e., for every $b\in B$, there is at least one element $a\in A$ such that $f(a) = b$; every point in $B$ is mapped onto by some element in the domain.
>A subtlety of this is that we must know the domain and codomain of $f$.
>For example, $f : \mathbb{R} \longrightarrow \mathbb{R}$, $f(x) = x+2$ is **surjective**, but $g : \mathbb{N} \longrightarrow \mathbb{N}$, $g(x) = x+2$ is **not surjective**.

# Injective Functions
>[!def]
>If we have a set $F\subseteq B$, then $f^{-1}(F) = \left\{a\in A \mid f(a)\in F\right\}$ is the preimage, or inverse image, of $F$ under $f$. Note that $F$ could be a single point, in which case $f^{-1}(F)$ would be the set of all points in the domain that map to the particular point in $F$ under $f$.
>
>If, for every $y\in B$, $f_{1}(y)$ consists of at most one point, then we say that $f$ is *injective* (or *one-to-one*).
>
>Equivalently, this means that for any $x_{1}, x_{2}\in A$ with $x_{1}\ne x_{2}$, $f(x_{1})\ne f(x_{2})$. By the contrapositive, and **for particular use in proofs**, it once again equivalently means that if $f(x_{1}) = f(x_{2})$ then $x_{1} = x_{2}$.

# Bijective Functions
>[!def]
>We have that a function $f : A \longrightarrow B$ is *bijective* if $f$ is both **surjective** and **injective**. Some people may say that $f$ is a *one-to-one correspondence* from $A$ onto $B$, however one should be careful not to confuse this with a one-to-one/injective function.
>
>This implies that for every point $b\in B$, there is exactly one element $a\in A$ such that $f(a) = b$. Equivalently, $f(x)=y$ has a **unique solution**.

Consider the following examples.

>[!example] 
>Let $2\mathbb{Z}$ denote the even integers.
>Give an example of an injection $f$ from the even integers to the integers.
>
>$f : 2\mathbb{Z} \longrightarrow \mathbb{z}$.
>Consider $f(x) = x$. This is an injection, as each $x$ maps to a unique $f(x)$.
>
>Give an example of a surjection from the integers to the evens.
>
>$g : \mathbb{Z} \longrightarrow 2\mathbb{Z}$.
>Consider $g(x) = 2x$. $g$ is surjective as every even integer will be hit by this mapping. Is $g$ injective however?
>Suppose that $g(y) = g(z)$. Then,
>$$\begin{align*}2y &= 2z \\ y &= z.\end{align*}$$
>As $g(y) = g(z) \Rightarrow y = z$, then $g$ is also injective. Therefore $g$ is a **bijection**. Note that this means that the set of all integers and the set of all even integers are of "equal size" (or more precisely, equal cardinality).
# Cardinality of Sets
>[!def]
>For some positive integer $n$, let the set $J_{n}$ be,
>$$\begin{align*}J_{n} &= \left\{1, 2, 3, ..., n\right\},\ J_{0} =\varnothing.\end{align*}$$
>A set $A$ is *finite* if there is a bijection $f$ from $A$ to a set $J_{n}$ as defined above. Otherwise, it is *infinite*.
>Suppose also the set $J$ where,
>$$\begin{align*}J &= \left\{1,2,3,...\right\}\end{align*}$$
>The set $A$ is *countably infinite* if there is a bijection from $A$ to this set $J$. If this doesn't exist, then $A$ is *uncountably infinite*.

>[!remark]
>When you count a finite set $B$, you are producing a bijection $f : B \longrightarrow J_{n}$!
>The same is also true for a countably infinite set $B$!

## Finite Sets
>[!theorem]
>Let $m$ and $n$ be positive integers. If there exist bijections $f : B \longrightarrow J_{n}$ and $g : B \longrightarrow J_{m}$, then $m=n$, i.e., a set may only have a bijection to one of $J_{n}$.
>The *cardinality* of a finite set is this value $n$.

## Countable Sets
Some examples of countable sets are the positive integers, as one may for the bijection $f(x) = x$ from $\mathbb{N}\longrightarrow J$.
More interestingly, the set of all integers is also countable!

We may form a bijection from the integers to $J$ by ordering the integers as $\left\{0, 1, -1, 2, -2, ...\right\}$, at which point it is trivial that there is a bijection to $J$.

Consider the set $\mathbb{Z}^{2}$. What about $J^{2}$? What about $\mathbb{Q}$.
## Uncountable Sets
One might ask if there exists any sets which are uncountable. I.e., are there sets which are infinite but cannot be put into a one-to-one correspondence onto $\left\{0,1,2,...\right\}$.

>[!example]

$$\begin{align*}
\text{let }X\text{ denote the set of all binary, countable sequences.}\\
X &= \left\{f : \left\{1,2,3,...\right\} \longrightarrow \left\{0,1\right\}\right\}
\end{align*}$$
>[!theorem]
>The set $X$ is uncountable. I.e., there is no bijection $\pi : \left\{1,2,3,...\right\} \longrightarrow X$.

>[!proof]
>We will show that if $\pi$ is a function, then $\pi$ is **not** surjective.
>Suppose that $pi : \left\{1,2,3,...\right\} \longrightarrow X$.
>E.g., 
>$$\begin{align*}\pi(1) &= \left\{0,1,0,1,1,0,1,...\right\}\\\pi(2) &= \left\{0,1,1,1,0,0,1,...\right\}\\\pi(2) &= \left\{0,0,1,0,0,0,0,...\right\}\\\pi(2) &= \left\{0,1,0,0,0,0,1,...\right\}\\\end{align*}$$
>We claim that there is some binary sequence $x\in X$ such that $x\notin \text{image}(\pi)$.
>We begin constructing $x$ to have its first element to be different to the first entry of $\pi(1)$, then have its second element be different to $\pi(2)$'s second element, and in general, have its $k^{th}$ entry be different to the $k^{th}$ entry of $\pi(k)$. This guarantees that $x$ is different to all $\text{image}(\pi)$, so $x\notin \text{image}(\pi)$.
>Therefore $\pi$ is not a surjection, and so is not a bijection either.
>$$\tag*{$\blacksquare$}$$

The following sets are also uncountable:
- $\mathbb{R}$
- The interval $(0,1)$
- Cantor's set

>[!remark]
>The same diagonal argument by cantor also proves the following theorem.

>[!theorem]
>If $A$ is a set, and $\mathcal{P}(A) = \left\{B \mid B\subset A\right\}$, then there is no surjective function $\pi : A \longrightarrow \mathcal{P}(A)$.

This theorem means that one can always continue taking power sets of $\mathbb{R}$ to construct new sets with increasing cardinality, i.e., which has no bijection to the prior sets.

>[!example]
>Prove that the set of all algebraic sets is countable.

>[!theorem] The Continuum Hypothesis
>There is no "in-between" set where $\mathbb{N}\subseteq A \subseteq \mathbb{R}$.
>Note that this continuum hypothesis has been proven by Godel to be "consistent" with the other axioms of set theory, i.e., it cannot be disproven but is also not necessarily proven.
>It was also then shown by Cohen that the negation of the continuum hypothesis is also consistent.
>All this means that the continuum hypothesis may be chosen to be true or not true, and contradictions will not arise.


## Equivalence Relations
$A$ having the same cardinality as $B$ is one example of an *equivalence relation*.
Note that:
- $A \sim A$ (reflexive)
- $A\sim B \Leftrightarrow B\sim A$ (symmetry)
- $A\sim B$ and $B\sim C \Rightarrow A\sim C$ (transitive)

>[!theorem]
>*The Schroeder-Bernstein Theorem*
>Let $A,B$ be sets. If there is an injective map from $f : A \longrightarrow B$ and there is an injective map $g : B \longrightarrow A$, then there is a (possibly completely different) bijection between $h : A \longrightarrow B$.
---
>[!example]
>Suppose we have $A=\mathbb{Q}_{>0}$, $B = \left\{1,2,3,...\right\}$.
>We have an injection $f : Q_{>0} \longrightarrow \left\{1,2,3,...\right\}$, with $\frac{p}{q} \longmapsto 2^{p}3^{q}$.
>We also have $g : \left\{1,2,3,...\right\} \longrightarrow \mathbb{Q}_{>0}$, with $g(x)=x$.
>By the Schroeder-Bernstein theorem, we have a bijection between $A$ and $B$.

## Invertibility of Sets
>[!def]
>Suppose that we have $f : A \longrightarrow B$. $f$ is invertible if there exists $g : B \longrightarrow A$ such that,
>- $f\circ g = id_{B} : B \longrightarrow B$
>	- i.e., $(f\circ g)(b)=b,\ \forall b\in B$,
>- $g\circ f = id_{A} : A\longrightarrow A$
>	- i.e., $(g\circ f)(a) = a,\ \forall a\in A$
>If this is the case, then $g$ is the *inverse* of $f$, and is usually written $f^{-1}$. Note that this is **not the same as the [[Functions (MATH2222)#Images and Inverse Images of Subsets|preimage]]**.
>Note that $f$ is invertible if and only if $f$ is a [[#Bijective Functions|bijection]].

>[!theorem]
>$f : A \longrightarrow B$ is invertible if and only if $f$ is bijective.
---
>[!proof]
>This may be proven by first showing that $f$ invertible $\Rightarrow f$ is bijective, then showing that $f$ is bijective $\Rightarrow f$ invertible.
>First, suppose that $f$ is invertible. Then there exists $f^{-1}$ such that,
>$$\begin{align*}f^{-1}\circ f &= id_{A} : A \longrightarrow A \\ f\circ f^{-1} &= id_{B} : B \longrightarrow B.\end{align*}$$
>To show that $f$ is injective, suppose the following,
>$$\begin{align*}f(x_{1}) &= f(x_{2}) \\ f^{-1}(f(x_{1})) &= f^{-1}(f(x_{2})) \\ x_{1} &= x_{2}.\end{align*}$$
>Therefore $f$ is injective.
>To show that $f$ is surjective, consider an arbitrary element $b\in B$. We have that,
>$$\begin{align*}f(f^{-1}(b)) &= b.\end{align*}$$
>We may take $a = f^{-1}(b)$ and see that $f(a) = b$. Therefore we have shown that any arbitrary element $b\in B$ has a value $a$ such that $f(a) = b$; $f$ is surjective.
>As $f$ is both injective and surjective, it must also be bijective.
>Now suppose that $f$ is bijective. $f$ is also therefore both injective and surjective. We must show that there exists a $g : B \longrightarrow A$ such that $f\circ g = id_{B}$ and $g\circ f = id_{A}$ to show that $f$ is invertible.
>TODO


# Injection, Surjection and Bijection under Composition
## Injection
>[!theorem]
>If $f : X \longrightarrow Y$ and $g : Y \longrightarrow Z$ are injective, then $g\circ f : X\longrightarrow Z$ is injective.
---
>[!proof]
>We may show that $g\circ f$ is injective by supposing we have,
>$$\begin{align*}(g\circ f)(x_{1})&= (g\circ f)(x_{2})\\g(f(x_{1})) &= g(f(x_{2})).\end{align*}$$
>We know that $g(y_{1})=g(y_{2})\Rightarrow y_{1}=y_{2}$ as $g$ is injective, so therefore have that,
>$$\begin{align*}f(x_{1}) &= f(x_{2}).\end{align*}$$
>As $f$ is also injective we now have that,
>$$\begin{align*}x_{1}&= x_{2}.\end{align*}$$
>Therefore $(g\circ f)(x_{1}) = (g\circ f)(x_{2})$ implies that $x_{1} = x_{2}$, so $g\circ f$ is injective.
>$$\ \tag*{$\blacksquare$}$$

## Surjection
>[!theorem]
>If $f : X \longrightarrow Y$ and $g : Y \longrightarrow Z$ are surjective, then $g\circ f : X \longrightarrow Z$ is surjective.
---
>[!proof]
>This may be proven by noticing that, as $f$ and $g$ are surjective, we have that,
>$$\begin{align}\forall y\in Y, \exists x\in X &\textrm{ such that }f(x)=y,\tag{1}\\\forall z\in Z, \exists y\in Y &\textrm{ such that }g(y)=z.\tag{2}\end{align}$$
>So to prove that $h$ is surjective, we must find some value $x\in X$ for each $z\in Z$ such that $h(x) = z$.
>Suppose we have any arbitrary $z_0\in Z$. Then by $(2)$, we have that.
>$$\exists y_0\in Y\textrm{ such that }g(y_0) = z_0.$$
>By $(1)$, we also know that,
>$$\exists x_0\in X\textrm{ such that }f(x_0) = y_0.$$
>Substituting this value for $y_0$, we have that,
>$$\begin{align*}\exists x_0\in X\textrm{ such that } g(f(x_0)) &= z_0\\(g\circ f)(x_0) &= z_0\\h(x_0) &= z_0.\end{align*}$$
>Therefore it has been proven that there is an element $x$ for any arbitrary element $z$ such that $h(x) = z$, so $h$ is surjective.
>$$\ \tag*{$\blacksquare$}$$

## Bijection
>[!theorem]
>If $f : X \longrightarrow Y$ and $g : Y \longrightarrow Z$ are bijections, then $g\circ f : X \longrightarrow Z$ is a bijection.
---
>[!proof]
>As $f$ and $g$ are bijections, they are each both injections and surjections. This implies, as proven previously, that $g\circ f$ is both an injection and surjection. This however means that $g\circ f$ is a bijection.
>$$\ \tag*{$\blacksquare$}$$

