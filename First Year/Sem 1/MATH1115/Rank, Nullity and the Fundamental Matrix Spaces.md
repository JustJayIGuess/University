# Fundamental Subspaces
>[!todo]
>Transfer notes!

>[!theorem]
>$\dim \text{row}(A) = \dim \text{col}(A)$.
>
>>[!proof]
>> Recall that row operations do not change the row space and don't change the dimension of the column space. So then we can compute both of these using the $\text{rref}(A)$, where,
>> $$
>> \dim\text{row}(A) = \text{\# non-zero rows in rref}(A)
>> $$
>> $$
>> \dim \text{col}(A) = \text{\# pivot columns in rref}(A).
> >$$
>> Each non-zero row has one pivot, so these are equal.

---

>[!def]
>The *rank* of $A$ is $\dim \text{row}(A)=\dim \text{col}(A)$.

>[!def]
>The *nullity* of $A$ is $\dim \text{null}(A)$.

>[!theorem]
>The *rank-nullity theorem* states than for an $m\times n$ matrix $A$,
>$$\text{rank}(A) + \text{nullity}(A) = n.$$
>Similarly,
>$$\text{rank}(A) + \text{nullity}(A^{T}) = m.$$
>
>>[!proof]
>>We can once again compute both using $\text{rref}(A)$
>>$$\begin{align*}\text{rank}(A) &= \text{\# of pivot columns}\\\text{nullity}(A) &= \text{\# of free variables}.\end{align*}$$
>>We have $n$ variables, and each is either pivot or free, so these must add to $n$.

---

>[!def]
>If $W$ is a subspace of $\mathbb{R}^{n}$, its *orthogonal compliment*, $W^{\perp}$ is,
>$$
>W^{\perp} = \left\{v\in \mathbb{R}^{n} \mid v\cdot w=0\ \forall w\in W\right\}.
$$

>[!theorem]
>$W^{\perp}$ is also a subspace.

>[!theorem]
>$(W^{\perp})^{\perp}=W$.

>[!todo]
>Prove these two theorems as exercises.

---

>[!theorem]
>For a real $m\times n$ matrix $A$, $\text{row}(A)$ and $\text{null}(A)$ are orthogonal compliments.
>Similarly for $\text{col}(A)$ and the left null space.
>>[!proof]
>>First, let $A = \begin{bmatrix}r_{1}\\\vdots\\r_{m}\end{bmatrix}$. Then $Ax = \begin{bmatrix}r_{1}\cdot x\\\vdots\\r_{m}\cdot x\end{bmatrix}$.
>>So then $Ax=0$ (i.e., $x\in \text{null}(A)$) if and only if $x$ is orthogonal to each of $r_{1},\cdots,r_{m}$. But if $x$ is orthogonal to $r_{1},\cdots,r_{m}$, then $x$ is orthogonal to $\text{row}(A)$.
>
>
>
>>[!remark]
>>For complex matrices, there is a complication, as $v\cdot w = \sum\limits \bar{v}_{i}w_{i}$, but $Ax$ does not involve this complex conjugation.

>[!theorem]
>Let $A$ be an $m\times n$ matrix.
>If $m>n$, we say that this is overdetermined. In this case, there is some $b$ with $Ax=b$ inconsistent.
>If $m<n$, we say that this is underdetermined. In this case, there is some $b$ with $Ax=b$ either inconsistent or having infinitely many solutions.
>>[!proof]
>>If overdetermined, then $\text{rank}(A)\le n<m$, so $\text{col}(A)$ has $\dim\le n$ and cannot span $F^{m}$. So there is some $b\in F^{m}$ which is not in $\text{col}(A)$.
>>If underdetermined, then $\text{rank}(A)\le m < n$, TODO
