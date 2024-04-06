First consider that a matrix may be thought of as a function $T_{A} : \mathbb{R}^{n} \longrightarrow \mathbb{R}^{m}$.
$$\begin{align*}
T_{a}(\vec{x}) &= A\vec{x}
\end{align*}$$
For example,
$$\begin{gather*}
\begin{bmatrix}1 & 2 & 3\\
4 & 5 & 6\end{bmatrix}\\
\\
T_{A} : \mathbb{R}^{3} \longrightarrow \mathbb{R}^{2}
\\
T_{A}\left(\begin{bmatrix}x_{1}\\
x_{2}\\
x_{3}\end{bmatrix}\right) = \begin{bmatrix}x_{1} + 2x_{2} + 3x_{3}\\
4x_{1}+5x_{2}+6x_{3}\end{bmatrix}
\end{gather*}$$
Now consider one matrix $A$, $m\times k$, and another matrix $B$, $k\times n$. From this we could either
- multiply these to get a new $m\times n$ matrix $AB$.
- compose their functions to get a new function $T_{AB} = T_{A}\circ T_{B}$.

Note that it still holds that $T_{AB}$ is equivalent to $AB$ as applied on $\mathbb{R}^{n}$. As an exercise, perhaps show that this holds true.

>[!theorem]
>For any matrix $A$, we may define a function $T_{A} : \mathbb{R}^{n} \longrightarrow \mathbb{R}^{m}$ where $T_{A}(\vec{x})$ for $\vec{x}\in\mathbb{R}^{n}$ is equivalent to the matrix-vector product $A\vec{x}$.

**Proposition.**
For matrices $A$, $B$ and $C$, s.t. $AB$ and $BC$ are defined, then $(AB)C = A(BC)$.
>[!proof]
>$((AB)C)_{ij} = \sum\limits_{p}^{q} a_{ip}b_{pj}$...
>This can equivalently be shown by considering the functions $T_{A}$, $T_{B}$ and $T_{C}$.
>$$\begin{align*}(T_{A}\circ T_{B})\circ T_{C} &= T_{A}\circ(T_{B}\circ T_{C})\end{align*}$$

# The Identity Matrix
>[!def]
>The *identity matrix*, denoted $I_{n}$ for an $n\times n$ matrix, or just simply $I$, is the multiplicative identity in matrix arithmetic. These are in the form,
>$$\begin{align*}
\begin{bmatrix}1 & 0 & \cdots & 0\\
0 & 1 & \cdots & 0\\
\vdots & \vdots & \ddots & \vdots\\
0 & 0 & \cdots & 1\end{bmatrix}
\end{align*}$$
>Rigorously, this being the identity implies the following.
>$$\begin{align*}
IA=AI=A
\end{align*}$$

# Matrix Inverses
>[!def]
>A matrix $A$ is invertible if there exists a matrix $A^{-1}$ such that,
>$$\begin{align*}
AA^{-1} = A^{-1}A = I
\end{align*}$$

>[!theorem]
>If $B$ and $C$ are both inverses of $A$, then $B=C$, i.e., **a matrix may only have one inverse**.
---
>[!proof]
>Suppose we have an invertible matrix $A$ with inverses $B$ and $C$. Then we have,
>$$\begin{align*}
B=BI=B(AC)=(BA)C=IC=C\\
\therefore B=C.\tag*{$\blacksquare$}
\end{align*}$$


Suppose that we have encoded a system of $n$ equations in $n$ variables as $A\vec{x}=B$. This equation is solvable if and only if $A$ is invertible, as,
$$\begin{align*}
A\vec{x} &= B\\
A^{-1}A\vec{x} &= A^{-1}B\\
\vec{x} &= A^{-1}B.
\end{align*}$$
>[!note]
>This may not be the most efficient way of solving a system of equations, but it is worth studying anyway for its general uses and ability to be manipulated algebraically.

Consider the following system.
$$\begin{align*}
2x_{1} + 3x_{2} &= 5\\
x_{1} + 2x_{2} &= 6\\
\\
A=\begin{bmatrix}2 & 3\\
1 & 2\end{bmatrix}&,\ 
B=\begin{bmatrix}5\\
6\end{bmatrix}.\\
\\
A^{-1} &= \begin{bmatrix}2 & -3\\
-1 & 2\end{bmatrix}\\
\text{It does in fact hold that,}\\
\vec{x} = A^{-1}B = \begin{bmatrix}2 & -3\\
-1 & 2\end{bmatrix}\begin{bmatrix}5\\
6\end{bmatrix} &= \begin{bmatrix}-8\\
7\end{bmatrix}
\end{align*}$$

>[!proof]
>Here is an abridged proof that $(AB)^{-1} = B^{-1}A^{-1}$.
>$$\begin{align*}
(AB)(B^{-1}A^{-1}) &= A(BB^{-2})A^{-1}\\
&= AA^{-1}\\
&= I\tag*{$\blacksquare$}
\end{align*}$$

>[!theorem]
>.