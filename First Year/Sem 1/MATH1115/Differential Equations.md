>[!def]
>A *differential equation* is an equation involving functions and their derivatives.

>[!def]
>The *order* of a differential equation is the highest derivative that appears.
>
>>[!example]
>>$y''=-y$ is a second-order differential equation.
>>The solutions to this is $y=A\cos (x-\alpha)$.

>[!def]
>The *initial conditions* of a solution to a differential equation may be specified.
>>[!example]
>>We may state that $y(0)=1$ and $y'(0)=5$. Then using the prior example, we now only have $y=5\sin(x) + \cos(x)$.

# Linear First-Order Differential Equations
>[!example]
>$$\begin{align*}
>y_{1}' &= a_{11}y_{1} + \cdots + a_{1n}y_{n}\\
>&\ \ \vdots\\
>y_{n}' &= a_{n1}y_{1} + \cdots + a_{nn}y_{n}.\\
>\\
>y' &= Ay.
>\end{align*}$$

>[!remark]
>Note if $A$ is diagonal, then $y_{i}' = \lambda_{i}y_{i}$. So then $y_{i} = C_{i}e^{\lambda_{i}x}$.

>[!theorem]
>If $A = PDP^{-1}$, then we still have the above remark.

>[!example]
>$$\begin{align*}
>y_{1}' &= y_{1} + y_{2}\\
>y_{2}' &= 4y_{1} - 2y_{2}\\
>\\
>A &= \begin{bmatrix}1 & 1 \\ 4 & -2\end{bmatrix}.
>\end{align*}$$
>We can diagonalise this as follows.
>$$\begin{align*}
>A &= \frac{4}{5}\begin{bmatrix} \frac{-1}{4} & 1 \\ 1 & 1 \end{bmatrix}\begin{bmatrix}-3 & 0 \\ 0 & 2\end{bmatrix}\begin{bmatrix}1 & -1 \\ -1 & \frac{-1}{4}\end{bmatrix}.
>\end{align*}$$
>Changing basis, we have,
>$$\begin{align*}
>u &= P^{-1}y \Rightarrow u'=P^{-1}y'.\\
>u' &= P^{-1}Ay\\
> &= P^{-1}PDP^{-1}y\\
>&= Du\\
>u &= \begin{bmatrix}u_{1} \\ u_{2}\end{bmatrix} = \begin{bmatrix}C_{1}e^{-3x} \\ C_{2}e^{2x}\end{bmatrix}\\
>\\
>y &= Pu\\
>&= \begin{bmatrix} \frac{-1}{4}C_{1}e^{-3x} + C_{2}e^{2x} \\ C_{1}e^{-3x} + C_{2}e^{2x} \end{bmatrix}.
>\end{align*}$$
>Now suppose we have initial conditions, $y_{1}(0)=1,y_{2}(0)=6$.
>Then we have,
>$$\begin{align*}
>\begin{bmatrix} \frac{-1}{4}C_{1} + C_{2} \\ C_{1} + C_{2} \end{bmatrix} &= \begin{bmatrix}1 \\ 6\end{bmatrix}\\
>\Rightarrow C_{1} &= 4,C_{2}=2.
>\end{align*}$$
>So then,
>$$\begin{align*}
>y_{1} &= -e^{-3x} + 2e^{2x}\\
>y_{2} &= 4e^{-3x} + 2e^{2x}.
>\end{align*}$$

>[!example]
>$y''=-y$, with initial conditions $y(0) = 1, y'(0)=5$.
>Let $z_{1}=y, z_{2} = y'$. Then,
>$$\begin{align*}
>z_{1}' &= z_{2}\\
>z_{2}' &= -z_{1}.\\
>\\
>A &= \begin{bmatrix}0 & 1 \\ -1 & 0\end{bmatrix}.\\
>\text{Rotation matrix!}\\
>p(\lambda) &= \det\begin{bmatrix}\lambda & -1 \\ 1 & \lambda\end{bmatrix} = \lambda^{2} + 1,\\
>\Rightarrow \lambda_{1} &= -i,\lambda_{2} = i\\
>P &= \begin{bmatrix}-i & i \\ 1 & 1\end{bmatrix}.\\
>D &= \begin{bmatrix}i & 0 \\ 0 & -i\end{bmatrix}.\\
>\\
>u &= P^{-1}z\Rightarrow u'=Du.\\
>u &= \begin{bmatrix}C_{1}e^{ix} \\ C_{2}e^{-ix}\end{bmatrix}\\
>z &= Pu = \begin{bmatrix}-iC_{1}e^{ix} + iC_{2}e^{-ix} \\ C_{1}e^{ix} + C_{2}e^{-ix}\end{bmatrix}.
>\end{align*}$$
>Recalling the initial conditions, we have,
>$$\begin{align*}
>\begin{bmatrix}-i & i \\ 1 & 1\end{bmatrix}\begin{bmatrix}C_{1} \\ C_{2}\end{bmatrix} &= \begin{bmatrix}1 \\ 5\end{bmatrix}.\\
>\Rightarrow C_{1} &= \frac{5}{2} + \frac{1}{2}i,C_{2} = \frac{5}{2} - \frac{1}{2}i.
>\end{align*}$$
>We finally have that,
>$$\begin{align*}
>y_{1} &= 5\cdot \frac{e^{ix}-e^{-ix}}{2} + \frac{e^{ix}+e^{-ix}}{2}\\
>&= -5i\sin x + \cos x\\
>y_{2} &= -5i\sin x - \cos x.
\end{align*}$$

