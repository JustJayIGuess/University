#LinearAlgebra 
# Motivation
Consider the system,
$$\begin{align*}
2x + 3y &= 4\\
6x + 7y &= 8.
\end{align*}$$
One may solve this algebraically as follows,
$$\begin{align*}
x &= \frac{-3}{2} y + 2\\
\therefore 6\left(\frac{-3}{2}y+2\right) + 7y &= 8\\
\vdots\\
x &= -1.
\end{align*}$$
This is cumbersome, so the information in this system may be encoded in an [[Augmented Matrix]].
$$\begin{align*}
\begin{pmatrix}2 & 3 & 4\\
6 & 7 & 8\end{pmatrix}\\
\Downarrow\\
\begin{pmatrix}2 & 3 & 4\\
0 & -2 & -4\end{pmatrix}\\
\Downarrow\\
\begin{pmatrix}2 & 3 & 4\\
0 & 1 & 2\end{pmatrix}\\
\\
\therefore y=2, 2x+3y=4\\\\

\text{Backsubstituting,}\\
2x+6=4\Rightarrow x &= -1
\end{align*}$$
>This is one useful application of matrices

This method of solving linear systems works by transforming an augmented matrix into its *row echelon form* and/or *reduced row echelon form*.
## Row Operations
We may manipulate an augmented matrix using *row operations*.

>[!def]
>The *elementary row operations* are:
>- Multiplying an entire row by a scalar
>- Adding a scalar multiple of a row to another row
>- Interchanging two rows

>[!def]
>If a matrix B can be reached from another matrix A using row operations, they are *row equivalent*.
# Row Echelon Form and Reduced Row Echelon Form
## Row Echelon Form
>[!note]
>This may be abbreviated as ref(M)

>[!def]
>A matrix is in *row echelon form* if:
>- All $0$ rows are at the bottom
>- Each *pivot* (leftmost nonzero entry in a row) is to the right of the pivots above it

For example, the following matrix is in row echelon form.
$$\begin{align*}
\begin{pmatrix}0 & \textbf{3} & 5 & 6 & 7\\
0 & 0 & 0 & \textbf{2} & 9\\
0 & 0 & 0 & 0 & 0\end{pmatrix}
\end{align*}$$
## Reduced Row Echelon Form
>[!note]
This may be abbreviated rref(M).

>[!def]
>A matrix is in *reduced row echelon form* if in addition to the prior constraints,
>- each pivot is $1$
>- each *pivot column* (column containing a pivot) has $0$ in all other entries

Now consider the previous example of a matrix in ref form.
This may therefore be converted to rref as follows:
$$\begin{align*}
\begin{pmatrix}
0 & 3 & 5 & 6 & 7\\
0 & 0 & 0 & 2 & 9\\
0 & 0 & 0 & 0 & 0
\end{pmatrix}\\
\\
\begin{pmatrix}
0 & 1 & \frac{5}{3} & 2 & \frac{7}{3}\\
0 & 0 & 0 & 1 & \frac{9}{2}\\
0 & 0 & 0 & 0 & 0
\end{pmatrix}\\
\\
\begin{pmatrix}
0 & 1 & \frac{5}{3} & 0 & \frac{-20}{3}\\
0 & 0 & 0 & 1 & \frac{9}{2}\\
0 & 0 & 0 & 0 & 0
\end{pmatrix}
\end{align*}$$
Reading the new linear system off from the matrix gives:
$$\begin{align*}
0x_{1} + x_{2} + \frac{5}{3} x_{3} + 0x_{4} &= \frac{-20}{3}\\
\Rightarrow x_{2} &= \frac{-5}{3}x_{3} - \frac{20}{3},\\
0x_{1} + 0x_{2} + 0x_{3} + x_{4} &= \frac{9}{2}\\
\Rightarrow x_{4} &= \frac{9}{2}\\
0x_{1} + 0x_{2} + 0x_{3} + 0x_{4} &= 0
\end{align*}$$

>[!remark]
>If the last row of the rref matrix were instead of the form (for $k\ne 0$),
>$$\begin{pmatrix}0 & 0 & 0 & 0 & k\end{pmatrix},$$
>then this would correspond to the equation $0=k$, which is a contradiction. Therefore, this type of augmented matrix indicates that the linear system has no solutions.

The pivot columns of the rref matrix correspond to 'basic' or 'leading' variables - in this case $x_{2}$ and $x_{4}$. The remaining columns correspond to the 'free' variables, which can be thought of as degrees of freedom. Often these free variables set equal to a parameter to more clearly show the degrees of freedom in the solution set.
$$\begin{align*}
\text{let } r,s\in\mathbf{R}\\
x_{1} &= r\\
x_{2} &= \frac{-5}{3}s - \frac{20}{3}\\
x_{3} &= s\\
x_{4} &= \frac{9}{2}
\end{align*}$$
>[!note]
>The entire solution space is parameterized by the two free variables $r$ and $s$
# Categorising solution spaces geometrically
>[!remark]
>Consider that each linear equation in a linear system describes a hyperplane of dimension $n-1$ with $n$ variables. The solution found through gaussian elimination corresponds to the mutual intersection between all these equations.

In 2D, two lines may either intersect at a unique point, at no points (if they are parallel but not coincident), or at infinitely many points.


![[Geometric Solution Spaces to Linear Systems|300]]
