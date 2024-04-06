>[!def]
>If we have $a,b\in \mathbb{Z}$, we say that $a$ *divides* $b$ (written $a|b$) when there is an integer $m\in \mathbb{Z}$ such that $b = am$.
>E.g., $3|15 \Leftarrow 15=3\times 5$.
>You can think about $a|b$ as "$a$ times something equals $b$".

>[!def]
>$p\in \mathbb{Z},p\ne 0,p\ne \pm 1$ is prime if the only positive divisors of $p$ are 1 and $p$ itself.

>[!def]
>$a,b\in \mathbb{Z}$ are considered *relatively prime*, or *coprime*, when they have no common positive factors other than 1.

>[!lemma] 
>*Bezout's Identity*
>Let $a,b\in \mathbb{Z}$ be coprime. Then,
>$\exists m,n\in \mathbb{Z}$ such that $ma+nb=1$.

>[!proof]
>Suppose that $a,b>0$. If $a$ or $b$ were negative, there exist trivial solutions $m,n$ based off this positive case (negating $m$ and/or $n$).
>Without loss of generality, assume $a>b>0$ (if $a=b$ then $a=b=1, m=1,n=-1$ for $a,b$ to be relatively prime)
>We now proceed with induction on $a+b$.
>**Base case.**
>If $a+b=1$, then it must be that $a=1,b=0$. We choose $m=0,n=1$.
>**Inductive Step.**
>Consider the pair $x,y-x,\ x+(y-x)=y=k$. This means that $a+b<k$. So by the inductive hypothesis we have that there is $m',n'\in \mathbb{Z}$ such that $m'b+n'(a-b)=1$.
>$$\begin{align*}
m'b+n'(a-b) &= 1\\
&= (m'-n')b+n'a\\
&= 
TODO
\end{align*}$$

>[!theorem]
>Let $a,b\in \mathbb{Z}$ be coprime, and suppose $a|qb,\ q\in \mathbb{Z}$.
>Then $a|q$.
---
>[!proof]
>By Bezouts identity, we have that there is $m,n$ so that
>$$\begin{align*}
ma+nb &= 1\\
q(ma+nb) &= q\\
amq+bnq &= q
\end{align*}$$
>Therefore $a$ divides $amq$ and also divides $bnq$, so then $a$ also divides $q$.

>[!theorem]
>If $p$ is prime and $a,b\in \mathbb{Z}$, then $p|ab\Rightarrow p|a\text{ or } p|b$.
---
>[!proof]
>Suppose that it is not true that $p|a$. Then $p$ and $a$ are coprime. So by the previous proposition, $p|ab \Rightarrow p|b$. The same applies with $a$ and $b$ switched.
>$$\tag*{$\blacksquare$}$$
---
>[!cor]
>$p|a_{1}a_{2}a_{3}...a_{n}\Rightarrow p|a_{i}\text{ for some }i.$
>By induction on $n$
>**Base case.**
>This is trivially true.
>**Inductive step.**
>We assume that $p|a_{1}a_{2}...a_{n-1}$.
>Now consider $p|a_{1}a_{2}...a_{n}$. We label $a_{1}a_{2}...a_{n-1}=b$.
>So we now have $p|ba_{n}$. We now know that $p|b$ or $p|a_{n}$. By inductive step and $n=2$ case, the corollary is now true for $n$.
>$$\tag*{$\blacksquare$}$$

>[!def]
>Given an integer $n$, a prime factorisation of $n$ is an expression of $n$ as the product of a finite number of distinct primes, each raised to some power, i.e.,
>$$\begin{align*}n=p_{1}^{k_{1}}p_{2}^{k_{2}}...p_{n}^{k_{n}}\end{align*}$$

>[!theorem]
>*The Fundamental Theorem of Arithmetic*
>Any integer $n\in \mathbb{Z}$ has a prime factorisation, which is unique up to reordering the factors.
---
>[!proof]
>We will assume $n>0$ and proceed by induction on $n=1$.
>**Base Case.**
>Trivially true.
>Note by convention,
>$$\begin{align*}\prod_{p\in \varnothing}p=1.\end{align*}$$
>**Inductive Step.**
>Consider the set of positive divisors of $n$.
>Take $p$ to be the smallest number in this set, so $n = \frac{n}{p}\times p$.
>Note that $p$ is prime. If $p$ were not prime, $p=q\times \frac{p}{q}$, and $q$ would be the smallest prime, as $q|p,\ p|n \Rightarrow q|n$.
>$\frac{n}{p}<n$, so now uniquely factorise $\frac{n}{p}$ using the inductive hypothesis as $\frac{n}{p} = p_{1}^{k_{1}}p_{2}^{k_{2}}\cdots p_{m}^{k_{m}}$. We now have the unique factorisation of $n = pp_{1}^{k_{1}}\cdots p_{m}^{k_{m}}$.
>To show unicity, $p|n \Rightarrow$ $p$ appears in any prime factorisation of $n$.
>$$\begin{align*}\ \tag*{$\blacksquare$}\end{align*}$$

# Greatest Common Divisors
>[!def]
>Let $a,b\in \mathbb{Z}$. The *greatest common divisor* of $a$ and $b$ ($\gcd(a,b)$) is the largest positive integer that divides both $a$ and $b$.

>[!theorem]
>$$\begin{align*}\left\{ma+nb \mid m,n\in \mathbb{Z}\right\}=\left\{kd \mid k\in \mathbb{Z}\right\},\qquad\text{where }d=\gcd(a,b)\end{align*}$$
>I.e., the set of all combinations of $a,b$ each with some integer multiple is the same as all the multiples of the $\gcd$ with some integer $\in \mathbb{Z}$.

>[!question]
>Is this related to lattice reduction?

>[!proof]
>***Exercise***: we can show that the two sets are subsets of each other.
>(use Bezout's identity)
## Properties of GCD
- $\gcd(a,0)=a$
- $\gcd(0,0)=0$
- $\left\{ma+nb \mid m,n\in \mathbb{Z}\right\}=\left\{kd \mid k\in \mathbb{Z}\right\},\ \text{where }d=\gcd(a,b)$

## The Euclidean Algorithm
>[!lemma]
>Let $a,b\in \mathbb{Z}$. The $\gcd(a,b)=\gcd(a-kb,b), \forall k\in\mathbb{Z}$.

>[!proof]
>This will be proven by showing that the sets of divisors of $a,b$ and $a-kb,b$ are equivalent.
>Suppose that $d|a$ and $d|b$. Then $d|kb$, and so $d|a-kb$. So the common divisors of $a,b$ are a subset of the common divisors of $a-kb,b$.
>Now suppose that $d|a-kb$. Then $d|b$ and $d|kb$. So $d|a-kb+kb$ and thus $d|a$. So the common divisors of $a-kb,b$ is a subset of $a,b$.
>So the two sets are equivalent.

>[!theorem]
>Let $a,b\in \mathbb{Z}$, $b\ne 0$.
>Then, there exists unique integers $q,r$ with $0\le r<|b|$, such that $a=bq+r$.
>I.e., the remainder after division is unique.

>[!proof]
>Consider the set $\left\{a-bk \mid k\in \mathbb{Z}\right\}\cap \mathbb{Z}_{\ge 0}$.
>Let $r$ be the minimum of this set (r is the remainder when a is divided by b).
>$\exists q\in \mathbb{Z}$ such that $r = a-bq$.
>Suppose $b>0$ and suppose for the sake of contradiction that $r\ge b$. Then $a-b(q+1)=a-bq-b=r-b\ge 0$. So $r-b<r$, but $r$ was meant to be the minimum. This is a contradiction.
>So then $r<b$. This proves the existence of $r<b$.
>To prove unicity of $r$, suppose for the sake of contradiction that there are two different $a=bq+r$ and $a=bq'+r'$.
>So then $0 = b(q-q')+r-r'\Rightarrow r'-r = b(q-q')$. So $b|r'-r$. However by the bound on $r$, then $-|b|<r-r'<|b|$. However the only multiple of $b$ in this interval is 0! So $r-r'=0\Rightarrow r=r'$.
>Therefore there must be only one unique $r$.
>Additionally, we now have $0=b(q-q')$, so $q$ and $q'$ are equivalent also.
>$$\begin{align*}\ \tag*{$\blacksquare$}\end{align*}$$

The Euclidean algorithm finds $\gcd(a,b)$ for $a,b\in \mathbb{Z}$.
Suppose that $|a|\ge |b|$ without loss of generality.
1. If $b=0$, return $|a|$. ($\gcd(a,0)=|a|$) and stop.
2. Otherwise write $a=bq+r$ with $q,r\in \mathbb{Z}$ such that $0\le r < |b|$. Replace $a,b$ with $b,r$ and repeat. (I.e., replace $a$ with $b$, and replace $b$ with the remainder of $a$ when divided by $b$)

>[!example]
>$\gcd(91, 63)$.
>Then we get to $91=63\times 1 + 28$. So find $\gcd(63, 28)$.
>Then we get to $63 = 2\times 28 + 7$. So find $\gcd(28, 7)$.
>Then we get to $28 = 4\times 7+0$. So find $\gcd(7, 0)$.
>$b=0$, so we return $|7|=7$.
>
>Note that now we also have $7 = 91m + 63n$ for some $m,n$, which can be found by reversing the algorithm.

