# Proof by Contradiction
>[!def]
>In *proof by contradiction*, we assume that the result is false, derive a contradiction, and finally conclude that the result is true.

>In MATH2222, we should avoid this technique when possible, as it doesn't give as much insight into the underlying structure of the argument. An example of when contradiction should be used is in proving irrationality.

>[!proof]
>Prove that $\sqrt{2}$ is irrational.
>We will use *proof by contradiction* to prove that it is not possible for $\sqrt{2}$ to be rational.
>Begin by taking $a,b\in \mathbf{R}, b\neq 0$ where $a$ and $b$ have no common factors, such that the fraction $\frac{a}{b}$ is in simplest form.
>Now suppose that $\sqrt{2}$ is rational, and can be represented by this ratio $\frac{a}{b}$.
>$$\begin{align*}\frac{a}{b} &= \sqrt{2}.\end{align*}$$
>Squaring both sides and isolating $a$,
>$$\begin{align*}\frac{a^{2}}{b^{2}} &= 2\\a^{2} &= 2b^{2}\end{align*}$$
>$a^{2}$ is equal to two times an integer, and so is even. This further implies that $a$  is even. Therefore, let $a = 2k$ for some $k\in \mathbf{Z}$.
>$$\begin{align*}(2k)^{2} &= 2b^{2}\\4k^{2}&= 2b^{2}\\2k^{2} &= b^{2}\end{align*}$$
>This now indicates that $b^{2}$, and therefore also $b$, is even. However if $a$ and $b$ are both even, then they possess a common factor.
>This contradicts the initial assumption, therefore $\sqrt{2}$ is irrational.
>$$\ \tag*{$\blacksquare$}$$
# Proving the Contrapositive
>[!def]
>When *proving the contrapositive*, we begin with a statement that we want to prove in the form of $A \Rightarrow B$. Since the statement $A \Rightarrow B$ is logically equivalent to $\neg B \Rightarrow \neg A$, we instead move forward by proving that $\neg B \Rightarrow \neg A$.


Begin the proof by considering the inequalities defined by the bounds $a$ and $b$.
$$
\begin{align*}
|f+g| &< a\\
|fg| &< b
\end{align*}
$$
Note that if $fg \ge 0$, then $fg = |fg| < b$, and that if $fg \le 0$, then $fg < |fg| < b \Rightarrow fg < b$. Therefore it is true in general that $fg < b$. This further means that $fg + k = b\Rightarrow fg = b - k$ for some bounded, strictly positive function $k:X\longrightarrow Y$.\\
Now take the square of the first inequality.
$$
\begin{align*}
|f+g|^2 &< a^2\\
f^2 + 2fg + g^2 &< a^2
\end{align*}
$$
Substituting $fg = b - K$,
$$
\begin{align*}
f^2 + 2(b - k) + g^2 < a^2\\
f^2 + g^2 < a^2 + 2k - 2b
\end{align*}
$$
Adding to this two times the second inequality,
$$
\begin{align*}
f^2 + 2|fg| + g^2 < a^2 + 2k - 2b + 2b\\
|f|^2 + 2|fg| + |g^2| < a^2 + 2k\\
(|f| + |g|)^2 < a^2 + 2k
\end{align*}
$$
All terms are positive, so,
$$
\begin{align*}
|f| + |g| < \sqrt{a^2 + 2k}.
\end{align*}
$$
The function $k$ is bounded by definition, so $|k| < c\Rightarrow k < c$ (as $k$ is strictly positive) for some maximum value $c$. Therefore the right hand side of the above inequality may be replaced by $\sqrt{a^2 + 2c}$, giving a constant uppr bound of $|f| + |g|$.

Now, if $f$ were unbounded, then $|f|$ would be unbounded in the positive direction. However, as $|g|$ may only add to this value in $|f| + |g|$, it can be concluded that $|f|+|g|$ must also be unbounded. The same reasoning can be applied to $g$, and so if $f$ or $g$ are unbounded then $|f| + |g|$ must be unbounded also. If both $f$ and $g$ are bounded then $|f| + |g|$ is clearly bounded.\\
Therefore, as $|f| + |g|$ is bounded as shown above, then both $f$ and $g$ must be bounded also.\qed


Begin the proof by considering the inequalities defined by the bounds $a$ and $b$.
$$
\begin{align*}
|f+g| &< a\\
|fg| &< b
\end{align*}
$$
Note that if $fg \ge 0$, then $fg = |fg| < b$, and that if $fg \le 0$, then $fg < |fg| < b \Rightarrow fg < b$. Therefore it is true in general that $fg < b$. This further means that $fg + k = b\Rightarrow fg = b - k$ for some bounded, strictly positive function $k:X\longrightarrow Y$.\\
Now take the square of the first inequality.
$$
\begin{align*}
|f+g|^2 &< a^2\\
f^2 + 2fg + g^2 &< a^2
\end{align*}
$$
Substituting $fg = b - K$,
$$
\begin{align*}
f^2 + 2(b - k) + g^2 < a^2\\
f^2 + g^2 < a^2 + 2k - 2b
\end{align*}
$$
Adding to this two times the second inequality,
$$
\begin{align*}
f^2 + 2|fg| + g^2 < a^2 + 2k - 2b + 2b\\
|f|^2 + 2|fg| + |g^2| < a^2 + 2k\\
(|f| + |g|)^2 < a^2 + 2k
\end{align*}
$$
All terms are positive, so,
$$
\begin{align*}
|f| + |g| < \sqrt{a^2 + 2k}.
\end{align*}
$$
The function $k$ is bounded by definition, so $|k| < c\Rightarrow k < c$ (as $k$ is strictly positive) for some maximum value $c$. Therefore the right hand side of the above inequality may be replaced by $\sqrt{a^2 + 2c}$, giving a constant uppr bound of $|f| + |g|$.

Now, if $f$ were unbounded, then $|f|$ would be unbounded in the positive direction. However, as $|g|$ may only add to this value in $|f| + |g|$, it can be concluded that $|f|+|g|$ must also be unbounded. The same reasoning can be applied to $g$, and so if $f$ or $g$ are unbounded then $|f| + |g|$ must be unbounded also. If both $f$ and $g$ are bounded then $|f| + |g|$ is clearly bounded.
Therefore, as $|f| + |g|$ is bounded as shown above, then both $f$ and $g$ must be bounded also.

