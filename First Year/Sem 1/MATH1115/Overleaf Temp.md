5. 
The matrix representing the system is a square matrix, and the fact that the system has infinitely many solutions means that there must be at least one free variable. Therefore at least one column of the $rref$ form must be a non-pivot column. For this to be the case in a square matrix, there must also be a row of zeroes at the bottom of the matrix.
If a matrix is invertible, then it is implied that the matrix has only one unique solution to the equation $Ax = \vec{0}$, where $A$ is the matrix. The above system of homogenous equations represents the equation $Ax = \vec{0}$, and has infinitely many solutions, therefore the matrix with coefficients $a_{ij}$ is not invertible.
The new non-homogenous system of equations may be represented by $Ax = b$ with,
$$
b = \begin{bmatrix}e \\ \pi \\ \sin(1) \\ \ln(11)\end{bmatrix}
$$
This must have either infinitely many solutions or no solutions, as it may only have unique solutions $x = A^{-1}b$ if $A$ is invertible, which it is not.

1. 
We begin by considering that $a<b\Rightarrow b-a\in P$ and $c<0\Rightarrow -c\in P$ where $P$ is the set of positive numbers. By P12, we now know that $(b-a)(-c)\in P$, and by the distributive property (P9), then $b(-c) + (-a)(-c)\in P$.

Now notice the following, building from P3.
$$\begin{align*}
a+(-a) &= 0\\
a(-c)+(-a)(-c) &= 0(-c)\\
ac+a(-c)+(-a)(-c)&= 0+ac\\
a(c+(-c)) + (-a)(-c) &= ac\qquad(P9,P2)\\
a0+(-a)(-c)&= ac\qquad(P3)\\
(-a)(-c)&= ac
\end{align*}$$
Additionally, notice the following, building from P9.
$$\begin{align*}
-cb &= -c\times b\\
-cb &= b(-c)\qquad(P8)\\
-bc &= b(-c)\qquad(P8)
\end{align*}$$
Therefore we can show that,
$$\begin{align*}
b(-c) + (-a)(-c)&\in P\\
-bc +ac&\in P\\
ac - bc&\in P.\qquad(P4)
\end{align*}$$
This now finally implies that $ac>bc$.


2. 
Consider the case when $n=1$. Then one may simply move the only disc in one move to another peg, which is trivially the best solution. We will denote this as $m_{1} = 1$, where $m_{n}$ is the number of moves needed to solve the puzzle.
Now assume that it is possible to solve the puzzle in all cases up to $n=k$, and consider the case $n=k+1$.

Note that the smallest disc may be moved anywhere at any time, as there are no discs smaller than it. Additionally, no other discs may move onto the peg that the smallest disc is currently on, i.e., there are only two pegs available at any time for discs other than the smallest. This means that, after any move made by a disc that is not the smallest, the only valid moves are a move involving the smallest disc, or a move undoing the last move. Undoing the last move will make the solution non-optimal, so it must be true that after every move not involving the smallest disc, the smallest disc must be moved.
We begin by moving the smallest ($k+1^{th}$) disc to a new peg, leaving a pile of size $k$. Now we can solve the case for $n=k$, moving the smallest disc after each move to the peg that is not used in the next move. We have now made an additional $2m_{k}-1$ moves. Finally, once the puzzle is solved for $n=k$, we move the smallest disc onto the top of the pile, for a total of $m_{k+1} = 1+1+2m_{k}-1 = 2m_{k}+1$.
We therefore have that,
$$\begin{align*}
m_{1} &= 1,\\
m_{k+1} = 2m_{k}+1 \Rightarrow m_{k} &= 2m_{k-1}+1.
\end{align*}$$
Expanding this,
$$\begin{align*}
m_{k} &= 2(2m_{k-2}+1)+1\\
&= 4m_{k-2}+3\\
&= 4(2m_{k-3}+1)+3\\
&= 8m_{k-3}+7
\end{align*}$$
It can be seen that each time an $m_{k-j}$ is expanded, an additional $2$ is multiplied into the coefficient of $m_{k-j-1}$ and the prior coefficient is added to the constant term. This means that the coefficient grows as a power of two, and the constant term grows as a power of two minus one,
$$\begin{align*}
m_{k} &= 2^{j}m_{k-j} + 2^{j}-1.
\end{align*}$$
When $j=k-1$,
$$\begin{align*}
m_{k} &= 2^{k-1}m_{k-(k-1)}+2^{k-1}-1\\
&= 2^{k-1}m_{1}+2^{k-1}-1\\
&= 2^{k-1}+2^{k-1}-1\\
&= 2\times 2^{k-1}-1\\
&= 2^{k}-1
\end{align*}$$
The solution was also optimal, as each move was made as absolutely required through inductively building up from the base case $n=1$, and no moves were made that would undo the previous move, as each second move was required to be a movement of the smallest disc.

3. 
