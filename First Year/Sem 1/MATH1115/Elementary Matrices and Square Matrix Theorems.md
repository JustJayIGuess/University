>[!def]
>An $n\times n$ matrix $E$ is *elementary* if it may be obtained from $I_{n}$ using a single [[Gaussian Elimination#Row Operations|row operation]]. Elementary matrices are useful for representing row operations on a matrix $A$ in terms of a matrix product $EA$.

For example, the following are elementary matrices.
$$\begin{align*}
E_1=\begin{bmatrix}1 & 0\\
0 & 7\end{bmatrix},E_2=\begin{bmatrix}0 & 1\\
1 & 0\end{bmatrix},E_{3}=\begin{bmatrix}1 & 3\\
0 & 1\end{bmatrix}.
\end{align*}$$
Now consider computing  the following.
$$\begin{align*}
E_1\begin{bmatrix}a & b\\c & d\end{bmatrix} &= \begin{bmatrix}a & b \\ 7c & 7d\end{bmatrix}\\
E_{2}\begin{bmatrix}a & b\\c & d\end{bmatrix} &= \begin{bmatrix}c & d\\a & b\end{bmatrix}\\
E_{3}\begin{bmatrix}a & b & c\\d & e & f\end{bmatrix} &= \begin{bmatrix}a+3d & b+3e & c+3f\\d & e & f\end{bmatrix}
\end{align*}$$
>[!theorem]
>$EA$, for an elementary matrix $E$, is obtained from $A$ by doing the row operation on $A$ which was done to $I$ to form $E$.

# Square Matrix Theorems
>[!theorem]
>For an $n\times n$ matrix $A$, the following are equivalent.
>- $A$ is invertible
>- $Ax=0$ has only the trivial solution $x=0$
>- $\text{rref}(A)=I_{n}$
>- $A$ is a product of elementary matrices
---
>[!proof]
>We will prove $A \Rightarrow B \Rightarrow C \Rightarrow D \Rightarrow A$.
>For $A \Rightarrow B$:
>Suppose that $A$ is invertible, i.e., there exists an $A^{-1}$ such that $AA^{-1}=A^{-1}A=I$.
>We have that,
>$$\begin{align*}x = A^{-1}Ax=A^{-1}(Ax)=A^{-1}(0)=0\end{align*}$$
>For $B \Rightarrow C$:
>Suppose that $Ax = 0$ has only $x=0$ as a solution. Then the system of equations corresponding to $\text{rref}(\begin{bmatrix}A\mid 0\end{bmatrix})$ must be,
>$$\begin{align*}x_{1} &= 0\\x_{2}&= 0\\\vdots\\x_{n}&= 0.\end{align*}$$
>Therefore $\text{rref}(A)=[I\mid 0]$. We can discard the last column of zeroes to get $\text{rref}(A) = I$.
>
>For $C \Rightarrow D$:
>Suppose that $\text{rref}(A)=I$. Then there must be some sequence of row operations, $E_{1},E_{2},...,E_{k}$, to get from $A$ to $I$. Hence,
>$$\begin{align*}E_{k}\cdots E_{2}E_{1}A &= I_{n}.\end{align*}$$
>As each $E_{i}$ is invertible and also an elementary matrix, we therefore may express $A$ as,
>$$\begin{align*}A &= E_{1}^{-1}E_{2}^{-1}\cdots E_{k}^{-1}I_{n}\\A &= E_{1}^{-1}E_{2}^{-1}\cdots E_{k}^{-1}\end{align*}$$
>So $A$ is a product of elementary matrices.
>
>For $D \Rightarrow A$:
>If we have that $A=E_{1}E_{2}\cdots E_{k}$, then we have that $A^{-1}=E_{k}^{-1}\cdots E_{2}^{-1}E_{1}^{-1}$, which is defined as all elementary matrices are invertible.
>$$\ \tag*{$\blacksquare$}$$

# Computing the Inverse of a Square Matrix
>[!cor]
>We can compute $A^{-1}$ by doing the same row operations we use to get $\text{rref}(A)=I_{n}$ to $I_{n}$.

As example of this corollary, we will find the following inverse.
$$\begin{align*}
A &= \begin{bmatrix}1 & 3 & -2\\
2 & 5 & -3\\
-3 & 2 & -4\end{bmatrix}
\end{align*}$$
Create the following augmented matrix to find $A^{-1}$.
$$\begin{align*}
A &= \begin{bmatrix}1 & 3 & -2 & 1 & 0 & 0\\
2 & 5 & -3 & 0 & 1 & 0\\
-3 & 2 & -4 & 0 & 0 & 1\end{bmatrix}
\end{align*}$$
![[Elementary Matrices 2024-02-29 10.17.13.excalidraw]]

Therefore we have that,
$$\begin{align*}
A^{-1} &= \begin{bmatrix}14 & -8 & -1\\
-17 & 10 & 1\\
-19 & 11 & 1\end{bmatrix}.
\end{align*}$$

# Commuting Inverses
>[!theorem]
>For $n\times n$ matrices $A$ and $B$, if $AB=I_{n}$, then $BA = I_{n}$.
>This is not obvious, and is false for non-square matrices!
---
>[!proof]
>It will suffice to show that $B$ is invertible, as then we have that,
>$$\begin{align*}AB=I&= B^{-1}B \\ ABB^{-1} &= B^{-1}BB^{-1} \\ A &= B^{-1},\end{align*}$$
>in which case we have that,
>$$\begin{align*}AB=B^{-1}B=BB^{-1}=BA=I.\end{align*}$$
>Now to show that $B$ is invertible, it suffices to show that $Bx=0$ has only trivial solution $x=0$. Suppose that $AB=I$.
>If $Bx=0$, then $ABx=A0=0$. However $AB=I$, so we have that $Ix=x=0$. Therefore $Bx=0 \Rightarrow x=0$, so $B$ is invertible. Therefore the theorem holds.
>$$\begin{align*}\ \tag*{$\blacksquare$}\end{align*}$$

# Diagonal Matrices
>[!def]
>A square matrix $D$ is *diagonal* if all entries off the diagonal are $0$.
>For example, the following is diagonal.
>$$\begin{align*}
\begin{bmatrix}5 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 3\end{bmatrix}
\end{align*}$$

