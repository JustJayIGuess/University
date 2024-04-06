A vector can be thought of as either a $1\times n$ matrix, $\begin{bmatrix}x_{1} & x_{2} & \cdots & x_{n}\end{bmatrix}$, or as an $n\times 1$ matrix, $\begin{bmatrix}x_{1} \\ x_{2} \\ \vdots \\ x_{n}\end{bmatrix}$.
Similarly, we can also think of an $m\times n$ matrix as either $m$ row vectors, $\begin{bmatrix}r_{1} \\ r_{2} \\ \vdots \\ r_{m}\end{bmatrix}$, or as $n$ column vectors, $\begin{bmatrix}c_{1} & c_{2} & \cdots & c_{n}\end{bmatrix}$.

# Encoding Systems of Linear Equations
A system of $n$ linear equations in $n$ variables is commonly encoded in an $n\times n$ matrix and an $n\times 1$ column vector.
$$\begin{align*}
\begin{matrix}
        & -2x_{2} & -6x_{3} & +4x_{4} &= 9\\
 -x_{1} & -2x_{2} &  -x_{3} & +3x_{4} &= 1\\
-2x_{1} & -3x_{2} &         & +3x_{4} &= -1\\
  x_{1} & +4x_{2} & +5x_{3} & -9x_{4} &= -7
\end{matrix}\\
\\
A &= \begin{bmatrix}0 & -3 & -6 & 4\\
-1 & -2 & -1 & 3\\
-2 & -3 & 0 & 3\\
1 & 4 & 5 & -9\end{bmatrix}\\
\\
x &= \begin{bmatrix}x_{1} \\ x_{2} \\ x_{3} \\ x_{4}\end{bmatrix}\\
\\
b &= \begin{bmatrix}9 \\ 1 \\ -1 \\ -7\end{bmatrix}\\
\\
Ax &= b
\end{align*}$$

# Matrix-Vector Multiplication
>[!def]
>If $A$ is an $m\times n$ matrix, and $x$ is an $n\times 1$ vector, the product $Ax$ is defined as follows.
>$$\begin{align*}
Ax &= \begin{bmatrix}a_{11}x_{1} + \cdots + a_{1n}x_{n}\\
\vdots\\
a_{m1}x_{1} + \cdots + a_{mn}x_{n}\end{bmatrix}
\end{align*}$$

An example of matrix-vector multiplication is shown below.
$$\begin{align*}
x &= \begin{bmatrix}1\\
2\\
3\\
4\end{bmatrix}\\
Ax &= \begin{bmatrix}0 & -3 & -6 & 4\\
-1 & -2 & -1 & 3\\
-2 & -3 & 0 & 3\\
1 & 4 & 5 & -9\end{bmatrix}\begin{bmatrix}1\\
2\\
3\\
4\end{bmatrix}\\
&= \begin{bmatrix}0\times 1 + -3\times 2 + -6\times3 + 4\times4\\
\vdots\\
\end{bmatrix}\\
&= \begin{bmatrix}-8\\
4\\
4\\
-12\end{bmatrix}
\end{align*}$$
# Matrix-Matrix Multiplication
>[!def]
>If $A$ is an $m\times r$ matrix, and $B$ is an $r\times n$ matrix, then $AB$ will be an $m\times n$ matrix, defined by,
>$$\begin{align*}
(AB)_{ij} &= \sum\limits_{k=1}^{r}a_{ik}b_{kj}
\end{align*}$$

Another way to think about this is by thinking of $B$ as $\begin{bmatrix}c_{1} & \cdots & c_{n}\end{bmatrix}$ for column vectors $c_{i}$, then $AB = \begin{bmatrix}Ac_{1} & \cdots & Ac_{n}\end{bmatrix}$.

>[!tip]
>To think about the sizing of matrices more easily, try writing out $B$ to the upper right of $A$. $A$ and $B$ will then map out a new grid of the correct size for $AB$, and on the other dimensions $A$ and $B$ should be of equal size.
>
>![[Vectors and Matrices 2024-02-26 20.27.47.excalidraw|300]]



