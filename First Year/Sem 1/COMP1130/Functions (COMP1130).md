>[!def]
>A function is defined by:
>- a set $A$, called the *domain*
>- a set $B$, called the *codomain*
>- an assignment from each element of $A$ to one element of $B$.
>
>A function named $f$ is formally defined by writing $f :: A\rightarrow B$.


A function with a finite domain may be completely defined by specifying outputs for each valid input.
$$\begin{align*}
f :: \mathbf{B}\rightarrow \mathbf{Z}\\
f(False) &= -1\\
f(True) &= 3
\end{align*}$$
For functions with infinite domain, the function must be explained more generally.
$$\begin{align*}
\text{minus}::\mathbf{Z}\rightarrow\mathbf{Z}, \text{minus}(x) &= -x\\
\text{isPos}::\mathbf{Z}\rightarrow\mathbf{B}, \text{isPos}(x) &= \cases{
\text{True if }y>0\\
\text{False if }y\le 0}
\end{align*}$$
>[!remark]
>$x$ and $y$ here are referring to mathematical variables in their respective domains and codomains, but are very different to the concept of variables in programming. For instance, in programming, a variable may be incremented by stating `x = x + 1`, while in mathematics, the equation $x = x+1$ is nonsensical.

# Polymorphic Functions
>[!def]
>A function is polymorphic if it can be defined for many different sets at once.
>E.g., the identity function `id :: A -> A`, `id(a) = a`, or a constant function `constantzero :: B -> Z`, `constantzero(b) = 0`. Functions such as `f(x) = -x` may also be called polymorphic, but only over sets where the operations are defined (i.e., sets where `-x` has some meaning).

>[!remark] Left/right projection and injection are polymorphic functions!
>```
>leftproj :: A x B -> A, leftproj(a,b) = a
>```


# Composition
>[!def]
>If we have two functions $f : A \longrightarrow B$ and $g : B \longrightarrow C$, then we may define a new function $g \circ f : A \longrightarrow C$, where $(g\circ f)(x) = g(f(x))$.

# Sets of Functions
>[!def]
>If we have two sets $A$ and $B$, then we can define the set $A \longrightarrow B$, the set of all functions from $A$ to $B$. One can think of the notation $f : A \longrightarrow B$ as being equivalent to saying that $f$ is in the set $A \longrightarrow B$.

The $\longrightarrow$ notation is defined using *right associativity*. I.e., $A\longrightarrow B\longrightarrow C = A\longrightarrow (B\longrightarrow C)$ is the set of functions from $A$ to the set of functions from $B\longrightarrow C$.

>[!remark]
>Suppose we have $f : A \longrightarrow B\longrightarrow C$. Then if we input an element $a\in A$, $f$ outputs a function $g : B \longrightarrow C$. If we now input an element $b\in B$, we get an element in $C$. So in all, we may think of $f$ as being a function with two inputs, in $A$ and $B$.

For example, the function that pairs two elements of sets $A$ and $B$ each will be defined as follows.
$$\begin{gather*}
f : A \longrightarrow B\longrightarrow A\times B\\
(f(a))(b) = (a,b)\text{, or}f(a,b) = (a,b)
\end{gather*}$$
