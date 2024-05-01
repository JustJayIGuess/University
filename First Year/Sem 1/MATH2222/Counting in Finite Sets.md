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

>[!lemma]
>$$\begin{align*}k \binom{n}{k} &= n \binom{n-1}{k-1}\end{align*}$$

>[!proof]
>Think about choosing a committee of $n$ applicants and appointing a chair of that committee.
>One way to do this is to first choose the committee, for which there are $\binom{n}{k}$ ways to do this, and then there are $k$ ways to choose the chair, so we have $k \binom{n}{k}$.
>Another way to do this is to first choose the chair, for which there are $n$ ways to do this, and then there are $\binom{n-1}{k-1}$ ways to fill out the rest of the committee. So we have $n \binom{n-1}{k-1}$. These must therefore be equal.
>$$\begin{align*}k \binom{n}{k} &= n \binom{n-1}{k-1}\end{align*}$$

---

>[!example]
>*Sums of Rows of Pascal's Triangle*

>[!lemma]
>$$\begin{align*}\sum\limits_{i=0}^{n} \binom{n}{i} &= 2^{n}\end{align*}$$

>[!proof]
>If we consider expanding the binomial $(1+1)^{n}$, we can see that we will get the sum of a row of pascal's triangle. However we also have $(1+1)^{n} = 2^{n}$

>[!proof]
>If $S$ has $n$ elements, then $\mathcal{P}(S)$ has $2^{n}$ elements. We can also count powerset of $S$ by the size of its elements, so there are $\binom{n}{0}$ elements of size 0, $\binom{n}{1}$ elements of size 1, etc.

---

>[!example]
>*Sum of Diagonals of Pascal's Triangle*

>[!lemma]
>$$\begin{align*}\sum\limits_{i=0}^{n}\binom{i}{k} &= \binom{n+1}{k+1}\end{align*}$$

>[!proof]
>**Exercise**

# Motivational Problems
1. How many *derangements* (arrangements where no element is in its initial position) are there in the set of permutations of an $n$ element set.
2. Roll a six-sided die $n$ times. How likely are we to have rolled each number at least once.
3. The Euler totient function $\phi(m)$ is the number of positive integers $k$ with $1\le k\le m$ that are relatively prime to $m$, where $m$ is a positive integer. How can we compute $\phi(m)$?

All three of these problems use a concept called the *inclusion-exclusion* principle.

## Euler's Totient Function
$$\begin{align*}
\phi(m) &= \left|\left\{k \mid 1\le k\le m,\ gcd(k,m)=1\right\}\right|
\end{align*}$$
If $m=p$ is prime, then $\phi(p) = p-1$.
If $m = p^{r}$, then note that all of $1\le k\le m$ are coprime with $m$ except the multiples of $p$. So then $\phi(p) = p^{r} - \frac{p^{r}}{p} = p^{r} - p^{r-1}$.
If $m=p^{r}q^{s}$ for distinct primes $p,q$, then we have,
$$\begin{align*}
\phi(m) &= m - (\text{multiples of }p) - (\text{multiples of }q) + (\text{multiples of }p\text{ and }q)\\
&= m - \frac{m}{p} - \frac{m}{q} + \frac{m}{pq},
\end{align*}$$
noting that we have to correct for double-counting multiples of $pq$.

## Derangements of an $n$-element set.
>[!def]
>A *derangement* of a set is an arrangement where no element is fixed.

>[!question]
>Is this related to the orbit of the group $S_{n}$?

>[!proof]
> We would now like to count the number of permutations of an $n$-element set $X = \left\{1,2,\cdots n\right\}$ such that no $i\in S$ is in position $i$.
> For $i=1,\cdots,n$, let $A_{i} = \left\{\text{permutations that fix }i\right\}$. By definition, a derangement is a permutation that is not in any of $A_{1},\cdots, A_{n}$.
> So we aim to find $|U - \bigcup_{i=1}^{n}A_{i}|$.
> 
> We must then compute $|\bigcap_{i\in S}A_{i}|$ for some $S\subset \left\{1,\cdots,n\right\}$. We then fix the $|S|$ points and permute the remaining. So then,
> $$\begin{align*}
> \left|\bigcap_{i\in S}A_{i}\right| &= (n-|S|)!
> \end{align*}$$
> **Note that this doesn't depend on $S$, but only on $|S|$; this is useful!**
> 
> Using inclusion-exclusion,
> $$\begin{align*}
> |U-\bigcup_{i=1}^{n}A_{i}| &= \sum\limits_{S\subset\left\{1,\cdots,n\right\}}(-1)^{|S|}(n-|S|)!\\
> &= \sum\limits_{k=0}^{n}(-1)^{k}\binom{n}{k}(n-k)!\\
&= \sum\limits_{k=0}^{n}(-1)^{k} \frac{n!}{k!}\\
&= n!\sum\limits_{k=0}^{n}\frac{(-1)^{k}}{k!}
> \end{align*}$$
> So then the proportion of permutations is $\sum\limits_{k=0}^{n}\frac{(-1)^{k}}{k!}$, which approaches $\frac{1}{e}$ as $n\longrightarrow \infty$. 

# Inclusion-Exclusion
>[!def]
>The *inclusion-exclusion* principle is commonly used in the following scenarios:
>- Finding $|(A\cup B)^{C}| = |U| - |A\cup B|$
>- Finding $|A\cup B|$
>The principle states the following.
>$$\begin{align*}
|U-(A\cup B)| &= |U| - |A|-|B|+|A\cap B|\\
|U-(A\cup B\cup C)| &= |U| - |A| - |B| - |C|\\&+ |A\cap B| + |A\cap C| + |B\cap C|\\&- |A\cap B\cap C|
\end{align*}$$
>In general, given a universe $U$ and subsets $A_{1},\cdots,A_{n}$, the number $N$ of elements of $U$ that are not in any of $A_{1},\cdots,A_{n}$ is,
> $$\begin{align*}
> \sum\limits_{S\subset \left\{1,2,\cdots,n\right\}}(-1)^{|S|}\left|\bigcap_{i\in S}A_{i}\right|
> \end{align*}$$

>[!proof]
>We need to show that each $x$ belonging to none of the $A_{i}$ contributes 1 to the sum, and each $x$ belonging to at least one of the $A_{i}$ contributes 0.
> Note that any $x\in U-(\bigcup_{i=1}^{n}A_{i})$ only contributes to the $S=\varnothing$ term, showing the first part of the proof.
> Now suppose $x$ belongs to at least one of $A_{i}$. Let $T\subset\left\{1,2,\cdots n\right\}$ be the indices $T = \left\{i \mid x\in A_{i}\right\}$.
> In the formula, $x$ is counted as $\pm 1$ in every subset of $T$.
> $x$ contributes 1 when $|S|$ even and $-1$ when $|S|$ odd. So the total contribution of $x$ to the formula is,
> $$\begin{align*}
> \sum\limits_{s\subset T}(-1)^{|S|} &= \sum\limits_{k=0}^{|T|}(-1)^{k}\binom{|T|}{k}
> \end{align*}$$
> Now note that this is the binomial expansion of,
> $$\begin{align*}
> (x+y)^{|T|}\vert_{x=1,y=-1} &= (1-1)^{|T|} = 0.
> \end{align*}$$
> Which proves the second part of the proof.
> $$\begin{align*}
> \ \tag*{$\blacksquare$}
> \end{align*}$$

>[!remark]
>This principle is most useful when the sizes of intersection are much easier to compute than sizes of unions.

---

>[!question]
>How many  surjective functions are there from $X=\{1,\cdots,k\}$ to $Y=\{1,\cdots,n\}$.

>[!proof]
>Recall that there are $n^{k}$ possible functions.
>Consider the functions that are not surjective.
>So let $A_{i} = \left\{f : X \longrightarrow Y \mid i\not\in \text{image}(f)\right\}$. These sets have some intersections between them. Then note that,
>$$\bigcup_{i=1}^{n}A_{i},$$
>is the set of functions $\left\{f : X \longrightarrow Y \mid f\text{ is not surjective}\right\}$.
>So we would like to find $\left|U - \bigcup_{i=1}^{n}A_{i}\right| = \left\{f : X \longrightarrow Y \mid f\text{ is surjective}\right\}$.
>Then by inclusion-exclusion,
>$$
>\left|U - \bigcup_{i=1}^{n}A_{i}\right| = \sum\limits_{S\in\{1,\cdots,n\}}(-1)^{|S|}\left|\bigcap_{i\in S}A_{i}\right|
>$$
>Now note that,
>
>
>$$
>\bigcap_{i\in S}A_{i} = \left\{f : X \longrightarrow Y \mid j\not\in\text{image}(f)\forall j\in S\right\}.
>$$
>So we would like to know how many functions do not have any elements of $S$ in their image. This is $(n-|S|)^{k}$. So then,
>$$
>\left|U - \bigcup_{i=1}^{n}A_{i}\right| = \sum\limits_{S\in\{1,\cdots,n\}}(-1)^{|S|}(n-|S|)^{k}.
>$$
>However the term in the sum only depends on the size of $S$, not on $S$ itself. A subset with $j$ elements will appear $\binom{n}{j}$ times, so then we have,
>$$
>\sum\limits_{i=1}^{n}(-1)^{i}(n-i)^{k}\binom{n}{i}.
>$$
>This is our final answer.

