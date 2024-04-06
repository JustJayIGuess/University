>[!def]
>If $A$ is a non-empty set of real numbers and there exists some $n\in\mathbb{R}$ such that $a<n$ for all $a\in A$, then there exists some $x\in \mathbb{R}$ such that $a\le x$ for all $a\in A$ and if $a\le y$ for all $a\in A$, then $y\ge x$.
>I.e., if there is any upper bound $n$ on a set, there must be a *least upper bound* $x$ such that any other upper bound $y$ is greater than or equal to $x$.
>
>More precisely, $x\in \mathbb{R}$ is a least upper bound (or *supremum*) for $A$ if:
>- $x$ is an upper bound for $A$
>- $y$ being an upper bound for $A$ implies that $y\ge x$.
>
>In compact notation, $\forall A\subseteq\mathbb{R},\ A\text{ nonempty and bounded, }\exists \sup(A)$.

>[!remark]
>As an axiom (P13), this distinguishes $\mathbb{R}$ from $\mathbb{Q}$, as this does not work for the rationals.

>[!example]
>Consider $A = \left\{\sin(x) \mid x\in \mathbb{R}\right\}$.
>Then $7$ is an upper bound of $A$ but it is not the least upper bound.
>The least upper bound will be $1$.
---
>[!example]
>Consider $A = \left\{x \mid x^{3}-x < 0\right\}$.
>Note that $x^{3} - x = x(x+1)(x-1)$.
>We have that $\exists\sup(A)=1$. **Note that $\sup(A)\notin A$**, however there is no upper bound that is strictly less than $1$.
---
>[!example]
>Notice that this fails for $\mathbb{Q}$.
>Let $B$ be the set of rational numbers that are less than $\pi$. We claim that there is no $\sup(B)$.
>This is because $\pi\notin \mathbb{Q}$, so any supposed least upper bound must have a smaller least upper bound that is closer to $\pi$.
>$$\therefore\mathbb{Q}\ne \mathbb{R}$$

>[!remark]
>This along with the other 12 axioms ([[Axioms for Numbers]]) can be used to construct the real numbers.
