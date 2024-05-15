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

---

>[!def]
>An *eigenbasis* for a square matrix $A$ is a basis $B = \left\{v_{1},\cdots,v_{n}\right\}$ for $F^{n}$ such that every $v_{i}$ is an eigenvector.
>Similarly, and *eigenbasis* for a linear transformation $T : V \longrightarrow V$ is a basis $B = \left\{v_{1},\cdots,v_{n}\right\}$ for $V$ with each $v_{i}$ an eigenvector.


>[!theorem]
>Suppose that $\lambda_{1},\cdots,\lambda_{k}$ are distinct eigenvalues for $A$ and $S_{1},\cdots ,S_{k}$ are corresponding sets of linearly independent eigenvectors. Then $S_{1}\cup S_{2}\cup\cdots\cup S_{k}$ is linearly independent.
>
>>[!example]
>>For $\lambda_{1}: \left\{v_{1},v_{2}\right\}$, $\lambda_{2}: \left\{v_{3},v_{4},v_{5}\right\}$, we have $\left\{v_{1},v_{2},v_{3},v_{4},v_{5}\right\}$ are linearly independent.
> 
>>[!corollary]
>>If an $n\times n$ matrix $A$ has $n$ distinct eigenvalues then $A$ has an eigenbasis and is therefore diagonalisable.
>>
>>>[!remark]
>>>This should make sense, as the characteristic polynomial of an  $n\times n$ matrix is of degree $n$, and most degree $n$ polynomials have $n$ distinct roots. So most matrices are diagonalisable.
> 
>>[!proof] Baby proof.
>>Suppose that $\left\{v_{1},v_{2}\right\}$ are linearly independent eigenvectors with eigenvalue 3, and $v_{3}$ is an eigenvector with eigenvalue $2$.
>>We claim that $\left\{v_{1},v_{2},v_{3}\right\}$ are linearly independent.
>>Suppose that
>>$$a_{1}v_{2}+a_{2}v_{2}+a_{3}v_{3}=0\tag{1}$$
>>We will be done if we can prove that $a_{1}=a_{2}=a_{3}=0$ from only this.
>>Multiply both sides by $A$.
>>$$\begin{align*}
>>A(a_{1}v_{1}+a_{2}v_{2}+a_{3}v_{3}) &= A(0)=0\\
>>a_{1}(Av_{1})+a_{2}(Av_{2})+a_{3}(Av_{3}) &= 0\\
>>3a_{1}v_{1}+3a_{2}v_{2}+2a_{3}v_{3} &= 0\tag{2}
>>\end{align*}$$
>>Now from $2(1)-(2)$, we have,
>>$$\begin{align*}
>>a_{1}v_{1}+a_{2}v_{2} &= 0\\
>>\Rightarrow a_{1}=a_{2} &= 0.
>>\end{align*}$$
>>Substituting this back into $(1)$ we can finally see that $a_{3}=0$ also. Therefore the vectors are all linearly independent.
> 
>>[!proof]
>> We will prove this by induction on $k$.
>> **Base case.**
>> For $k=1$, the statement is trivially true.
>> **Inductive step.**
>> Suppose that the theorem is true for $k-1$, so then $S_{1}\cup\cdots\cup S_{k}$ is linearly independent. Then let,
>> $$\begin{align*}
>> S_{1}\cup\cdots\cup S_{k-1} &= \left\{v_{1},\cdots,v_{p}\right\},S_{k}=\left\{w_{1},\cdots,w_{q}\right\}.
>> \end{align*}$$
>> Now suppose that,
>> $$\begin{align*}
>> a_{1}v_{1} + \cdots + a_{p}v_{p} + b_{1}w_{1} + \cdots + b_{q}w_{q} &= 0\tag{1}.
>> \end{align*}$$
>> Then we can multiply by $A$ and use properties of eigenvectors to get that,
>> $$\begin{align*}
>> a_{1}\lambda_{1}v_{1} + \cdots + a_{p}\lambda_{k-1}v_{p} + b_{1}\lambda_{k}w_{1} + \cdots + b_{q}\lambda_{k}w_{q} &= 0\tag{2}
>> \end{align*}$$
>> Subtracting $\lambda_{k} (1)$ from $(2)$,
>> $$\begin{align*}
>> a_{1}(\lambda_{1}-\lambda_{k})v_{1}+\cdots + a_{p}(\lambda_{k-1}-\lambda_{k})v_{p} &= 0.
>> \end{align*}$$
>> Then because this set of vectors are linearly independent, all of $a_{1},\cdots, a_{p}$ are $0$. Substituting this back in we can finally conclude that all $a$ are equal to zero, which completes our proof.

# Cayley-Hamilton Theorem

>[!theorem]
>*Cayley-Hamilton Theorem*
>Any square matrix $A$ satisfies its characteristic polynomial.
>I.e.,
>$$\begin{align*}
>P_{A}(A) &= 0.
>\end{align*}$$
> 
>>[!example]
>>Take $A=\begin{bmatrix}a & b\\c & d\end{bmatrix}$.
>>Then we have the following characteristic polynomial,
>>$$\begin{align*}
>>P(\lambda) &= \lambda^{2} - (a+d)\lambda + (ad-bc).
>>\end{align*}$$
>>Now note that,
>>$$\begin{align*}
>>A^{2} &= \begin{bmatrix}a^{2}+bc & ab+bd\\ac+cd & bc+d^{2}\end{bmatrix}\\
>>(a+d)A &= \begin{bmatrix}a^{2}+ad & ab+bd \\ ac+cd & ad-bc\end{bmatrix}.
>>\end{align*}$$
>>So then it is clear that $P(A)=0$.
> 
>>[!proof] (Sketch Proof.)
>>Suppose that $A$ is diagonalisable, so that $A=PDP^{-1}$, $D = \begin{bmatrix}\lambda_{1} & &\\&\ddots&\\&&\lambda_{n}\end{bmatrix}$. This is sufficient through an epsilon-delta argument, as all matrices are epsilon close to a diagonalisable matrix.
>>
>>Then $P_{A}(\lambda) = P_{D}(\lambda) = (\lambda-\lambda_{1})\cdots(\lambda-\lambda_{n})$. So then,
>>$$\begin{align*}
>>P_{A}(A) &= (A-\lambda_{1}I)\cdots(A - \lambda_{n}I)\\
>>&= P(D-\lambda_{1}I)\cdots(D-\lambda_{n}I)P^{-1}\\
>>&= 0.
>>\end{align*}$$
>>The last line follows as $D-\lambda_{i}I$ has a zero in position $i$. 
