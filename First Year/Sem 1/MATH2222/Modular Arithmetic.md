Modular arithmetic is based off an example of [[Equivalence Relations]].
We can show that modular arithmetic follows all properties of equivalence relations:
- Reflexive - $x\equiv x\mod n$
- Symmetric - $x\equiv y\mod n \Rightarrow y\equiv x\mod n$
- Transitive - $x\equiv y\mod n$ and $y\equiv z\mod n \Rightarrow x\equiv z\mod n$

>[!def]
>Consider the set $S = \mathbb{Z}$.
>The equivalence relation of interest is called *congruence*, denoted $\equiv$.
>First, fix $n\ge 1$. Define an equivalence relation on $S$ by saying that $x\equiv y$ if $n\mid x-y$.
>We now check that this is in fact an equivalence relation:
>- $x\equiv x$: $x-x=0,\ n|0$
>- $x\equiv y$: $n|x-y \Rightarrow n|y-x \Rightarrow y\equiv x$
>- $x\equiv y$ and $y\equiv z \Rightarrow lx-y=kn,\ y-z=ln$, so $x-z = (k+l)n \Rightarrow n|x-z \Rightarrow x\equiv z$
>So we have a valid equivalence relation.
>The set of equivalence classes (or *congruence classes*, *remainder classes*), are written $\mathbb{Z}_{n}$ or $\frac{\mathbb{Z}}{n\mathbb{Z}}$.
>$$\begin{align*}\mathbb{Z} &= \bigcup_{\bar{a}\in\mathbb{Z}_{n}}\bar{a}\end{align*}$$
>I.e., the equivalence classes $\mathbb{Z}_{n}$ are all subsets of $\mathbb{Z}$.
>$Z_{n}$ has $n$ equivalence classes.

>[!example]
>Consider $n=2$, defining the set of congruence classes $Z_{2}$.
>$$\begin{align*}\mathbb{Z}_{2} &= \left\{\bar{0},\bar{1}\right\}\end{align*}$$
>So then we have that $\bar{0}\subseteq \mathbb{Z}$ and $\bar{1}\subseteq \mathbb{Z}$.

>[!theorem]
>There are exactly $n$ equivalence classes in $Z_{n}$.
---
>[!proof]
>By definition, $a\sim b \Leftrightarrow n|a-b$.
>The division algorithm is already proven to yield unique $q,r$ such that $a=kn+r$, $b = ln+s$.
>It now follows that $a\sim b \Leftrightarrow r=s$.
>So the equivalence classes are labelled by the remainder of division by $n$,
>$$\begin{align*}\bar{i} &= \left\{a \mid a=kn+i,\ i\in [0,n)\right\}\end{align*}$$
>which must be $0\le i\le n-1$, so there must be $n$ equivalence classes.
>$$\ \tag*{$\blacksquare$}$$

>[!lemma]
>If $a\equiv r\mod n$ and $b\equiv s\mod n$, then,
>$$\begin{align*}a+b&\equiv r+s\mod n \\ ab&\equiv rs\mod n\end{align*}$$
---
>[!proof]
>We are given that $n|a-r$, and $n|s-b$.
>So then $a=kn+r$, $b = ln+s$.
>Then $a+b = (k+l)n+(r+s) \Rightarrow (a+b)-(r+s) = (k+l)n$.
>So then $a+b\equiv r+s$.
>The same line of reasoning can prove $ab\equiv rs$.
---
>[!remark]
>This means we can do arithmetic on equivalence classes!

>[!note]
>$\mathbb{Z}_{n}$ is an example of a *commutative ring*.
>$\mathbb{R}^{n\times n}$ is an example of a *non-commutative ring*.
>A ring is a finite set equipped with addition and multiplication.
>If we do not require the operation labelled as addition, we have a *group*.
>So a group is a finite set equipped with some binary operation, called multiplication.

>[!def]
>We can therefore define *addition and multiplication on $\mathbb{Z}_{n}$*.
>Addition is defined as $\bar{a}+\bar{b} = \overline{a+b}$. So we can take an element from $\bar{a}$ and $\bar{b}$ and add them, then the equivalence class containing this is $\bar{a}+\bar{b}$.
>In other words, regardless of the elements chosen from the congruences classes $\bar{a}$ and $\bar{b}$, $a+b$ will always be in $\overline{a+b}$.
> Similarly, $\bar{a}\times \bar{b} = \overline{ab}$.
> We have therefore defined addition and multiplication of equivalence classes.
> We also then have that, over $\mathbb{Z}_{n}$, $\bar{n}=\bar{0}$.

>[!example]
>**Casting out nines.**
>First write out an integer in base 10, $\sum\limits_{n=0}^{m}a_{n}10^{n}$.
>Note that $10\equiv 1\mod 9$. So then,
>$$\begin{align*}\sum\limits_{n=0}^{m}a_{n}10^{n}&= \sum\limits_{n=0}^{m}a_{n}\mod9\end{align*}$$

>[!def]
>We can always define an additive inverse $-\bar{x}$ that will take any $\bar{x}$ to $\bar{0}$.
>So the additive inverse of $\bar{x}$ is $\overline{-x}$.

>[!def]
>We can define the multiplicative identity in $\mathbb{Z}_{n}$ to be $\bar{1}$.
>Note that $\mathbb{Z}$ has only $1$ and $-1$ as multiplicative inverses.
>In $\mathbb{Z}_{n}$, we must be more careful. E.g., $2$ does not have a multiplicative inverse$\mod 4$.

>[!question]
>Under what conditions does $n,x$ have a multiplicative inverse?
>Equivalently, for what $x$ does $xy \equiv 1\mod n$?

>[!lemma]
>If $a,n$ are relatively prime, then multiplication by $a$ will be a map $\bar{x}\longmapsto a\bar{x}$.
>In other words, multiplication by $a$ will permute all the non-zero congruence classes.

>[!proof]
>Consider $0a,a,2a,3a,...,(n-1)a\mod n$.
>Note that none of these numbers can be divisible by $n$, as $a<n$ and $a,n$ are relatively prime. These must all therefore have distinct remainders.
>Therefore multiplication by $a$ is injective. We therefore have an injective map from a finite set to itself, which must be bijective.
>So then there must be an inverse of multiplication by $a$.

>[!cor]
>If $a,n$ are relatively prime, then $a$ has a multiplicative inverse mod $n$.

>[!example]
>$3x=1\mod 8 \Rightarrow x=3$.

# The Chinese Remainder Theorem
## Motivation
>[!example]
>Suppose the following:
>$$\begin{align*}
x &\equiv 1\mod3\\
x &\equiv 2\mod 5\\
x &\equiv 4\mod 7\\
\\
x &= 3k+1=2\mod 5,\\
\therefore 3k &\equiv 1\mod 5\\
k &= 2\mod 5\text{  (as 3,5 coprime)}\\
\therefore k &= 5m+2\\
\Rightarrow x &= 15m+7\\
15m+7 &\equiv 4\mod 7\\
\therefore m &\equiv 4\mod 7\\
m &= 7n+4\\
\\
\therefore x &= 105k + 67
\end{align*}$$

## Existence and Uniqueness Theorem
>[!theorem]
>*The Chinese Remainder Theorem* states the following.
>Let $\left\{n_{i}\right\}_{i=1}^{r}$ be $r$ positive integers which are pairwise coprime. Let $\left\{a_{i}\right\}_{i=1}^{r}$ be any $r$ integers.
>Then the system of equations,
>$$\begin{align*}
x &\equiv a_{1}\mod n_{1}\\
\vdots\\
x &\equiv a_{r}\mod n_{r},
\end{align*}$$
>has a unique solution modulo $N=\prod_{i=1}^{r}n_{i}$.
>
>This can be alternatively stated as follows.
>Given $n_{1},...,n_{r}$ coprime pairwise and $a_1,...,a_r$ be arbitrary integers, and $N$ be the product of all $n_i$, the function $\mathbb{Z_{N}}\longrightarrow \mathbb{Z}_{n_{1}}\times\cdots\times\mathbb{Z}_{n_{r}}$ is bijective.
>For this map to be surjective, there must be, for any $(a_1,...,a_r)$, a solution $x$ in the domain. That this is unique implies that this $x$ is unique. So there is always a solution, and this solution is unique (modulo $N$).
---
>[!proof]
>![[Modular Arithmetic 2024-03-20 13.51.30.excalidraw]]

Generalisations to CRT cannot be neatly made, e.g., if $n_{i}$ are not pairwise coprime, then there may not be any solutions.
## Computation
Suppose we have a system of equations to which CRT may be applied.
$$\begin{align*}
x &\equiv a_{1}\mod n_{1}\\
&\vdots
\end{align*}$$
Define that $N_{i} := \frac{N}{n_{i}}$, so $n_{i}$ and $N_{i}$ are coprime.
$N_{i}$ must therefore have some multiplicative inverse $y_{i}\mod n_{i}$, i.e.,  $y_{i}N_{i} = 1\mod n_{i}$.
Then take,
$$\begin{align*}
x &= \sum\limits_{j=1}^{r}a_{j}N_{j}y_{j}.
\end{align*}$$
This must be a solution.
$$\begin{align*}
x &= \sum\limits_{j=1}^{r}a_{j}N_{j}y_{j}\\
&= a_{1}N_{1}y_{1}+...+a_{i}N_{i}y_{i}+...\mod n_{i}\\
&= a_{i}N_{i}y_{i}\\
&= a_{i},
\end{align*}$$
as $n_{i}$ is a factor of all $N_{k}$ except $N_{i}$.
# Fermat's Little Theorem
>[!theorem]
>Fermat's little theorem states the following,
>$$\begin{align*}
\text{Let }p\text{ be prime}.\\
\text{If }a\text{ is not a mutiple of }p,\text{ then},\\
a^{p-1} &\equiv 1\mod p
\end{align*}$$

>[!cor]
>$$\begin{align*}
a^{p}-a &\equiv 0\mod p
\end{align*}$$

>[!def]
>The *order* of $a$ is the smallest non-negative power $k$ such that $a^{k} \equiv 1\mod p$.
>For example, the order of 2, mod 5, is 4.

>[!lemma]
>Take some prime $p$, with $a\not\equiv 0\mod p$. For $x\in\mathbb{Z}_{p}$, let the *orbit* be $S_{x} = \left\{x, ax, a^{2}x, ...\right\}$. There is a positive integer $k$ such that for all $x\ne 0$, then $S_{x}$ has $k$ elements.
>I.e., all orbits have the same size.

>[!proof]
>Since $\mathbb{Z}_{p}$ for a prime $p$ is a finite set, the positive powers of $a$ cannot all be distinct, and so must repeat. So there is $m,n$ such that $a^{m}\equiv a^{n}\mod p$.
>If $m>n$, then this means that $a^{m-n}\equiv 1\mod p$.
>So the order of $a$ is well-defined, and we will call it $k=m-n$.
>So then $S_{1} = \left\{1,a,a^{2},...\right\}$ must have $k$ distinct elements.
>Now we want to show that $S_x$ also has $k$ distinct elements.
>Recall that multiplication by nonzero $x$ permutes $\mathbb{Z}_{p}\setminus \left\{0\right\}$.
>So then the set $\left\{1x,ax,a^{2}x,...,xa^{k-1}\right\}$ must also be distinct.
>Then $xa^{k}$ is the next element, which must be $1$. So $S_{x}$ also has $k$ elements.
>$$\ \tag*{$\blacksquare$}$$

>[!lemma]
>The distinct orbits in $\mathbb{Z}_{13}$ partition $\mathbb{Z}_{13}$ into distinct subsets. So we have an equivalence relation.
>Take $p$ prime, and fix $a\not\equiv 0\mod p$.
>We define the equivalence relation that $x\sim y$ if $y\equiv xa^{i}\mod p$ for some $i$.
>
>We can show this is reflexive by taking $i=0$.
>Additionally $a^{i}$ must be coprime with $p$, so we now multiply both sides by $a^{k-1}$ where $k$ is the order. So then we have $x = ya^{k-1}$.
>Transitivity can be shown simply by index laws.

>[!proof]
>Consider the specific case first. Let $p=13,a=5$, and consider $f : \mathbb{Z}_{13} \longrightarrow \mathbb{Z}_{13},\ f(x)=ax=5x$.
>Notice that,
>- $0 \longmapsto 0$
>- $1 \longmapsto 5 \longmapsto 12 \longmapsto 8 \longmapsto 1$.
>- $2 \longmapsto 10 \longmapsto 11 \longmapsto 3 \longmapsto 2$
>- $4 \longmapsto 7 \longmapsto 9 \longmapsto 6 \longmapsto 4$
>Note that we have all 4-cycles (except 0).

>[!proof]
>Now we prove Fermat's Little Theorem.
>First let $k$ be the order of $a$, so that $a^{k} = 1\mod p$.
>We must now show that $p-1$ is some multiple of $k$, $kr=p-1$.
>Then we would have that $a^{p-1}=a^{kr}=(a^k)^{r}=1\mod p$.
>Now consider the equivalence relation defined previously.
>The previous equivalence class had multiple sets all of size $p$ with one additional element $\left\{0\right\}$. So then $p=kr+1\Rightarrow p-1=kr$ for some $r$.
>Therefore we have proven Fermat's Little Theorem.
>$$\ \tag*{$\blacksquare$}$$

>[!cor]
>$a^{p} \equiv a\mod p$ for any prime $p$ and integer $a$.
>This is important, as if we have some number, like $341$, and find an $a$ such that $7^{341}\equiv 51\mod 341$. As $7\ne 51$, then $341$ is not prime.
>This does not go both ways, however.
>If $n$ is prime this holds, but if $n$ is not prime, it may or may not hold

[[Counting in Finite Sets]]

