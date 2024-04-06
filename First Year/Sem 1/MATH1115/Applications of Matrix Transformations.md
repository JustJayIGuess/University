Some applications of matrix transformations include:
- Network analysis
- Chemical equations
- Electrical Circuits
- Leontief Input-Output Models

# Network Analysis
We may consider a network where the flow into any vertex must equal the flow out of it.
![[Applications of Matrix Transformations 2024-03-06 12.14.39.excalidraw|300]]
We may now form a system of equations for this.
$$\begin{align*}
x_{3} &= x_{4}+40\\
x_{4} + 60 &= x_{1}\\
x_{1} &= 55 + x_{2}\\
x_{2} + 30 &= x_{3}\\
\\
&\begin{bmatrix}
0 & 0 & 1 & -1 & 40\\
-1 & 0 & 0 & 1 & -60\\
1 & -1 & 0 & 0 & 55\\
0 & 1 & -1 & 0 & -30
\end{bmatrix}
\end{align*}$$
If we add all rows, we will get the row,
$$\begin{align*}
\begin{bmatrix}0 & 0 & 0 & 0 & 5\end{bmatrix}
\end{align*}$$
This means that our matrix is inconsistent, i.e., there are no solutions. This is analogous to the fact that the total inflow into the matrix is different to the total outflow of the matrix.

# Chemical Equations
Suppose we have the following chemical equations.
$$\begin{align*}
\ce{CH_{4} + O_{2} -> CO_{2} + H_{2}O}
\end{align*}$$
How may we balance this equations?
We must balance the carbon, hydrogen and oxygen.
$$\begin{align*}
\ce{x_{1}CH_{4} + x_{2}O_{2} &-> x_{3}CO_{2} + x_{4}H_{2}O}\\
x_{1}&= x_{3}\tag{carbon}\\
4x_{1} &= 2x_{4}\tag{hydrogen}\\
2x_{2} &= 2x_{3}+x_{4}\tag{oxygen}\\
\\
&\begin{bmatrix}
1 & 0 & -1 & 0 & 0\\
4 & 0 & 0 & -2 & 0\\
0 & 2 & -2 & -1 & 0
\end{bmatrix}\\\\
\sim&\begin{bmatrix}
1 & 0 & 0 & \frac{-1}{2} & 0\\
0 & 1 & 0 & -1 & 0\\
0 & 0 & 1 & \frac{-1}{2} & 0
\end{bmatrix}
\end{align*}$$
Therefore we have the following,
$$\begin{align*}
x_{4}\text{ is free.}\\
x_{1} &= \frac{1}{2}x_{4}\\
x_{2} &= x_{4}\\
x_{3} &= \frac{1}{2}x_{4}\\
\\
\text{let }x_{1} &= t\text{, then,}\\
x_{1} &= \frac{1}{2}t\\
x_{2} &= t\\
x_{3} &= \frac{1}{2}t\\
x_{4} &= t\\
\\
t &= 2,\\
\ce{CH_{2} + 2O2 -> CO2 + 2H2O}
\end{align*}$$

# Electrical Circuits
Consider the following circuit.

![[Applications of Matrix Transformations 2024-03-06 12.32.16.excalidraw|350]]

The current into any junction must equal the current out.
$$\begin{align*}
I_{1} &= I_{2} + I_{3}\\
I_{2} + I_{3} &= I_{1}\\
&\text{Voltage drop around a circuit must be zero.}\\
50 - 5I_{1} - 20I_{3} &= 0\\
30 +20I_{3} - 10I_{2} &= 0\\
\\
&\begin{bmatrix}
1 & -1 & -1 & 0\\
-1 & 1 & 1 & 0\\
5 & 0 & 20 & 50\\
0 & 10 & -20 & 30
\end{bmatrix}\\
\\
\sim&\begin{bmatrix}
1 & 0 & 0 & 6\\
0 & 1 & 0 & 5\\
0 & 0 & 1 & 1\\
0 & 0 & 0 & 0
\end{bmatrix}\\
\therefore, I_{1} &= 6, I_{2}=5,I_{3}=1
\end{align*}$$

# Leontief Input-Output Models
Suppose that an economy is divided into sectors. Each sector produces outputs and requires inputs from other sectors and itself.

|          | Inputs required per dollar output |               |             |           |
| -------- | --------------------------------- | ------------- | ----------- | --------- |
| Provider |                                   | Manufacturing | Agriculture | Utilities |
|          | Manufacturing                     | $0.50         | $0.10       | $0.10     |
|          | Agriculture                       | $0.20         | $0.50       | $0.30     |
|          | Utilities                         | $0.10         | $0.30       | $0.40     |
I.e., to produce \$1 of agriculture, we need \$0.10 of manufacturing, \$0.50 of agriculture and \$0.30 of utilities.
$$\begin{align*}
C &= \begin{bmatrix}
0.5 & 0.1 & 0.1\\
0.2 & 0.5 & 0.3\\
0.1 & 0.3 & 0.4
\end{bmatrix}
\end{align*}$$
Suppose we produce,
$$\begin{align*}
x &= \begin{bmatrix}
x_{1}\\
x_{2}\\
x_{3}
\end{bmatrix}
\end{align*}$$
We want $d = \begin{bmatrix}d_{1}\\d_{2}\\d_{3}\end{bmatrix}$ "outside demand" left.
The total consumed is now $Cx$, so we are left with,
$$\begin{align*}
x-Cx &= d\\
(I-C)x &= d
\end{align*}$$
>[!theorem]
>If $C$ is a square matrix with non-negative entries, and each column sum is less than 1, then $I-C$ is invertible and the entries of $(I-C)^{-1}$ are non-negative.
>This means we can solve a Leontief equations $x = (I-C)^{-1}d$.
---
>[!proof]
>(Rough sketch)
>Recall that for a real number $r\in \mathbb{R}$ with $|r|<1$, then we have $\sum\limits_{n=0}^{\infty} = \frac{1}{1-r}$.
>We may claim that $(I-C)^{-1} = \sum\limits_{n=0}^{\infty}C^{n}$.
>Checking this,
>$$\begin{align*}(I-C)\sum\limits_{n=0}^{\infty}C^{n} &= \sum\limits_{n=0}^{\infty}C^{n} - \sum\limits_{n=1}^{\infty}C^{n}=I \end{align*}$$
>We need $\sum\limits_{n=0}^{\infty}C^{n}$ to converge, then this will be true.

