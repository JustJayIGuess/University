
>[!proof]
>Proof of $\det(A) = ad-bc$
>Note that the row operation of adding one row to another does not alter the area of the parallelogram.
>EXERCISE (by row operations)

>[!def] Intuitive Definition.
>For an $n\times n$ matrix $A$, the determinant of $A$ is the $n$-dimensional volume scaling factor of $T_{A}$, which is positive if $T_{A}$ preserves orientation and negative if $T_{A}$ reverses orientation.
# Properties of the Determinant
- $\det(I_{n}) = 1$
- If $B$ is obtained from $A$ by scaling a single row by a scalar factor $c$ then $\det(B)=c\det(A)$
- If $B$ is obtained from $A$ by adding a multiple of one row to another tow then $\det(B)=\det(A)$
- If $B$ is obtained from $A$ by swapping two rows then $\det(B)=-\det(A)$.

>[!def]
>Suppose by induction that we already defined the determinant of an $(n-1)\times (n-1)$ matrix. For an $n\times n$ matrix $A_{1}$, we have that,
>$$\begin{align*}\det(A) &= \sum\limits_{j=1}^{n}a_{1j}C_{1j}=a_{11}C_{11}+...+a_{1n}C_{1n}\\C_{ij} &= (-1)^{i+j}\det(\text{A with row i and j deleted}).\end{align*}$$
>E.g.,
>$$\begin{align*}
\det\left(\begin{bmatrix}a & b & c \\ d & e & f \\ g & h & i\end{bmatrix}\right)=a\det\left(\begin{bmatrix}e & f\\h & i\end{bmatrix}\right)-b\det\left(\begin{bmatrix}d & f\\g & i\end{bmatrix}\right)+c\det\left(\begin{bmatrix}d & e\\g & h\end{bmatrix}\right)
\end{align*}$$
>Note that $\det(n\times n)$ has $n!$ terms. So $\det(10\times10)$ has over 3 million terms.

>[!theorem]
>$\det(A)\ne 0 \Leftrightarrow A\text{ invertible}$.
---
>[!proof]
>will be done on monday

>[!theorem]
>For any $1\le i\le n$, we can instead compute the determinant using the *cofactor expansion along row $i$* instead of row $1$, i.e.,
>$$\begin{align*}\det(A)=a_{i1}C_{i1}+a_{i2}C_{i2}+...+a_{in}C_{in}.\end{align*}$$
>We can also go along the $i^{th}$ *column*.
---
>[!proof]
>will be done on monday

>[!lemma]
>Suppose $A,B,C$ are $n\times n$ matrices that are identical except in a single row $k$, and row $k$ of $A$ is row $k$ of $B\ +$ row $k$ of $C$. Then,
>$$\begin{align*}
\det(A)=\det(B)+\det(C).
\end{align*}$$

>[!proof]
>By induction on the size $n$.
>**Base case.**
>Trivial; $\det(\begin{bmatrix}a\end{bmatrix})=a$ and $a=b+c$.
>**Inductive step.**
>Suppose the two cases where $k=1$ and where $k\ne 1$.
>*If $k=1$:*
>So,
>$$\begin{align*}\det\left(\begin{bmatrix}b_{11}+c_{11} & b_{12}+c_{12}\\a_{21} & a_{22}\end{bmatrix}\right) &= (b_{11}+c_{11})C_{11}(A)+(b_{12}+c_{12})C_{12}(A)\\&= b_{11}C_{11}(A)+b_{12}C_{12}(A)+c_{11}C_{11}(A)+c_{12}C_{12}(A)\\&= b_{11}C_{11}(B)+b_{12}C_{12}(B)+c_{11}C_{11}(C)+c_{12}C_{12}(C)\\&= \det(B)+\det(C).\end{align*}$$

>[!lemma]
>Suppose that we get from the square matrix to $A$ to $B$ by multiplying a row, $k$, by $c$. Then $\det(B)=c\det(A)$

>[!proof]
>This will be proven by induction on the size of the matrix, $n$.
>**Base case.**
>$n=1$ is clear.
>**Inductive step.**
>$k=1$:
>We assume that this holds for any matrix of size $n-1$.
>Then,
>$$\begin{align*}
\det(B)&= b_{11}C_{11}(B)+...+b_{1n}C_{1n}(B)\\
&= ca_{11}C_{11}(A)+...+ca_{1n}C_{1n}(A)\\
&= c(a_{11}C_{11}(A)+...)\\
&= c\det(A).
\end{align*}$$
>$k\ne 1$:
>Note that $B$ with row 1 and column $j$ deleted is the same as $A$ with row $1$ and column $j$ deleted, with some row scaled by $c$.
>By our induction hypothesis, $C_{1j}(B)=cC_{1j}(A)$.
>Then,
>$$\begin{align*}
\det(B) &= b_{11}C_{11}(B)+...+b_{1n}C_{1n}(B)\\
&= a_{11}cC_{11}(A)+...+a_{1n}cC_{1n}(A)\\
&= c\det(A).
\end{align*}$$

>[!lemma]
>Suppose that $B$ is obtained from $A$ by swapping two rows. Then,
>$$\begin{align*}\det(B) &= -\det(A)\end{align*}$$

>[!proof]
>This will be done in a workshop

>[!lemma]
>If $B$ is obtained from $A$ by adding a multiple of one row to another row, then the determinant is unchanged.
>$$\begin{align*}\det(A)=\det(B)\end{align*}$$

>[!proof]
>Add $cR_{i}$ to $R_{j}$. Then,
>$$\begin{align*}B&= \begin{bmatrix}R_1\\R_2\\\vdots\\R_i\\\vdots\\R_n\end{bmatrix},\  C = \begin{bmatrix}R_1\\R_2\\\vdots\\R_i\\\vdots\\cR_{i}\\\vdots\\R_{n}\end{bmatrix}\end{align*}$$
>Then we have two matrices that differ only by a row that is multiplied. So $\det(B)=\det(A)+\det(C)$. We also have that,
>$$\det(C)=c\det\left(\begin{bmatrix}R_1\\\vdots\\R_i\\\vdots\\R_i\\\vdots\\R_n\end{bmatrix}\right)$$
>However now notice that we can swap the two identical rows $R_{i}$ and $R_{i}$ which should negate the determinant. Since the matrix is unchanged, it must still be equal. Therefore the determinant of $C$ is zero. I.e.,
>$$\begin{align*}\det(B)=\det(A).\end{align*}$$


>[!summary] 
>- Multiplying a row by $c$ will multiply the determinant by $c$
>- Swapping two rows will negate the determinant
>- Adding a multiple of one row to another will not change the determinant

>[!cor]
>If the $\text{rref}$ of $A$ has a row of zeroes, then $\det(A)=0$. Imagine swapping the zero row to the top of the matrix. Then all cofactors are multiplied by zero.

>[!cor]
>If $A=E_{r}\cdots E_1$, where $E_{i}$ is an elementary matrix, then,
>$$\begin{align*}\det(A)=\det(E_{r})\cdots \det(E_{1})\end{align*}$$

>[!cor]
>$A$ is invertible if and only if $\det(A)\ne 0$.

>[!lemma]
>$\det(A^{T})=\det(A)$.

>[!proof]
>If $A$ is not invertible: both sides are zero, so the lemma holds.
>If $A$ is invertible, then $A=E_{r}\cdots E_{1}$ for elementary matrices $E_{i}$.
>So then $A^{T} = E_{1}^T \cdots E_{r}^{T}$.
>Then since $\det(A^{T})=\det(A)$ the statement must be true.

>[!cor]
>We can equivalently do any column operation, and the effect will be the same as with the analogous row operation.
>Any column operation can be thought of as a row operation on the transpose.

>[!cor]
>We can compute the determinant of $A$ by cofactor expansion along any row or column.
>To do this along any row, imagine swapping any row to the top row. Equivalent for columns.

>[!cor]
>$\det(AB)=\det(A)\det(B)$

>[!proof]
>If $A$ or $B$ is not invertible, then both sides will be zero.
>Otherwise we have that $A=E_{r}\cdots E_{1}$ and $B = F_{r}\cdots F_{1}$ where $E,F$ are elementary matrices. Then $AB=E_{r}\cdots E_{1}F_{r}\cdots F_{1}$, so $\det(AB)=\det(A)\det(B)=\det(E_{r})\cdots\det(E_{1})\det(F_{r})\cdots\det(F_{1})$

>[!def]
>The *adjoint* of $A$ is the matrix
>$$[\text{adj}(A)]_{ij} = C_{ji} = (-1)^{i+j}\det(A\text{ with row j and column i deleted})$$

>[!theorem]
>If $A$ is invertible, then,
>$$\begin{align*}A^{-1} &= \frac{1}{\det(A)}\text{adj}(A).\end{align*}$$

>[!proof]
>If is enough to prove that,
>$$\begin{align*}[A\text{ adj}(A)]_{ii} &= \det(A) \\ [A\text{ adj}(A)]_{jj} &= 0\text{ for }i\ne j\\
[A\text{ adj(A)}]_{ii} &= \sum\limits_{k=1}^{n}a_{ik}\text{ adj}(A)_{ki}\\
&= \sum\limits_{k=1}^{n}a_{ik}\text{ adj}(A)_{ik}\\
&= 
\end{align*}$$

