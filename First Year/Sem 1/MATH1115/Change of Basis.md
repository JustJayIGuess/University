>[!question]
>Given two bases $B,C$, how are $[v]_{B}$ and $[v]_{C}$ related?

>[!theorem]
>$[v]_{C} = P_{B \rightarrow C}[v]_{B}$, where $P_{B \rightarrow C}$ is the matrix,
>$$\begin{align*}P_{B \rightarrow C} &= \begin{bmatrix}[v_{1}]_{C} & \cdots & [v_{n}]_{C}\end{bmatrix}\end{align*}$$

>[!proof]
>Suppose that $v = a_{1}v_{1} + \cdots + a_{n}v_{n}$, so $[v]_{B} = \begin{bmatrix}a_{1}\\\vdots\\a_{n}\end{bmatrix}$.
>Also, $v_{i} = P_{1i}w_{1} + \cdots + P_{ni}w_{n}$.
> 
> $$\begin{align*}
> v &= a_{1}v_{1} + \cdots + a_{n}v_{n}\\
> &= a_{1}(P_{11}w_{1} + \cdots + P_{n1}v_{n})+\cdots\\
> &= (P_{11}a_{1} + \cdots)w_{1} + \cdots\\
> \therefore [v]_{C} &= \begin{bmatrix}P_{11}a_{1}+\cdots+P_{1n}a_{n}\\\vdots\end{bmatrix} = P_{B \rightarrow c}[v]_{B}.
> \end{align*}$$

