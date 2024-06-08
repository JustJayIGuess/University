# Partitions
>[!def]
>A partition of $[a,b]$ is a sequence $a=t_{0}<t_{1}<\cdots<t_{n}=b$.
>I.e., a subdivision of an interval.
>E.g., $[0,10]$ can be partitioned as $0<1<2<3<4<6<9<10$

# Summation of Areas
Consider a function $f$ which is bounded on $[a,b]$.
Now let $P$ be a partition of $[a,b]$, so we have a collection of intervals $[t_{i},t_{i+1}]$ where $f$ is bounded. We therefore have a bounded, non-empty set $F_{i} = \left\{f(x) \mid x\in[t_{i}, t_{i+1}]\right\}$ which must have a $\inf F_{i} = m_{i}$ and $\sup F_{i} = M_{i}$. We can then draw a rectangle from the x-axis to entirely below the graph of $f$ with area $m_{i}(t_{i+1}-t_{i})$ and another that entirely includes $f$ in the interval $t_{i+1}-t_{i}$ with area $M_{i}(t_{i+1}-t_{i})$.

>[!def]
>The *lower sum* for $f,P$ is,
>$$\begin{align*}L(f,P) = \sum\limits_{i=1}^{n}m_{i}(t_{i}-t_{i-1}) = \sum\limits_{i=1}^{n}\inf\left\{f(x) \mid x\in[t_{i,}t_{i-1}]\right\}(t_{i}-t_{i-1})\end{align*}$$
>The *upper sum* for $f,P$ is the same, however using the supremum, and is denoted $U(f,P)$.

Note that, across all possible partition, the set of possible upper or lower sums is a bounded set; bounded below by the lower sum of the whole interval and bounded above by the upper sum of the whole interval. So each of these sets have their own supremum and infimums.

>[!def]
>A bounded function $f$ is *integrable* on $[a,b]$ if,
>$$\begin{align*}\sup\left\{L(f,P)\right\}=\inf\left\{U(f,P')\right\}.\end{align*}$$
>If $f$ is integrable on $[a,b]$ we can then write,
>$$\begin{align*}\int_{a}^{b}f &= \sup\left\{L(f,P)\right\} = \inf\left\{U(f,P')\right\}.\end{align*}$$

# Integrability
>[!example]
>Show that the integral,
>$$\begin{align*}\int_{0}^{1}2x,\end{align*}$$
>exists. On $[0,1]$ $f$ has infimum 0 and supremum 2, so if the integral exists, it lies between 0 and 2.
>Take a partition $P_{2} = \left\{0, \frac{1}{2}, 1\right\}.$
>Then we have,
>$$\begin{align*}
L(2x,P_{2}) &= (0)\left(\frac{1}{2}\right) + (1)\left(\frac{1}{2}\right) = \frac{1}{2}\\
U(2x,P_{2}) &= (1)\left(\frac{1}{2}\right) + (2)\left(\frac{1}{2}\right) = \frac{3}{2}.
\end{align*}$$
> 
> First, we guess that the integral is equal to $1$. We will now show that for any $\epsilon>0$, we can find a partition $P_{\epsilon}$ such that $|L(f,P_{\epsilon})-1|<\epsilon$ and $|U(f,P_{e})-1|<\epsilon$.
> First, we choose $P_{n} = \left\{0,\frac{1}{n},\frac{2}{n},\cdots,1\right\}$. Then we have,
> $$\begin{align*}
> L\left(2x,P_{n}\right)&= 0\left(\frac{1}{n}\right) + \frac{2}{n}\left(\frac{1}{n}\right) + \cdots + \frac{2(n-1)}{n} \left(\frac{1}{n}\right)\\
> &= 2\left(\frac{1}{n} + \frac{2}{n} + \cdots + \frac{n-1}{n}\right)\left(\frac{1}{n}\right)\\
> U\left(2x, P_{n}\right) &= 2\left(\frac{1}{n} + \frac{2}{n} + \cdots + \frac{n-1}{n}+1\right)\left(\frac{1}{n}\right)\\
> \\
> U(2x,P_{n})-L(2x,P_{n}) &= \frac{2}{n}\\
> \lim_{n \longrightarrow \infty} \frac{2}{n} &= 0\\
> \therefore \sup\{L(f,P)\} &= \inf\{U(f,P)\}.
> \end{align*}$$
> So $2x$ is integrable on $[0,1]$.


>[!remark]
>Some, **but not all** functions are integrable.
>There is no integral for the function,
>$$\begin{align*}f(x) &= \begin{cases}1 & x\in \mathbb{Q} \\ 0 & x\not\in\mathbb{Q}\end{cases}\end{align*}$$
>This function has upper sum $b-a$ and lower sum $0$ regardless of the partition chosen (as $\mathbb{Q}$ is dense in $\mathbb{R}$), so as long as $b\ne a$, then $\sup\{L(f,P)\} \ne \inf\{U(f,P)\}$.

---

>[!theorem]
>Uniformly continuous functions that are integrable on $[a,b]$ are integrable on $[a,b]$.

>[!proof]
>Take $f$ to be a function that is uniformly continuous on $[a,b]$.
>We would like to show that $\sup\{L(f,P)\} = \inf\{U(f,P)\}$, but to do this, it is sufficient to find some special partitions that make the two arbitrarily close.
>
>Observe that for any partition $P$ of $[a,b]$, we have that,
>$$\begin{align*}U(f,P)-L(f,P) &= \sum\limits_{i}(t_{i}-t_{i-1})(M_{i} - m_{i}).\end{align*}$$
>Now fix $\epsilon' > 0$. As $f$ is uniformly continuous, we can get a $\delta$ such that $$0<|x-y|<\delta \Rightarrow |f(x)-f(y)| < \frac{\epsilon'}{2(b-a)}.$$
>Now we will choose $P$ such that $|t_{i} - t_{i-1}| < \delta$. Then we have $|f(t_{i}) - f(t_{i-1})|<\frac{\epsilon'}{2(b-a)}$ for any $\epsilon'$ that generated the $\delta$.
>$$\begin{align*}
\sum\limits_{i=1}^{n} (M_{i} - m_{i})(t_{i}-t_{i-1}) &< \sum\limits_{i=1}^{n}\left(\frac{\epsilon'}{2(b-a)}\right)\delta\\
&= \frac{\epsilon'}{2(b-a)}\sum\limits_{i-1}^{n}\delta\\
&<\frac{\epsilon'}{2(b-a)}(b-a)\\
&= \frac{\epsilon'}{2}<\epsilon'\\
\therefore U(f,P) - L(f,P) &< \epsilon'
\end{align*}$$
>Therefore $f$ is integrable.

>[!def]
>A $P'$ *refinement* of $P$ if $P'$ has all the points in $P$, with potentially some more points.

>[!lemma]
>If $P'$ is a refinement of $P$, then $U(f,P')\le U(f, P)$ and $L(f,P')\ge L(f,P)$.

>[!lemma]
>Any two partitions of $[a,b]$ admit a common refinement.

>[!theorem]
>Due to the previous lemma, we may choose $P=P'$ and will still always be able to show integrability of an integrable function.

>[!remark]
>If we have a sequence of successive refinements $S_{P} = P^{1},S^{2}, \cdots$, then,
>$$\begin{align*}
\left\{U(f,P^{n}\right\}\text{ is non-increasing},\\
\left\{L(f,P^{n}\right\}\text{ is non-decreasing.}
\end{align*}$$

>[!theorem]
>If $\left\{a_n\right\}$ is non-increasing and bounded below, then $\left\{a_{n}\right\}$ converges.
>
>>[!proof]
>>We will show that $\lim_{n\rightarrow \infty}a_{n} = \inf\{a_{n}\}=: \alpha$.
>>Note that the upper bound will be $a_{0}$, as the sequence is non-increasing. So the sequence is bounded above and below.
>>
>>Fix $\epsilon>0$.
>>We would like to show that there is $N>0$ such that $n>N \Rightarrow |a_{n} - \alpha|<\epsilon$.
>>Since $\alpha$ is an infimum, there is some $a_{n}$ such that $|a_{n}-\alpha|<\epsilon$. Since $\left\{a_{n}\right\}$ is non-increasing, $a_{k}\le a_{n}$ for all $k>n$. So then for all $k>n$, $|a_{k}-\alpha|<\epsilon$.
>
>>[!corollary]
>>For any sequence $P^{i}$ of successive refinements, $\left\{U(f,P^{i}\right\}$ converges.
>
>>[!proof]
>>$\left\{U(f,P^{i})\right\}$ is bounded below by the lower sum for all $i$.

# Bolzano-Weierstrass Theorem
>[!theorem]
>Every bounded sequence has a convergent subsequence.
>
>>[!proof]
>>We could show this by showing that every sequence either a non-increasing or non-decreasing subsequence, however we will not use this proof.
>>
>>First, take some bounded sequence $\left\{a_n\right\}$. We have an infimum and supremum, so we can define $I=[\inf\{a_{n}\}, \sup\{a_{n}\}]$.
>>Now, we inductively define a sequence of nested intervals.
>>Given $I_{n}$, divide it in half. One of these halves must have infinitely many points. If both have infinitely many points, then choose either one.
>>Set this interval to be $I_{n+1}$.
>>Now (as proved in a homework question), there must exist some $\alpha$ that is in every $I_{n}$, as $I_{n}$ is a sequence of nested closed intervals.
>>
>>Now, we will define a subsequence that converges to $\alpha$ by letting $b_{i}$ be some element in $I_{i}$. Upon doing this, we will also remove all points $a_{n}$ with $n<i$ to preserve ordering of our subsequence. As we are removing a finite number of elements from an infinite set, we will not run out of points.
>>As the length of the interval $I_{n}$ is $\frac{1}{2^{n-1}}(l(I_{1}))$, so our points get closer and closer, so our subsequence converges to $\alpha$.


