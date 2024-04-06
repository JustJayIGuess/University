# General Linear Transformations

>[!def]
>A function $T : \mathbb{R}^{n} \longrightarrow \mathbb{R}^{m}$ is a *linear transformation* if, for all $c\in \mathbb{R}$ and $u,v\in R^{n}$, we have,
>$$\begin{align*}T(u+v)&= T(u)+T(v) \\ T(cu) &= cT(u).\end{align*}$$

# Matrix Multiplication as Linear Transformations
>[!lemma]
>For a matrix $A$, $T_{A}$ is a linear transformation, with $T_{A}(x) = Ax$.
---
>[!proof]
>Observe that,
>$$\begin{align*}T_{A}(u+v) &= A(u+v) = Au+Av = T(u)+T(v)\\T_{A}(cu)&= A(cu)= c(Au)=cT(u)\tag*{$\blacksquare$}\end{align*}$$

## Examples
>[!example]
>Suppose we have $f(x) = \sin(x) : \mathbb{R} \longrightarrow \mathbb{R}$.
>Is this linear?
>
>Check: is it true that $f(x+y) = f(x)+f(y)$?
>By counterexample, $\sin(30\degree+60\degree) = \sin(90\degree) \ne \sin(30\degree)+\sin(60\degree)$.
>This is **not a linear transformation**.

>[!example]
>Is $2x+3$ linear?
>$$\begin{align*}2(0+0)+3 &= 3 \ne 6 = (2(0)+3)+(2(0)+3)\end{align*}$$
>This is **not a linear transformation**.

# Linear Transformations as Matrix Multiplication

>[!theorem]
>Suppose $T : \mathbb{R}^{n} \longrightarrow \mathbb{R}^{m}$ is a linear transformation.
>Then $T = T_{A}$ for some matrix $A$.
>I.e., every linear transformation can be represented by multiplication by some matrix.
---
>[!proof]
>Suppose that $T$ is linear. We will find a matrix $A$ and then show that $T(x) = T_{A}(x)$ for all $x\in \mathbb{R}^{n}$.
>Let,
>$$\begin{align*}e_{1} &= \begin{bmatrix}1\\0\\ \vdots\\0\end{bmatrix},e_{2}=\begin{bmatrix}0\\1\\ \vdots\\0\end{bmatrix},\cdots,e_{n}=\begin{bmatrix}0\\0\\ \vdots\\1\end{bmatrix}\\A &= \begin{bmatrix}T_{e_{1}}\cdots T_{e_{n}}\end{bmatrix}.\end{align*}$$
>For some column vector $x=\begin{bmatrix}x_{1}\\ \vdots\\x_{n}\end{bmatrix}$, observe that,
>$$\begin{align*}x &= x_{1}e_{1}+x_{2}e_{2}+\cdots+x_{n}e_{n}.\end{align*}$$
>Then,
>$$\begin{align*}T(x)&= T(x_{1}e_{1}+x_{2}e_{2}+\cdots+x_{n}e_{n})\\&= T(x_1e_{1})+T(x_{2}e_{2})+\cdots+T(x_{n}e_{n})\\&= x_{1}T(e_{1})+x_{2}T(e_{2})+\cdots+x_{n}T(e_{n}).\end{align*}$$
>By definition of matrix multiplication,
>$$\begin{align*}A\begin{bmatrix}x_{1}\\\vdots\\x_{n}\end{bmatrix}&= \begin{bmatrix}T_{e_{1}}\cdots T_{e_{n}}\end{bmatrix}\begin{bmatrix}x_{1}\\\vdots\\x_{n}\end{bmatrix}.\end{align*}$$
>So, $T=T_{A}$.

>[!remark]
>By this theorem, we now know that we can represent a linear transformation with a matrix by considering the result of the transformation on each basis vector $T(e_{i})=T_{i}$. The matrix will be the matrix with $T_{i}$ as its columns.

## Example
>[!example]
>Suppose $T : \mathbb{R}^{2} \longrightarrow \mathbb{R}^{3}$, with,
>$$\begin{align*}T\left(\begin{bmatrix}x\\y\end{bmatrix}\right)&= \begin{bmatrix}2x+y\\x-3y\\-x+y\end{bmatrix}\\T\left(e_{1}\right)=T\left(\begin{bmatrix}1\\0\end{bmatrix}\right)&= \begin{bmatrix}2\\1\\-1\end{bmatrix}\\\vdots\\T(x)=Ax, A&= \begin{bmatrix}2 & 1\\1 & -3\\-1 & 1\end{bmatrix}.\end{align*}$$

>[!example]
>$$\begin{align*}
T : \mathbb{R}_{2} \longrightarrow \mathbb{R}_{2}\text{ be a rotation by } \frac{\pi}{6}.\\
T(e_{1}) &= T\left(\begin{bmatrix}1\\0\end{bmatrix}\right)\\
&= \begin{bmatrix}\cos(\frac{\pi}{6})\\\sin(\frac{\pi}{6})\end{bmatrix}\\
&= \begin{bmatrix} \frac{\sqrt{3}}{2}\\ \frac{1}{2} \end{bmatrix}\\
T(e_{2}) &= T\left(\begin{bmatrix}0\\1\end{bmatrix}\right)\\
&= \begin{bmatrix}-\sin(\frac{\pi}{6})\\ \cos(\frac{\pi}{6})\end{bmatrix}\\
&= \begin{bmatrix} \frac{-1}{2} \\ \frac{\sqrt{3}}{2} \end{bmatrix}\\
\\
\therefore T(x)=Ax,A &= \begin{bmatrix} \frac{\sqrt{3}}{2} & \frac{-1}{2} \\ \frac{1}{2} & \frac{\sqrt{3}}{2}\end{bmatrix}
\end{align*}$$

# Rotation Matrices

>[!remark]
>The matrix for a rotation by $\theta$ is,
>$$\begin{align*}\begin{bmatrix}\cos(\theta) & -\sin(\theta) \\ \sin(\theta) & \cos(\theta)\end{bmatrix}\end{align*}.$$

>[!question]
>What might happen if one applies the rotation matrices for $\theta_{1}$ and $\theta_{2}$ successively, as compared to what happens when we apply the single matrix for $\theta_{1}+\theta_{2}$.
>What identities might we be able to extrapolate from this with regards to the trigonometric functions?
