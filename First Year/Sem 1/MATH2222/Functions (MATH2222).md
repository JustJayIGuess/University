>[!def]
>A function $f$ from a source [[Sets (MATH2222)|set]] A, the **domain**, to a target set B, the **codomain**, is a rule that assigns an element $f(a)\in B$ to each $a\in A$. To denote this, we write,
>$$\begin{align*}f: A \rightarrow B\end{align*},$$
>or occasionally,
>$$\begin{align*}A \overset{f}{\longrightarrow}B.\end{align*}$$
>In terms of individual elements, we may also write that,
>$$\begin{align*}a \longmapsto f(a)\end{align*},$$
>which is read as '$a$ maps to $f(a)$'.

>[!remark]
>The domains and codomains of a function may distinguish them from each other; the following functions are **different functions**.
>$$\begin{align*}f(x) &= x^{2}+2\qquad f:\mathbf{Z}\longrightarrow \mathbf{Z}\\
f(x) &= x^{2}+2\qquad f:\mathbf{R}\longrightarrow \mathbf{R}\end{align*}$$

# Graphs
>[!def]
>The *graph* of a function $f : A \longrightarrow B$ is a subset of $A \times B$ defined as,
>$$\begin{align*}\text{Graph}(f) &= \left\{(a,f(a)) \mid a\in A\right\}\end{align*}$$

# Images and Inverse Images of Subsets
>[!def]
>We may consider a subset $S$ of the domain $A$ ($S\subseteq A$), and investigate the result of applying a function $f : A \longrightarrow B$ on this subdomain $S$. The resulting set, denoted $f(S)$, may be defined as follows.
>$$\begin{align*}
f(S) &= \left\{f(a) \mid a\in S\right\}
\end{align*}$$
>This set, $f(S)$, is called the *image* of $S$.

>[!def]
>Similarly, we may also consider the subset $T\subseteq B$, and investigate which elements of the domain $A$ map to this subset; i.e.,
>$$\begin{align*}
f^{-1}(T) &= \left\{a\in A \mid f(a)\in T\right\}.
\end{align*}$$
>This set, $f^{-1}(S)$, is called the *inverse image* of $T$.

>[!note]
>This notation, $f^{-1}$, is neither the inverse of the function $f$ nor is it the reciprocal. That is to say, $f^{-1}$ is not a function from $B \longrightarrow A$.


# Defining Functions
>[!def]
>Functions may be defined in multiple ways, as long as they are defined such that every possible element in the domain is precisely mapped to exactly one element in the codomain.

Consider the following.
$$\begin{align*}
f : \mathbf{R} \longrightarrow \mathbf{R},\quad f(x)=\cases{x+2,x\ge 0\\-\pi,\  \ \ \ x\le 0}
\end{align*}$$
In this case, it is not clear what value $f(x)$ should take on at $x=0$, as in the first case it appears to be $2$, and in the second it appears to be $\pi$. This function is therefore *not well defined*.
Now consider this example.
$$\begin{align*}
f : \mathbf{R} \longrightarrow \mathbf{R},\quad f(x)=\cases{x,x\ge 0\\-x,x\le 0}
\end{align*}$$
In this case, the function has only one possible output for all elements in the domain; it is *well defined*.
Functions may also be defined by listing all possible inputs and their respective mappings to outputs, or in English words, as long as every input in the domain has one valid output in the codomain.

# Function Operations
## Composition
>[!def]
>If $A \overset{f}{\longrightarrow} B$ is defined and $B \overset{g}{\longrightarrow}C$ is defined, ensuring that the codomain of $f$ and domain of $g$ are equivalent, then a function, $g$ *composed with* $f$, may be written as $g\circ f$. This new function can be thought of as applying $f$, then applying $g$, i.e.,
>$$\begin{align*}g\circ f(a) &= g(f(a)).\end{align*}$$

## Addition and Multiplication
>[!def]
>Consider the functions $f,g : A \longrightarrow \mathbf{R}$.
>We may now define the *addition* and *multiplication* of these two functions as follows.
>$$\begin{align*}
(f+g)(a) &= f(a) + g(a)\\
(fg)(a) &= f(a)\times g(a)
\end{align*}$$

