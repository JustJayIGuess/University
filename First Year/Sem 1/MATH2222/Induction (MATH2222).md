If we have a collection of statements $P(n)$, with $n\in \mathbb{N}$, we may use induction to prove all statements in $P$.
>[!theorem]
>*The Principle of Induction*
>Begin with $\left\{P(n)\right\}_{n\in \mathbb{N}}$ being the statements to prove.
>If the following hold, then for all $n\in \mathbb{N}$, $P(n)$ holds.
>- $P(0)$ is true
>- if $P(k)$ is true for any $k\in \mathbb{N}$, then $P(k+1)$ is true

We also have *strong induction*.
>[!theorem]
>We prove the following:
>- P(0) is true
>- For each $k\ge 0$, if $P(l)$ holds for all $l\in [0, k]$, then $P(k+1)$ holds.
>
>This is logically equivalent to ordinary induction.

>[!tip]
>In induction questions that are phrased as,
>$$\begin{align*}\sum\limits_{i=a}^{b}f(x),\end{align*}$$
>you can try guessing the formula by considering the analogous integral of $f(x)$.

# Examples of Induction

>[!example]
> Fix $q>2$. Then for all $n\in \mathbb{N}$, $n<q^{n}$.
> Let $P(n)$ be the statement that this is true for $n$.
> First, prove base case.
> $$\begin{align*}
> n &= 0,\\
> 0 < q^{0}&= 1
> \end{align*}$$
> So the statement is true for $n=0$.
> Now, suppose that $k<q^{k}$. We now must show that $k+1 < q^{k+1}$.
> $$\begin{align*}
> k &< q^{k}\\
> k+1<k+k &= 2k<qk<qq^{k}=q^{k+1}\\
> \therefore k+1 &< q^{k+1}
> \end{align*}$$
> We have therefore proven all $P(n)$.
> $$\begin{align*}
> \tag*{$\blacksquare$}
> \end{align*}$$

>[!example]
> If there is an injective function $f : J_{m} \longrightarrow J_{n}$ ($J_{k} = \left\{1,2,...,k\right\}$), then $m\le n$.
> We will prove this by induction on $n$.
> **Base case.**
> Consider first the base case $n=1$. We need to check that if $f : J_{m} \longrightarrow J_{1}=\left\{1\right\}$ is injective, then $m\le 1$.
> The only function that satisfies this is $f(x)=1$. It is now clear that the only way for this function to be injective is for $J_{m}$ to have one or less elements, i.e., $m\le 1$.
> **Induction step.**
> Now assume that this statement is true for $n=k$, i.e., if there is an injection $f : J_{m} \longrightarrow J_{k}$, then $m\le k$. We must now show that if there exists an injective function $f : J_{m} \longrightarrow J_{k+1}$, then $m\le k+1$.
> So, let $f : J_{m} \longrightarrow J_{k+1}(=\left\{1,2,3,...,k,k+1\right\})$ be injective. We will rewrite $J_{k+1}=J_{k}\cup \left\{k+1\right\}$.
> Now note that if $k+1$ is not in the image of $f$, then the function $f' : J_{m} \longrightarrow J_{k}$, $f'(x)=f(x)$ is injective. In this case, we have that $m\le k \le k+1$, i.e., $m\le k+1$.
> If $k+1$ is in the image of $f$, i.e., $f(i)=k+1$ for some unique $i\in J_{m}$ (as $f$ is injective).
> We want $i=m$, so we may change $f$ for convenience,
> $$\begin{align*}
> g : J_{m} \longrightarrow J_{k+1},\\
> g(x) &= \cases{f(x),\ x\ne i,\ x\ne m \\ f(i)=k+1,\ x=m \\ f(m),\ x=i}
> \end{align*}$$
> So, we may now consider the subsets of the domain and codomain without the largest functions. By the induction hypothesis, $m-1\le k$, therefore $m\le k+1$.
> $$\begin{align*}
> \ \tag*{$\blacksquare$}
> \end{align*}$$
---
>[!cor]
>If there is a bijection $f : J_{m} \longrightarrow J_{n}$, then $m=n$.
---
>[!proof]
>If $f$ is bijective then it is also injective, so we have that $m\le n$. However $f^{-1}$ is also injective, so $n\le m$. Therefore $n\le m\le n \Rightarrow m=n$.

>[!example]
> Prove that for all $n\ge 1$, $n^{5} - n$ is divisible by $10$.
> We will prove this by induction.
> **Base case.**
> $$\begin{align*}
> n&= 1\\
> 1^{5}-1&= 0\text{ divisible by 10}.
> \end{align*}$$
> We would also show the base case for $n=2$.
> **Inductive Step**
> Assume that $k^{5}-k$ is divisible by 10, and prove that $N=(k+1)^{5}-(k+1)$ is divisible by 10.
> $$\begin{align*}
> k+1 &= (k-1)+2\\
> N &= [(k-1)+2]^{5} - [(k-1)+2]\\
> &= (k-1)^{5}+10(k-1)^{4}+40(k-1)^{3}+80(k-1)^{2} + 80(k-1)+32-2-(k-1)\\
> &= (k-1)^{5}-(k-1)+10(...)
> \end{align*}$$
> We have prove $P(k+1)$ using $P(k-1)$.

>[!example]
> *The Coin Removal Game*
> We have a finite string of coins with no gaps; e.g., HTHHTH.
> If we see a head, then we may remove it and flip the two neighbours.
> ```
> HTHHTH
> HH_TTH
> _T_TTH
> _T_TH_
> _T_H__
> _T____
> ```
> For what starting positions can we find a play sequence that ends up with the empty set?
> 
> **Proposition:** the coin game is winnable if and only if the starting string has an odd number of heads.
> We will prove that starting with an odd number of heads allows us to win the game, and then that if there is an even number of heads it is impossible to win.
> 
> Suppose we have a string with an odd number of heads.
> If we have one head, we may trivially win by removing the head.
> First, find the first head along from the left and remove it.
> ```
> TTTHHTH...HTHT
> TTH_TTH...HTHT
> ```
> We now know that the substring to the left has one head.
> We also know that, since since the whole string was odd, when we removed the head and made the right substring even, flipping the coin to the right now has an odd number of heads.
> Now we have smaller substrings with odd numbers of heads.
> By the strong induction hypothesis, we can perform winning moves to remove all coins in each of the sub strings.
> 
> Now suppose the starting string has an even number of heads.
> Take any head and remove it. We are left with two strings, where one is even and one is odd. The odd substring may be solved, but the even substring will eventually reduce to some substring `HH` which cannot be solved.

>[!caution]
>We will prove that all horses are the same colour.
> **Base case.**
> If there is one horse, then all horses are the same colour.
> **Inductive step.**
> Suppose that any stable of $k$ horses have all the same colour.
> If we have a stable of size $k+1$, then we may make two separate subgroups of size $k$ which must all have the same colour. Therefore all the horses are the same colour.
> Therefore all horses are the same colour.
> 
> This actually doesn't work, as we have assumed implicitly that $n>2$, so our base case isn't sufficient.

>[!example]
> We will prove that player two in *the match game* always has a winning strategy by strong induction on the number of matches in pile $|A|=|B|$.
> **Base case.**
> If there is one match in each pile, player two trivially can win by taking the match in the opposite pile to player one.
> **Inductive step.**
> We assume that player two has a winning strategy whenever the game has size less than $k$.
> Now suppose a game with $k+1=|A|=|B|$ matches.
> Now if player one takes $n$ matches from pile $A$, then player two can take $n$ matches from pile B. We are now in a case that already has a winning strategy. Therefore player two can win for a pile of size $k+1$ given they can win for any pile $\le k$.
> Therefore player two can always win.

# Extensions of Induction
Suppose that the statements to be proven are indexed by pairs of integers $\left\{P(n,m)\right\}_{n,m>1}$ rather than by a sequence of integers $\left\{1,2,3,...\right\}$. This can be proven by *double induction*.
One can think about the statements in the following layout.
$$\begin{align*}
\begin{bmatrix}P(1,1) & P(1,2) & \cdots\\
P(2,1) & P(2,2) & \cdots\\
\vdots & \vdots & \ddots\end{bmatrix}
\end{align*}$$
One may begin with the bases cases $P(m,1)$ and $P(1,n)$ for all $m,n\in \mathbb{N}$, proven by regular induction or some other technique.
Then, as the inductive step, one may show that if $P(m, n-1)$ holds and $P(m-1,n)$ holds then $P(m,n)$.

>[!example] Example: Integer Partitions.
>Consider the number of solutions $(x_{1}, ..., x_{m})$ to the equation $x_{1}+x_{2}+x_{3}+...+x_{m}=n$ were $n\ge 0, x_{i}\ge 0$.
>The answer to this is $P(m,n) = \binom{n+m-1}{n}$.
---
>[!proof]
> This will be proven by double induction.
> **Base cases.**
> First, check base cases for $P(m,1)$.
> We have the equation $x_{1}+ x_{2}+ x_{3}+ ... + x_{m}=1$, which clearly has $m$ solutions.
> $$\begin{align*}
> P(m,1) &= \binom{m}{1}=m
> \end{align*}$$
> So the base cases hold for $P(m,1)$.
> Second, check base cases for $P(1,n)$.
> We have the equation $x_{1} = n$, which clearly has only one solution.
> $$\begin{align*}
> P(m,1) &= \binom{n}{n}=1
> \end{align*}$$
> Therefore both sets of base cases hold.
> **Inductive Step**
> If it is known that $P(m,n-1)=\binom{(n-1)+m-1}{n-1}$ and $P(m-1,n) = \binom{n+(m-1)-1}{n}$, we want to prove that $P(m,n) = \binom{m+n-1}{n}$.
> Looking at the second inductive hypothesis, consider the solutions where $x_{1}=0$. Then by the hypothesis we have that there are $\binom{n+m-2}{n}$. Now consider the remaining solutions, where $x_{1}$ is non-zero.
> Say that $(x_{1}, ..., x_{m})$ is a solution. Now consider the case where we reduce $x_{1}$ by one. We gain a new set of solutions $(y_{1}, ..., y_{m})$ for $y_{1}+...+y_{m} = n-1$, i.e., there is a bijection between X and these new solutions. So $|X| = P(m, n-1)$. So $P(m,n) = P(m,n-1)+P(m-1,n)$.
> However by using Pascal's triangle, this means that,
> $$\begin{align*}
> \binom{n+m-1}{n} &= \binom{n+m-2}{n-1} + \binom{n+m-2}{n}.\tag*{$\blacksquare$}
> \end{align*}$$
> 