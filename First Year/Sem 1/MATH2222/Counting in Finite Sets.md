Suppose we have some finite set $S$. How can we find $|S|$?

- *The Rule of Sum*:
$$\begin{align*}
\text{If }S = \bigsqcup_{i}s_{i},\ |S| = \sum\limits_{i}|s_i|
\end{align*}$$
- *Rule of Product*:
$$\begin{gather*}
\text{Let }T\text{ be a set whose elements can be described}\\
\text{by a series of indepenedent choices,}\\
s_{1},s_{2},...,s_{r},\\
\text{where step }s_{i}\text{can be performed on }r_{i}\text{ elements.}\\
\text{Then,}\\
|S| = \prod_{i}r_{i}
\end{gather*}$$
>[!example]
>Define that $[k] = \left\{1,2,...,k\right\}$, and let $S$ be a finite set.
>We might be interested in sets such as,
>$$\begin{align*}\left\{f : [k]\longrightarrow S \mid f\text{ is injective}\right\} \\ \left\{f : [k] \longrightarrow S \mid f\text{ is surjective}\right\} \\ \left\{f : [k] \longrightarrow S \mid f\text{ is bijective}\right\}\end{align*}$$

A function $f : [k] \longrightarrow S$ is just an indexed list (sometimes called an *arrangement*) of elements of $S$.
$$\begin{align*}
f \leftrightarrow f(1),f(2),...,f(k)
\end{align*}$$
If $f$ is injective, then this list should have no repetitions.

>[!theorem]
>Let $S$ be a finite set with $n$ elements.
>The number of injective functions from $[n]$ to $S$ (the number of arrangements of $k$ elements in $S$ without repetition) is,
>$$\begin{align*}n(n-1)(n-2)\cdots(n-k+1).\end{align*}$$

>[!cor]
>The number of bijections from $f : [n] \longrightarrow [n]$ is $n! = n(n-1)(n-2)\cdots (2)(1)$.

>[!def]
>A bijection $f : [n] \longrightarrow [n]$ is called a permutation.

>[!proof]
>To count the number of injective functions $f : [k] \longrightarrow S$, $|S|=n$, we use the rule of products.
>Observe that there are $n$ choices for what $f(1)$ will map to. However $f$ is injective, so now there are only $n-1$ choices for $f(2)$. By the rule of products, we therefore have the formula given above.

>[!remark]
>If we do not require injectivity, then there will be $n$ choices for each set, so the number of functions $f : [k] \longrightarrow S,\ |S|=n$ is $n^{k}$.

>[!def]
>A *selection* of $k$ elements from the set $[n]$ is a $k$-element subset of $[n]$.
>E.g., $\left\{1,3,4\right\}$ is a selection of $[5]$.

$$\begin{gather*}
\text{Let }T_{k}^{n} = \left\{A\subset [n] \mid |A|=k\right\}.\\
\text{The cardinality of }T_{k}^{n}\text{, that is, the number of}\\k\text{-element subsets of an }n\text{-element set is written},\\
n\choose{k}\\
\text{If }k<0\text{ or }k>n,\\
{n\choose{k}} = 0
\end{gather*}$$

>[!theorem]
>Let $k,n$ be integers, with $0\le k\le n$.
>Then,
>$$\begin{align*}{n\choose k} &= \frac{n!}{k!(n-k)!}\end{align*}$$

>[!proof]
>We will relate the number of selections to the number of arrangements in two ways.
>We first aim to count the number of arrangements of $k$-element sets in an $n$ element set. This is already known to be $n(n-1)(n-2)\cdots(n-k+1)$.
>So first, choose the subset, which has $n\choose k$ possibilities. Then we can order this set in $k!$ different ways.
>These must be equal, as they both count the same set. So,
>$$\begin{align*}n(n-1)\cdots(n-k+1) &= {n\choose k}k! \\ {n\choose k} &= \frac{n(n-1)\cdots{(n-k+1)}}{k!} \end{align*}$$
>Which simplifies to the formula above.

>[!remark]
>This is an example of a combinatorial proof - we count the same set in two ways and deduce that the expressions giving this count are equal.


# Binomial Coefficients
>[!def]
>The numbers $n\choose k$ are also called the *binomial coefficients*. I.e.,
>$$\begin{align*}(x+y)^{n} &= {n\choose 0}x^{n}y^{0} + {n\choose 1}x^{n-1}y^{1} + \cdots + {n\choose n-1}x^{1}y^{n-1} + {n\choose n}x^{0}y^{n} \\ &= \sum\limits_{i=0}^{n} \binom{n}{i}x^{i}y^{n-i} \end{align*}$$

>[!lemma]
>$$\begin{align*}{n\choose k} &= {n\choose n-k}\end{align*}$$

>[!proof]
>1. By Bijection.
>Observe that we have a bijection $f : \text{k-element subsets} \longrightarrow \text{(n-k)-element subsets}$ which is bijective, defining $f$ to be the function that sends a subset to its compliment. We know this is bijective because $f$ is its own inverse.
>2. Algebraically
>$$\begin{align*}{n\choose k} &= \frac{n!}{k!(n-k)!} = \frac{n!}{(n-k)!k!} = {n\choose n-k}\end{align*}$$
>3. By Analogy
>Note that another appearance of $n\choose k$ is in counting lattices paths. This is a problem setup where we must follow some path to a specified point with only moves to the right or upwards allowed.
>We will first prove that the number of lattice paths from the origin to the point $(k,n-k)$ is $n\choose k$.
>We have a path that is $k+n-k = n$ long. So we can choose which of these must be upward steps. Then this will be $n\choose k$.
>We can equivalently ask which of these should be steps to the right, which will give $n\choose n-k$.
>4. Pascal's Recursion
>$$\begin{align*}{n\choose k} &= {n-1\choose k} + {n-1\choose k-1}\end{align*}$$
>This can be proven by lattice paths. At the penultimate step of the path, we could either be at $(k-1, n)$ or $(k, n-1)$. These have $k-1\choose n$ and $k\choose n-1$ steps each.
>We can also prove this by asking how many subsets do not include the largest element of the set. Then we supplement this by adding the number of subsets that don't include this element.

Now we may prove the binomial coefficient theorem.

>[!proof]
>When multiplying out the factors, to get something of the form $x^{i}y^{n-i}$, we must choose $i$ $x$'s and $n-i$ $y$'s. Then there are $\binom{n}{i}$ ways to do this.

>[!theorem]
>*Stars and Bars.*
>With repetition allowed, there are $\binom{n+k-1}{k-1}$ ways to select $n$ objects from $k$ types.
>This is also equal to the number of non-negative integer solutions to the equation,
>$$\begin{align*}x_{1} + x_{2} + \cdots + x_{k}&= n.\end{align*}$$

>[!proof]
>We will model the non-negative integer solutions to the equation given as an arrangement of "stars and bars" as follows.
>![[Counting in Finite Sets Stars and Bars.excalidraw]]

# Combinatorial Proofs
>[!example]
>*The chairperson identity*
---
>[!lemma]
>$$\begin{align*}k \binom{n}{k} &= n \binom{n-1}{k-1}\end{align*}$$
---
>[!proof]
>Think about choosing a committee of $n$ applicants and appointing a chair of that committee.
>One way to do this is to first choose the committee, for which there are $\binom{n}{k}$ ways to do this, and then there are $k$ ways to choose the chair, so we have $k \binom{n}{k}$.
>Another way to do this is to first choose the chair, for which there are $n$ ways to do this, and then there are $\binom{n-1}{k-1}$ ways to fill out the rest of the committee. So we have $n \binom{n-1}{k-1}$. These must therefore be equal.
>$$\begin{align*}k \binom{n}{k} &= n \binom{n-1}{k-1}\end{align*}$$

>[!example]
>*Sums of Rows of Pascal's Triangle*
---
>[!lemma]
>$$\begin{align*}\sum\limits_{i=0}^{n} \binom{n}{i} &= 2^{n}\end{align*}$$
---
>[!proof]
>If we consider expanding the binomial $(1+1)^{n}$, we can see that we will get the sum of a row of pascal's triangle. However we also have $(1+1)^{n} = 2^{n}$
---
>[!proof]
>If $S$ has $n$ elements, then $\mathcal{P}(S)$ has $2^{n}$ elements. We can also count powerset of $S$ by the size of its elements, so there are $\binom{n}{0}$ elements of size 0, $\binom{n}{1}$ elements of size 1, etc.

>[!example]
>*Sum of Diagonals of Pascal's Triangle*
---
>[!lemma]
>$$\begin{align*}\sum\limits_{i=0}^{n}\binom{i}{k} &= \binom{n+1}{k+1}\end{align*}$$
---
>[!proof]
>**Exercise**
