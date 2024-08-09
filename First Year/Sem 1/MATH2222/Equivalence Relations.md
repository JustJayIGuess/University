Let $S$ be a set.
>[!def]
>A (binary) *relation* on $S$ is simply a subset $R\subseteq S\times S$, i.e., a set of ordered pairs $(s_{1}, s_{2})$.
>If $R$ is a relation on $S$, and if $(x,y)\in R$, then it is said that $y$ is *related to* $x$ under $R$.

>[!example]
>$R\text{ on }\mathbb{Z} = \left\{(x,y)\in \mathbb{Z}\times \mathbb{Z}\mid x+y\text{ is even}\right\} = \left\{(0,2),(-1,3), (3,7),(6,8),...\right\}$.

>[!example]
>Suppose $S=\left\{a,b,c\right\}$.
>There are currently $2^{9}$ possible relations $R$ on $S$.


# Equivalence Relations
An equivalence relation can be thought of as a **weaker form of equality**.

>[!def]
>Let $S$ be some set. $E$ is an equivalence relation on $R$ if:
>- (reflexive) for every $x\in S$, we have $(x,x)\in E$
>- (symmetric) for every $x,y\in S$, we have $(x,y)\in E$ if and only if $(y,x)\in E$
>- (transitive) for every $x,y,z\in S$, if $(x,y)\in E$ and $(y,z)\in E$, then $(x,z)\in E$.

>[!example]
>If $S = \left\{a,b,c\right\}$, then $R=\left\{(a,a),(b,c),(b,a)\right\}$ is not an equivalence relation, as it is not reflexive or symmetrix. It is however transitive.

>[!example]
>The equivalence relation $\left\{(x,y)\in S\times S \mid x=y\right\}$ is an equivalence relation.
>So if $S=\left\{a,b,c\right\}$ then $R=\left\{(a,a),(b,b),(c,c)\right\}$. It can be seen that this is reflexive, symmetric and transitive.

>[!example]
>$R=\left\{(x,y)\in \mathbb{Z}\times \mathbb{Z} \mid x+y\text{ is odd}\right\}$.
>This is not an equivalence relation, as it is not reflexive ($(1,1)\notin R$).

>[!example]
>$R = \left\{(f,g)\in S\times S \mid g-f\text{ is continuous everywhere}\right\}$
>This is an equivalence relation.

>[!example]
>$R = \left\{(x,y)\in \mathbb{Z}\times \mathbb{Z} \mid x+y\text{ is even}\right\}$
>This is an equivalence relation.

>[!example]
>$R=\left\{(x,y)\in \mathbb{Z}\times \mathbb{Z} \mid x\le y\right\}$.
>This is not symmetric, so it is not an equivalence relation.

# Equivalence Classes
Let $S$ be some set, and let $E\subseteq S\times S$ be an equivalence relation on $S$.
If $(x,y)\in E$, we can write $x\sim_{E}y$, or if there is only one relation being discussed, $x\sim y$.
>[!def]
>Let $x\in S$. The equivalence class of $x$, denoted $[x]$ is defined as,
>$$\begin{align*}[x] := \left\{y\in S \mid x\sim y\right\}.\end{align*}$$
>I.e., $[x]$ is the set of all elements in $S$ that are related to it.

>[!theorem]
>$y\in [x] \Leftrightarrow x\in [y] \Leftrightarrow [x]=[y]$
>Let $x,y\in S$ if $[x]\cap[y]\ne \varnothing$, then $[x]=[y]$.

>[!proof]
>Suppose $y\in [x] \Rightarrow x\sim y$. By symmetry, then $y\sim x$, so $y\in [y]$.
>Let $z\in [x]$ and $y\in [x]$. Then $x\sim z$ and $x\sim y$. By symmetry and transitivity, then $z\in [y]$

>[!proof]
>Let $x,y\in S$, and suppose $[x]$ and $[y]$ are not disjoint. So there is some $z\in[x]$ and $z\in [y]$. So then $x\sim z$ and $y\sim z$. We can now show that $[x]=[y]$.

>[!cor]
>Let $E$ be an equivalence relation on $S$. Then the distinct equivalence classes of $E$ partitions $S$ into disjoint subsets.
>This means:
>- every $x\in S$ is in some equivalence class, and
>- distinct equivalence classes do not overlap.

>[!remark]
>Equivalence relations **partition** $S$ into classes, so,
>$$\begin{align*}S &= \bigsqcup_{\alpha}S_{\alpha},\ S_\alpha\subseteq S\end{align*}$$
> Conversely, given a partition of $S$, we can always define an equivalence relation $x\sim y$ if $x,y$ are in the same subset of the partition (note that $x,x$ are in the same partition, $x,y$ being in the partition implies $y,x$ is in the partition, and $x\sim y$ with $y\sim z$ implies that $x\sim z$).
