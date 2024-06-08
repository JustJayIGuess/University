$$\begin{align*}
&\begin{bmatrix}1 & 2 & 3 & 2 & 1\\
-1 & -1 & -2 & -2 & 1\\
2 & 5 & 7 & 4 & 4\\
1 & 3 & 4 & 2 & 2\end{bmatrix}\\
R_{2} &= R_{1} + R_{2}\\
&\sim\begin{bmatrix}1 & 2 & 3 & 2 & 1\\
0 & 1 & 1 & 0 & 2\\
2 & 5 & 7 & 4 & 4\\
1 & 3 & 4 & 2 & 2\end{bmatrix}\\
R_{3} &= R_{3} - 2R_{1}\\
&\sim\begin{bmatrix}1 & 2 & 3 & 2 & 1\\
0 & 1 & 1 & 0 & 2\\
0 & 1 & 1 & 0 & 2\\
1 & 3 & 4 & 2 & 2\end{bmatrix}\\
R_{4} &= R_{4} - R_{1}\\
&\sim\begin{bmatrix}1 & 2 & 3 & 2 & 1\\
0 & 1 & 1 & 0 & 2\\
0 & 1 & 1 & 0 & 2\\
0 & 2 & 2 & 0 & 3\end{bmatrix}\\
\text{Swap }&R_{2},\ R_{4}\\
&\sim\begin{bmatrix}1 & 2 & 3 & 2 & 1\\
0 & 2 & 2 & 0 & 3\\
0 & 1 & 1 & 0 & 2\\
0 & 1 & 1 & 0 & 2\end{bmatrix}\\
R_{4} &= R_{3} - R_{4}\\
&\sim\begin{bmatrix}1 & 2 & 3 & 2 & 1\\
0 & 2 & 2 & 0 & 3\\
0 & 1 & 1 & 0 & 2\\
0 & 0 & 0 & 0 & 0\end{bmatrix}\\
R_{3} &= 2R_{3} - R_{2}\\
&\sim\begin{bmatrix}1 & 2 & 3 & 2 & 1\\
0 & 2 & 2 & 0 & 3\\
0 & 0 & 0 & 0 & 1\\
0 & 0 & 0 & 0 & 0\end{bmatrix}\\
R_{1} &= R_{1} - R_{2}\\
&\sim\begin{bmatrix}1 & 0 & 1 & 2 & -2\\
0 & 2 & 2 & 0 & 3\\
0 & 0 & 0 & 0 & 1\\
0 & 0 & 0 & 0 & 0\end{bmatrix}\\
R_{2} &= R_{2} - 3R_{3}\\
&\sim\begin{bmatrix}1 & 0 & 1 & 2 & -2\\
0 & 2 & 2 & 0 & 0\\
0 & 0 & 0 & 0 & 1\\
0 & 0 & 0 & 0 & 0\end{bmatrix}\\
R_{1} &= R_{1} + 2R_{3}\\
&\sim\begin{bmatrix}1 & 0 & 1 & 2 & 0\\
0 & 2 & 2 & 0 & 0\\
0 & 0 & 0 & 0 & 1\\
0 & 0 & 0 & 0 & 0\end{bmatrix}\\
R_{2} &= \frac{1}{2}R_{2}\\
&\sim\begin{bmatrix}1 & 0 & 1 & 2 & 0\\
0 & 1 & 1 & 0 & 0\\
0 & 0 & 0 & 0 & 1\\
0 & 0 & 0 & 0 & 0\end{bmatrix}
\end{align*}$$