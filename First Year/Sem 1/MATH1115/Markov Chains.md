>[!def]
>A *dynamical system* is a (finite) set of variables whose values change with time.
>The value of a variable at a given time is the *state*  of the variable and the vector of these is the *state vector*.
>
>>[!remark]
>>Typically we get from the state vector at $t$ to the state vector at $t+1$ by a multiplication by a matrix.

>[!example]
>Market shares.
>![[Markov Chains 2024-05-22 12.09.53.excalidraw]]
>Let $y_{1}(t)$ be the market share of 1 at time  $t$, and $y_{2}(t)$ be that of 2.
>Now suppose we have $y_{0} = \begin{bmatrix} \frac{1}{2} & \frac{1}{2} \end{bmatrix}$.
>Then,
>$$\begin{align*}
>y(t+1) &= Ay(t),\ A = \begin{bmatrix}0.8 & 0.1 \\ 0.2 & 0.9 \end{bmatrix}.\\
>y(t) &= A^{t}y(0).
>\end{align*}$$
>By computing this at a few points, it appears as if $y_{1}$ is getting smaller while $y_{2}$ gets bigger. This will stabilise at $\begin{bmatrix} \frac{1}{3} \\ \frac{2}{3} \end{bmatrix}$.

>[!def]
>A *probability vector* is a vector with entries that add to one.
>A *stochastic matrix* is a square matrix whose column vectors are probability vectors.

>[!def]
>A *markov chain* is a dynamical system where $y(0)$ is a probability vector and $y(t+1) = Py(t)$ for a stochastic matrix $P$.

>[!lemma]
>If $P$ is a stochastic matrix and $v$ is a probability vector, then $Pv$ is also a probability vector.
>
>>[!proof]
>>First, it is clear that $Pv$ has nonnegative entries, by the definition of matrix multiplication.
>>Now, check that the entries of $Pv$ add to one,
>>$$\begin{align*}
>>\sum\limits_{i}(Pv)_{i} &= \sum\limits_{i}\sum\limits_{j}P_{ij}v_{j}\\
>>&= \sum\limits_{j}\sum\limits_{i}P_{ij}v_{j}\\
>>&= \sum\limits_{j}(\sum\limits_{i}P_{ij})v_{j}\\
>>&= \sum\limits_{j}1v_{j}\\
>>&= 1
>>\end{align*}$$

>[!question]
>Do these markov chains always stabilise?
>
>>[!remark]
>>This is equivalent to asking whether all markov chains have an eigenvalue 1.
>
>>[!check] Solution.
>>No! We could, for example, have an alternating state.
>>$$\begin{align*}
>>P  &= \begin{bmatrix}0 & 1 \\ 1 & 0\end{bmatrix}\\
>> y(0) &= \begin{bmatrix}1 \\ 0\end{bmatrix}.
>>\end{align*}$$

>[!def]
>A stochastic matrix $P$ is *regular* if $P$ or some positive power of $P$ has all positive (and non-zero) entries.

>[!theorem]
>If $P$ is a regular stochastic matrix then,
>- there is a unique probability vector $q$ with $Pq=q$,
>- for any probability vector $v$, $\lim_{n \longrightarrow \infty}P^{n}v = q$,
>- $\lim_{n \longrightarrow \infty}P^{n} = Q$, where each column of $Q$ is $q$. We call this the *steady state vector* for $P$.
>- any other eigenvalue $\lambda_{i}\ne 1$ of $P$ has $|\lambda_{i}|<1$.
>
>>[!proof]
>>Can't find one!
>>Here's a good try:
>>
>>First, note that $\begin{bmatrix}1\\1\\\vdots\\1\end{bmatrix}$ is an eigenvector for the transpose of $P$, with $\lambda=1$. So 1 is an eigenvalue of $P$ as well.
>>If some $v$ has both positive and negative entries, then,
>>$$\begin{align*}
>>\sum\limits|(Pv)_{i}| &= \sum\limits_{i}\left|\sum\limits_{j}P_{ij}v_{j}\right|\\
>>&\le \sum\limits_{i}\sum\limits_{j}|P_{ij}v_{j}|\\
>>&= \sum\limits|v_{j}|
>>\end{align*}$$
>>So then the eigenvector with both positive and negative entries must have $\lambda\le 1$.
>>This proof goes on a bit to show that this inequality is strict if $P$ is regular.

>[!example] Example (cont.)
>We have $p(\lambda) = \lambda^{2} - 1.7\lambda + 0.7 = (\lambda-1)(\lambda-0.7)$.
>Take $\lambda=1$. Then we have the eigenspace spanned by $\begin{bmatrix}1 \\ 2\end{bmatrix}$. This is not a probability vector, but $\frac{1}{3}\begin{bmatrix} \frac{1}{3} \\ \frac{2}{3} \end{bmatrix}$ is one. This is our steady state vector.
>Take $\lambda = 0.7$. Then we have the eigenspace spanned by $\begin{bmatrix} \frac{1}{2} \\ \frac{-1}{2} \end{bmatrix}$. This cannot be a probability vector.
>We have $y(0) = \begin{bmatrix} \frac{1}{2} \\ \frac{1}{2} \end{bmatrix} = q + \frac{1}{3}v_{2}$. So then $y(n) = q + \frac{1}{3}0.7^{n}v_{2} \longrightarrow q$.

>[!def] Google PageRank Algorithm
>Fix some small $\epsilon>0$ (usually ~15%). Suppose a user goes from page to page in the following way:
>- If a page has $k$ links for $k>0$, then with probability $1-\epsilon$, they follow a randomly chosen link. With probability $\epsilon$, they pick a random page.
>- If a page has no links, they pick a random page.
>
>Now we can create an $n\times n$ matrix where $n$ is the number of websites.
>Then the Google matrix is a regular stochastic matrix.
>
>The steady state vector is the PageRank vector. So if a website is often visited, it will have a large probability in the PageRank.
