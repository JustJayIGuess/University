>[!def]
>A set is roughly a collection of elements where elements:
>- are in no particular order, and
>- only appear once.

# Finite Sets
Some sets have only finitely many elements, and so can be listed exhaustively.
$$\begin{align*}
\{*\}\tag{singleton}\\
\{\text{False}, \text{True}\}\tag*{($\text{booleans}, \mathbf{B}$)}
\end{align*}$$
Often, elements of a set can be implied using dots.
$$\begin{align*}
\{1,2,3,\dots,100\}\tag{the numbers from 1 to 100}
\end{align*}$$
# Infinite Sets
Many sets are infinite in size. Some notables sets are shown below.
$$\begin{align*}
\mathbf{N} = \{0,1,2,\dots\}\tag{the natural numbers}\\
\mathbf{Z} = \{..., -2, -1, 0, 1, 2, ...\}\tag{the integers}\\
\mathbf{R}\tag{the real numbers}\\
\text{`The strings'}\tag{all finite lists of characters}
\end{align*}$$
# Set Operations
## Set Products
>[!def]
>Given sets $S_{1}, S_{2}, ..., S_{n}$, a new set $T=S_{1}\times S_{2}\times ...\times S_{n}$ may be formed where every $n$-tuple $(s_{1}, s_{2},...,s_{n})$ is an element of $T$, and $s_{1}\in S_{1}, s_{2}\in S_{2}, ..., s_{n}\in S_{n}$.

An example of a combination of sets is given below.
$$\begin{align*}
&\mathbf{B}\times \{\text{Red}, \text{Green}, \text{Blue}\}\\
&= \{(\text{False}, \text{Red}), (\text{False}, \text{Green}), (\text{False}, \text{Blue}), (\text{True}, \text{Red}), (\text{True}, \text{Green}), (\text{True}, \text{Blue})\}
\end{align*}$$
## Set Addition
>[!def]
>Given sets $S_{1}, S_{2}, ..., S_{n}$, a new set $T=S_{1}+S_{2}+\dots+S_{n}$ may be formed where every element $s$ from $S_{i}$ is an element of $T$ within a tuple, along with a tag designating which set it came from.

The use of tags ensures that the two sets remain disjoint, and the names of the tags are arbitrary, as long as they in some way indicate the origin set of that element.
>[!note]
>This is not the same as a set union. For instance, consider the set $S = \mathbf{B}+\mathbf{B}$.
>$$\begin{align*}S=\{(\text{False},\text{Left}), (\text{True},\text{Left}), (\text{False},\text{Right}), (\text{True},\text{Right})\}
\end{align*}$$
>On the other hand, the set union $S = \mathbf{B}\cup\mathbf{B}$ would be,
>$$\begin{align*}
S &= \{\text{False}, \text{True}\}.
\end{align*}$$


