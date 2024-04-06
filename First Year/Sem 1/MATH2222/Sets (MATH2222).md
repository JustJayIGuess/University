>[!def]
>A set is a precisely defined collection of objects

# Standard Sets
>[!def]
>The *natural numbers*, denoted $\mathbf{N}$, is the set containing the positive integers (sometimes containing $0$ as well, depending on convention), i.e.,
>$$\begin{align*}
\mathbf{N} &= \{0, 1, 2, 3, 4, \cdots\}.
\end{align*}$$

>[!def]
>The *integers*, denoted $\mathbf{Z}$ for German 'zahlen', is the set containing all integers, i.e.,
>$$\begin{align*}
\mathbf{Z} &= \{\cdots, -3, -2, -1, 0, 1, 2, 3, \cdots\}.
\end{align*}$$

>[!def]
>The *rationals*, denoted $\mathbf{Q}$, is the set containing all numbers that can be expressed as a ratio of integers, i.e.,
>$$\begin{align*}
\mathbf{Q} &= \left\{\frac{a}{b}:a,b\in \mathbf{Z}, b\ne 0\right\}.
\end{align*}$$

>[!def]
>The *real numbers*, denoted $\mathbf{R}$, is the set containing all numbers that can be expressed in an infinite decimal expansion, i.e. both rational and irrational numbers.

>[!def]
>The *complex numbers*, denoted $\mathbf{C}$, is equivalent to $\mathbf{R}$, adjoined with the constant $i$, which is the constant with the property that $i^{2} = -1$.
>$$\begin{align*}
\mathbf{C} &= \mathbf{R}[i]
\end{align*}$$


>Note that $\mathbf{N}\subseteq\mathbf{Z}\subseteq\mathbf{Q}\subseteq\mathbf{R}\subseteq\mathbf{C}$.

# Containment and Equality
>[!def]
>A is *contained in* B ($A\subseteq B$) if and only if for every element in A, there exists that same element in B.

>[!def]
>Two sets are considered equal if and only if they both contain each other ($A\subseteq B$ and $B\subseteq A$).

# Set Builder Notation
Sets may be defined using the following shorthand,
$$\begin{align*}
P &= \{p\in\mathbf{N}:p\text{ is prime}\},
\end{align*}$$
and is read, 'P is equal to the set of all elements p in N such that p is prime.'

# The Empty Set
The empty set is denoted $\emptyset$.

# Set Operations
## Union
>[!def]
>The *union* of A and B is defined as,
>$$\begin{align*}
A\cup B &= \left\{x \mid x\in A\text{ or }x\in B\right\},
\end{align*}$$
>i.e., the set of all elements contained in either A or B, inclusive.
## Intersection
>[!def]
>The *intersection* of A and B is defined as,
>$$\begin{align*}
A\cap B &= \left\{x \mid x\in A\text{ and }x\in B\right\}.
\end{align*}$$
>i.e., the set of all elements contained in both A and B.
## Complement
>[!def]
>The *complement* of A, if considered in the context of a **universe set** U, is defined as,
>$$\begin{align*}
A^{c} &= \left\{x\in U \mid x\notin A\right\},
\end{align*}$$
>i.e., the set of all elements in the universe set that is not contained in the set A.
## Power Set
>[!def] 
>The *power set* of A (denoted $\mathcal{P}(A)$) is defined as,
>$$\begin{align*}
\mathcal{P}(A) &= \left\{B \mid B\subseteq A\right\},
\end{align*}$$
>i.e., the set of all subsets of A, e.g.,
>$$\begin{align*}
A &= \left\{1, 2, 3\right\}\\
\mathcal{P}(A)&= \left\{\left\{1, 2, 3\right\}, \left\{1, 2\right\}\left\{1, 3\right\}, \left\{2, 3\right\}, \left\{1\right\}, \left\{2\right\}, \left\{3\right\}, \varnothing\right\}.
\end{align*}$$

>[!proof]
>Prove that, if the set A has $k$ elements, then $\mathcal{P}(A)$ has $2^{k}$ elements.
## Cartesian Product
>[!def]
>The *cartesian product* of sets A and B is defined as,
>$$\begin{align*}
A\times B &= \left\{(a, b) \mid a\in A, b\in B\right\}.\\
\end{align*}$$

See further info in [[Sets (COMP1130)#Set Products|COMP1130 Set Products]].
# Set Properties
## Cardinality
>[!def]
>The *cardinality* of a set A, denoted $\lvert A\rvert$, is the number of elements contained within it.
## Disjoint
>[!def]
>Sets A and B are *disjoint* if $A\cap B = \varnothing$.


# Russel's Paradox
Consider building the set of all sets that are not elements of themselves, i.e.,
$$\begin{align*}
R &= \left\{A \mid A\notin A\right\}.
\end{align*}$$
Now ask the questions, *is R in this set?*
If $R$ is in the set, then it contains itself, however this means that it must not be in the set. Conversely, if R is not in the set, then it does not contain itself, so R must be in the set.
This is a contradiction, and is addressed by *not allowing the construction of sets of all objects with a property.* Instead, one may only begin with some universe set, and from there give constraints to filter out elements with a particular property.
