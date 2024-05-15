>[!question]
>What is the matrix for $T : V \longrightarrow V$ in an eigenbasis $B=\left\{v_{1},\cdots,v_{n}\right\}$.
>>[!check] Solution.
>>We have $T(v_{1})=\lambda_{1}v_{1}\cdots T(v_{n})=\lambda_{n}v_{n}$.
>>$$\begin{align*}
>>[\lambda_{1}v_{1}]_{B} &= \begin{bmatrix}\lambda_{1}\\0\\\vdots\\0\end{bmatrix}\cdots[\lambda_{n}v_{n}]_{B} = \begin{bmatrix}0\\\vdots\\0\\\lambda_{n}\end{bmatrix}.
>>\end{align*}$$
>>So then,
>>$$\begin{align*}
>>[T]_{B} &= \begin{bmatrix}\lambda_{1} & 0 & \cdots & 0\\
0 & \lambda_{2} & \cdots & 0\\
\vdots & \vdots & \ddots & \vdots\\
0 & 0 & \cdots & \lambda_{n}\end{bmatrix}.
\end{align*}$$

>[!example]
>Suppose $A$ is $n\times n$ and has eigenbasis $B = \left\{v_{1},\cdots,v_{n}\right\}$.
>So then $Av_{i} = \lambda_{i}v_{i}$.
>Then,
>$$\begin{align*}
>[T_{A}]_{B} &= \begin{bmatrix}\lambda_{1} & 0 & \cdots & 0\\
>0 & \lambda_{2} & \cdots & 0\\
>\vdots & \vdots & \ddots & \vdots\\
>0 & 0 & \cdots & \lambda_{n}\end{bmatrix}.
>\end{align*}$$
>If $E=\left\{e_{1},\cdots,e_{n}\right\}$ is the standard basis, then,
>$$\begin{align*}
>[T_{A}]_{E} &= A\\
>\Rightarrow [T_{A}]_{B} &= D = \begin{bmatrix}\lambda_{1} & 0 & \cdots & 0\\
>0 & \lambda_{2} & \cdots & 0\\
>\vdots & \vdots & \ddots & \vdots\\
>0 & 0 & \cdots & \lambda_{n}\end{bmatrix}
>\end{align*}$$
>Now consider changing basis between $E$ to $B$.
>$$\begin{align*}
>P=P_{B \rightarrow E} &= \begin{bmatrix}v_{1} & \cdots & v_{n}\end{bmatrix}\\
>P_{E \rightarrow B} &= P^{-1}.
>\end{align*}$$
>Then we have,
>$$\begin{align*}
>A &= PDP^{-1}.
\end{align*}$$

>[!def]
>If $A$ does not have an eigenbasis, we call $A$ *defective*.

>[!example]
>Take $A = \begin{bmatrix}0 & 0 & -2 \\ 1 & 2 & 1 \\ 1 & 0 & 3\end{bmatrix}$.
>We can compute the characteristic polynomial as $P(\lambda)=(\lambda-1)(\lambda-2)^{2}$. This has roots at $\lambda_{1}=1,\lambda_{2}=2$.
>For $\lambda_{1}$, $E_{\lambda_{1}} = \text{span}\left\{v_{1}=\begin{bmatrix}-2\\1\\1\end{bmatrix}\right\}$.
>For $\lambda_{2}$, $E_{\lambda_{2}} = \text{span}\left\{v_{2} = \begin{bmatrix}-1\\0\\1\end{bmatrix}, \begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix}\right\}$.
>So then $A=PDP^{-1}$ with,
>$$\begin{align*}
>P &= \begin{bmatrix}-2 & -1 & 0\\1 & 0 & 1\\1 & 1 & 0\end{bmatrix},\\
>D &= \begin{bmatrix}1 & 0 & 0 \\ 0 & 2 & 0\\0 & 0 & 2\end{bmatrix}.
>\end{align*}$$

>[!def]
>If $A$ and $B$ are $n\times n$ are *similar* if there exists $P$ with $B=PAP^{-1}$.
>If $A$ and $B$ are similar, they represent the same linear transformation in two different bases.

>[!theorem]
>If $A,B$ are similar, then $P_{A}(\lambda)=P_{B}(\lambda)$.
>So $P(\lambda)$ depends only on the linear transformation $T$, and not the choice of basis.
>
>>[!proof]
>>Suppose that $B=PAP^{-1}$. Then we have,
>>$$\begin{align*}
>>P_{B}(\lambda) &= \det(\lambda I - PAP^{-1})\\
>>&= \det(P\lambda IP^{-1}-PAP^{1})\\
>>&= \det(P(\lambda I - A)P^{-1})\\
>>&= \det(P)\det(\lambda I-A)\det(P^{-1})\\
>>&= \det(\lambda I-A) = P_{A}(\lambda).
\end{align*}$$

>[!example]
>Take $A = \begin{bmatrix}1 & 2 \\ 0 & 1\end{bmatrix}$, which has $P_{A}(\lambda) = (\lambda-1)^{2}$.
>This has only one eigenvector $\lambda_{1} = 1$, and the eigenspace turns out to be one-dimensional, so there is no eigenbasis.
>
>![[an-emoji-disintegrating-in-pain.gif|200]]

>[!def]
>The *algebraic multiplicity* of an eigenvalue $\lambda_0$ is the number of $\lambda-\lambda_0$ factors in $P(\lambda)$.

>[!def]
>The *geometric multiplicity* is the dimension of the eigenspace $E_{\lambda_{0}}$.

>[!theorem]
>- Alg mult $\ge$ geom mult
>- A is diagonalisable if and only if alg mult $=$ geom mult for all eigenvalues.
