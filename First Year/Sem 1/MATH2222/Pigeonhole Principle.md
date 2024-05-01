>[!def]
>In simplest form, the *pigeonhole principle* states that if there are $k$ 'pigeonholes' and more than $k$ 'pigeons' then some hole must have at least two pigeons.
>It may be more precisely stated as the next theorem.

>[!remark]
>We have used this before! Recall the proof that of $p$ is prime and we take some $a$ in $\mathbb{Z}_{p}$, then there must exist some $b$ such that $ab \equiv 1\mod p$.
>We proved this by considering the set of size $p$,
>$$
>\left\{0,a,2a,3a,\cdots,(p-1)a\right\}.
>$$
>Note that if all elements are distinct, then one of these must be $1\mod p$. If none of the elements are $1\mod p$ then by the pigeonhole principle, there must be two entries $ia,ja$ such that $ia \equiv ja\mod p$. Then $(i-j)a \equiv 0\mod p$, which means $p|(i-j)a$. But $a,p$ are coprime, so then $p|i-j$. But both of $i,j$ are less than $p$, so $i-j=0$, which is a contradiction.

>[!theorem]
>Placing more than $kn$ objects into $n$ classes puts more than $k$ objects into some class.

>[!proof]
>Consider the contrapositive, that if there is no class out of $n$ classes with more than $k$ objects, then there are less than $kn$ total objects. This is clearly true (and can be proven by induction if needed).

---

>[!example]
>Consider tiling a grid with dominos.
>![[Pigeonhole Principle 2024-04-30 16.27.53.excalidraw]]
>We claim that it is always possible to split the board with a straight vertical line or straight horizontal line, without splitting any dominos.

>[!proof]
>Consider associating a splitting line with some domino if that line splits the domino. Note that there are $18$ dominos and $10$ cutting lines.
>Each line cuts 1.8 dominos on average. So there must be some line that cuts either zero or one dominos. However any line must cut an even number of dominos, as if we cut one domino, then the board must be tiled on each side of the line despite it having an odd number of squares left. Therefore there must be some line must cut zero dominos.

## In Lossless Compression
A compression algorithm takes as input a (ideally long) binary string and outputs a shorter binary string.
Ideally this function has an inverse such that no information is lost when the data is decompressed. I.e., the function should be injective if it is injective.
However as it is injective, the cardinality of the codomain must be greater than or equal to the cardinality of the domain. So these ideal lossless compression algorithms do not actually exist!
