>[!def]
>Let $A$ be an $n\times n$ matrix. A nonzero vector $v$ is an *eigenvector* with *eigenvalue* $\lambda$ if,
>$$\begin{align*}
>Av &= \lambda v
>\end{align*}$$

>[!example]
>Take $A = \begin{bmatrix}2 & 0\\0 & 3\end{bmatrix}$.
>Observe that $A\begin{bmatrix}1\\0\end{bmatrix} = \begin{bmatrix}2\\0\end{bmatrix}$, so $\begin{bmatrix}1\\0\end{bmatrix}$ is an eigenvector with $\lambda=2$.
>Also observe that $A\begin{bmatrix}0\\1\end{bmatrix} = \begin{bmatrix}0\\3\end{bmatrix}$, with $\lambda=3$ as the eigenvalue.
>
>Now note that we can more easily compute something such as $A^{10}\begin{bmatrix}1\\-1\end{bmatrix}$.
>$$\begin{align*}
>A^{10}\left(\begin{bmatrix}1\\0\end{bmatrix}-\begin{bmatrix}0\\1\end{bmatrix}\right) &= A^{10}\begin{bmatrix}1\\0\end{bmatrix} - A^{10}\begin{bmatrix}0\\1\end{bmatrix}\\
>&= 2^{10}\begin{bmatrix}1\\0\end{bmatrix} - 3^{10}\begin{bmatrix}0\\1\end{bmatrix}\\
>&= \begin{bmatrix}2^{10}\\-3^{10}\end{bmatrix}.
\end{align*}$$

---

>[!lemma]
>Let $A$ be an $n\times n$ matrix. Then,
>- if $v$ is an eigenvector with eigenvalue $\lambda$ and $a\ne 0$, then $av$ is also an eigenvector with eigenvalue $\lambda$.
>- if $v,w$ are both eigenvectors with the same eigenvalue $\lambda$, then if $v+w\ne 0$, $v+w$ is also an eigenvector with eigenvalue $\lambda$.
>
>>[!proof]
>>Suppose $Av=\lambda v$. Then $A(av) = a(Av) = a\lambda v = \lambda(av)$.
>>Now suppose $Av = \lambda v, Aw = \lambda w$. Then $A(v+w) = Av+Aw = \lambda v + \lambda w = \lambda(v+w)$.
>>$$\begin{align*}
\ \tag*{$\blacksquare$}
\end{align*}$$

---

>[!def]
>The *eigenspace* of $A$ corresponding to $\lambda$ is,
>$$\begin{align*}
>E_{\lambda} &= \left\{v \mid Av=\lambda v\right\}\\
>&= \left\{v \mid v\text{ is an eigenvector with eigenvalue }\lambda\right\}\cup \left\{0\right\}.
>\end{align*}$$
>It follows from the above lemma that each $E_{\lambda}$ is a subspace of $F^{n}$.

>[!example]
>Let $A = \begin{bmatrix} \frac{5}{3} & \frac{2}{3} \\ \frac{-2}{3} & \frac{10}{3} \end{bmatrix}$.
>>[!question]
>>Is $v_{1} = \begin{bmatrix}2\\1\end{bmatrix}$ an eigenvector?
>
>$$\begin{align*}
>Av_{1} &= \begin{bmatrix}4\\2\end{bmatrix}\\
>&= 2v_{1}.
>\end{align*}$$
>So then $v_{1}$ is an eigenvector with eigenvalue $\lambda_{1}=2$.
>Similarly, $v_{2} = \begin{bmatrix}1\\2\end{bmatrix}$ is an eigenvector with eigenvalue $\lambda_{2} = 3$.
>Once again, we can compute more complicated results easily.
>$$\begin{align*}
>A^{10}\begin{bmatrix}1\\-1\end{bmatrix} &= 2^{10}v_{1} - 3^{10}v_{2}\\
>&= \begin{bmatrix}2^{11}-3^{10}\\2^{10}-2\times3^{10}\end{bmatrix}.
\end{align*}$$

---

>[!def]
>If we have a linear transformation $T : V \longrightarrow V$, then a nonzero vector $v$ is an *eigenvector* with *eigenvalue* $\lambda$ if $T(v)=\lambda v$.
>Recalling that we may represent linear transformations by matrices, we have that $T$ is represented by the matrix,
>$$\begin{align*}
>[T]_{B} &= \begin{bmatrix}[T(v_{1})]_{B} & \cdots & [T(v_{n})]_{B}\end{bmatrix}.
>\end{align*}$$

>[!example]
>Take $A = \begin{bmatrix} \frac{5}{3} & \frac{2}{3} \\ \frac{-2}{3} & \frac{10}{3} \end{bmatrix}$, and take the basis $B = \left\{v_{1},v_{2}\right\}, v_{1} = \begin{bmatrix}2\\1\end{bmatrix}, v_{2} = \begin{bmatrix}1\\2\end{bmatrix}$.
>As these are eigenvectors, we have $T(v_{1}) = 2v_{1},T(v_{2}) = 3v_{2}$. So then, in the $B$ coordinate system, $[T(v_{1})] = \begin{bmatrix}2\\0\end{bmatrix}$, $[T(v_{2})] = \begin{bmatrix}0\\3\end{bmatrix}$. This means we will get a diagonal matrix $[T]_B$,
>$$\begin{align*}
>[T]_{B} &= \begin{bmatrix}2 & 0 \\ 0 & 3\end{bmatrix}.
\end{align*}$$

---

>[!example]
>Take $A = \begin{bmatrix} \frac{\sqrt{3}}{2} & \frac{-1}{2} \\ \frac{1}{2} & \frac{\sqrt{3}}{2} \end{bmatrix}$. This is a rotation matrix, so there should be no eigenvectors, as any vector will not point in the same direction after a rotation.
>However, there are eigenvectors if we allow complex numbers!

