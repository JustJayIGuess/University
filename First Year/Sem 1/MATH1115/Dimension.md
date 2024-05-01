>[!def]
>We define the *dimension* $\dim(V)$ as the number of basis vectors in a **[[Coordinates and Basis#Bases of Vector Spaces|basis]]** of $V$.

---

>[!example]
>The vector space $M_{2\times2}$ is 4-dimensional, and has the standard basis,
>$$\begin{align*}
\left\{A_{1},A_{2},A_{3},A_{4}\right\}\\
A_{1} &= \begin{bmatrix}1 & 0\\0 & 0\end{bmatrix}\\
A_{2} &= \begin{bmatrix}0 & 1\\0 & 0\end{bmatrix}\\
A_{3} &= \begin{bmatrix}0 & 0\\1 & 0\end{bmatrix}\\
A_{4} &= \begin{bmatrix}0 & 0\\0 & 1\end{bmatrix}
\end{align*}$$

---

>[!example]
>The vector space $\left\{0\right\}$ is 0-dimensional with basis $\varnothing$.

---

>[!example]
>$P_{n}$, set of polynomials of $\deg\le n$ is ($n+1$)-dimensional, with basis,
>$$\begin{align*}\left\{1,x,x^{2},\cdots,x^{n}\right\}\end{align*}$$
>This can also be defined with basis,
> $$\begin{align*}
> \left\{1,x,\frac{x^{2}}{2},\frac{x^{3}}{6},\cdots,\frac{x^{n}}{n!}\right\}
> \end{align*}$$
> This is useful because,
> $$\begin{align*}
> \frac{d}{dx}(v_{i}) &= \cases{v_{i-1}\quad i\ge1\\0\ \qquad i=0}
> \end{align*}$$

# Validity of Dimension of a Finite Vector Space
>[!theorem]
>Any two bases for a finite-dimensional vector space have the same size.

>[!proof]
>Suppose we have a basis $B = \left\{v_{1,}\cdots, v_{n}\right\}$ is a basis of $V$ and $S = \left\{w_{1},\cdots,w_{m}\right\}$. It is enough to show that if $m>n$ then $S$ is linearly dependent, and if $m<n$ then $S$ does not span $V$.
>
> To prove the first part, we may prove that $x_{1}w_{1} + \cdots + x_{m}w_{m} = 0$ (\*) has more than one solution.
> 	First observe that, as $B$ is a basis, then any vector $v\in V$ is a linear combination of the vectors in $B$. So we have that,
> 	$$\begin{align*}
> 	w_{1} &= a_{11}v_{1} + \cdots + a_{n1}v_{n}\\
> 	\vdots\\
> 	w_{m} &= a_{1m}v_{1} + \cdots + a_{nm}v_{n}.
> 	\end{align*}$$
> 	So substituting into (\*),  we have that,
> 	$$\begin{align*}
> 	x_{1}(a_{11}v_{1}+\cdots + a_{n1}v_{n})\\
> 	\vdots\\
> 	+ x_{m}(a_{1m}v_{1}+\cdots + a_{nm}v_{n}).
> 	\end{align*}$$
> 	We can rearrange this into the form,
> 	$$\begin{align*}
> 	(a_{11}x_{1} + \cdots + a_{1m}x_{m})v_{1} + \cdots + (a_{n1}x_{1} + \cdots  + a_{nm} + x_{m})v_{n}.
> 	\end{align*}$$
> 	However $B$ is a basis, so each of these terms must equal zero. So then,
> 	$$\begin{align*}
> 	a_{11}x_{1} + \cdots + a_{1m}x_{m} &= 0\\
> 	\vdots\\
> 	a_{n1}x_{1} + \cdots + a_{nm}x_{m} &= 0.
> 	\end{align*}$$
> 	This can be arranged in a matrix equation $Ax = 0$. However $m>n$, so this matrix equation must have free variables in its reduced form. Therefore there are infinitely many solutions. So if $m>n$ then $S$ is linearly dependent.
> 
> Now to prove the second part, we can follow the same process, but with the roles of $B$ and $S$ swapped. If $S$ did span $V$, then $v_i$ can be written as a linear combination of the vectors in $S$. We will then find that $B$ is linearly dependent, which is a contradiction.
> $$\begin{align*}
> \ \tag*{$\blacksquare$}
> \end{align*}$$

---

>[!theorem]
>The *plus/minus* theorem states that, if $S$ is a set of vectors in $V$, then:
>- if $S$ is linearly independent and $v\not\in\text{Span}\left(S\right)$ then $S\cup \left\{v\right\}$ is also linearly independent.
>- if $v\in S$ is a linear combination of $S\setminus \left\{v\right\}$ then $\text{Span}(S) = \text{Span}(S\setminus\left\{v\right\})$.
>I.e., we can add linearly independent vectors to a set while preserving linear independence, and we can remove vectors that are linear combination of the other vectors without changing the span.

>[!corollary]
>Suppose $V$ is $n$-dimensional, with $S = \left\{v_{1},\cdots,v_m \right\}$. Then:
>- if $m<n$ and $S$ is linearly independent then there exists $v_{m+1},\cdots,v_{n}$ such that $\left\{v_{1},\cdots,v_{n}\right\}$ is a basis for $V$.
>- if $m>n$ and $S$ spans $V$, then there exists $S'\in S$ where $S'$ is a basis of $V$.

>[!proof]
>Suppose that $S = \left\{v_{1},\cdots,v_{n}\right\}$ is linearly independent and $v\not\in \text{Span}(S)$. It will suffice to prove that,
>$$\begin{align*}S' &= \left\{v_{1},\cdots,v_{n},v\right\}\text{ is lin. indep.}\end{align*}$$
>Suppose that $a_{1}v_{1} + \cdots + a_{n}v_{n} + a_{n+1}v_{n+1} = 0$.
>If $a_{n+1}\ne 0$. Then we may divide by $a_{n+1}$ to get,
>$$\begin{align*}v_{n+1} &= \left(\frac{-a_{1}}{a_{n+1}}\right)v_{1} + \cdots + \left(\frac{-a_{n}}{a_{n+1}}\right)v_{n}.\end{align*}$$
>However this cannot happen as $v_{n+1}\not\in\text{Span}(S)$.
>If $a_{n+1} = 0$, then we clearly have the solution where all $a_{i}=0$.
>This proves the first part of the theorem.
> 
> First, without loss of generality, we will say that $S = \left\{v_{1},\cdots,v_{n}\right\}$ and we will consider the last element $v = v_{n}$ to be the vector that is linearly dependent on the other vectors.
> Now suppose $w\in \text{Span}(S)$, so $w=a_{1}v_{1}+\cdots+a_{n}v_{n}$, and $v = b_{1}v_{1}+\cdots + b_{n-1}v_{n-1}$. Then we have,
> $$\begin{align*}
> w &= a_{1}v_{1} + \cdots + a_{n-1}v_{n-1} + a_{n}(b_{1}v_{1}+\cdots=b_{n-1}v_{n-1})\\
> &= (a_{1} + a_{n}b_{1})v_{1} + \cdots + (a_{n-1}+a_{n}b_{n-1})v_{n-1}\\
> &\in \text{Span}\left\{v_{1},\cdots,v_{n-1}\right\}
> \end{align*}$$
