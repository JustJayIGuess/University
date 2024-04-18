>[!def]
>The *rational numbers* are denoted $\mathbb{Q}$, and may be defined as,
>$$\begin{align*}
\left\{\frac{a}{b} \mid a,b\in\mathbb{Z},\ b\ne 0\right\}
\end{align*}$$
>We also equip this with the equivalence,
>$$\begin{align*}
\frac{a}{b} &= \frac{c}{d}\text{ when }ad=bc.
\end{align*}$$
>Based on this equivalence relation, we say that $\frac{a}{b}$ is in *lowest form* if $\gcd(a,b)=1$. Any rational number may be written in some unique lowest form.

# The Billiard Problem
Suppose that we have a square billiard table with pockets at the corners, and strike the ball with a particular slope $m$.
![[The Rational Numbers (MATH2222) 2024-04-16 13.09.21.excalidraw|400]]
If we continue this line, we will see that eventually the ball will fall into a corner pocket.
We therefore pose the following question.

>[!question]
>For which slopes will the ball eventually fall into a pocket.

>[!theorem]
>The ball will be pocketed if and only if $m\in\mathbb{Q}.$

>[!proof]
> Note that a line of slope $m$ has rational slope if and only if the line passes through a point with integer coordinates. Therefore we have a bijection between lines through the origin and a lattice point in $\mathbb{R}^{2}$ and the rational numbers.
> $$
> l \longmapsto \text{slope of }l.
> $$
> Now imagine defining a billiard table at every unit square along the cartesian plane. Note that in this case, the ball bouncing off the wall can be thought of as travelling along a straight line into other copies of the billiard table.
> 
> Then the ball is pocketed if the line intersects some lattice point. Therefore the ball will be pocketed if and only if the slope was rational.

# Parameterisations
Suppose we would like to describe a 'nice' subset of the plane using a single parameter.
Take, for instance, the line with slope $\frac{a}{b}$.

```functionplot
f(x)=sqrt(1-x^2)
g(x)=-sqrt(1-x^2)
```


```desmos-graph
y = 1/3 x
```

We may define this line as the set,
$$\begin{align*}
l&:= \left\{(x,y)\in\mathbb{R} \mid y=\frac{a}{b}x\right\}\\
&= \left\{(bt,at) \mid t\in \mathbb{R}\right\}\text{ as }(b,a)\in l
\end{align*}$$

Now consider the unit circle.
```functionplot
x^2 + y^2 = 1
```


Using set builder notation,
$$\begin{align*}
C &:= \left\{(x,y)\in\mathbb{R}^{2} \mid x^{2}+y^{2}=1\right\}\\
&= \left\{(\cos(t),\sin(t)) \mid t\in[0,2\pi)\right\}
\end{align*}$$
We can also parameterise the circle by consider the line from $(-1,0)$ going through a point in the circle. This will map all real numbers to a unique point on the circle, but misses the point $(-1,0)$.

```desmos-graph
1=x^2 + y^2
y = 1/2 (x+1)
y = -3 (x+1)
```

>[!theorem]
>We therefore have the following.
>$$\begin{align*}
(x,y) &= \left(\frac{1-t^{2}}{1+t^{2}}, \frac{2t}{1+t^{2}}\right),\ t\in\mathbb{R},\\
x^{2}+ y^{2} &= 1
\end{align*}$$

>[!corollary]
>A point $(x,y)$ with $x^{2}+y^{2} =1$ has rational coordinates if and only if $t$ is rational in the previous parameterisation.

>[!proof]
>We will prove there is a bijection from $(x,y)$ to the parameterisation.
>Note that for any $t\in \mathbb{R}$, $\frac{1-t^{2}}{1+t^{2}} \ne -1$. So if,
>$$\begin{align*}
(x,y) = \left(\frac{1-t^{2}}{1+t^{2}}, \frac{2t}{1+t^{2}}\right)
\end{align*}$$
>we can guarantee that $x\ne -1$.
>Then if $x^{2}+y^{2}=1$,
> 
> $$\begin{align*}
> \left(\frac{1-t^{2}}{1+t^{2}}\right)^{2}+\left(\frac{2t}{1+t^{2}}\right)^{2}...
> \end{align*}$$
> 
> Conversely, if $x,y$ has $x\ne 1$ and $x^{2}+y^{2}=1$, then consider the line between $(-1,0)$ and $(x,y)$. This line has the equation,
> $$\begin{align*}
> ...
> \end{align*}$$
> (show that $(x,y)$ satisfies the parametric equation).
> 
> We have therefore shown that all points $(x,y)$ on the unit circle except $(-1,0)$ can be described uniquely using the parametrisation.
> **(complete this at home)**

# Rational Zeroes Theorem
>[!theorem]
>Let $c_{0},c_{1},\cdots,c_{n}\in\mathbb{Z}$, with $c_{0},c_{n}\ne 0$.
>Now let $f(x) = c_{0}+c_{1}x + c_{2}x^{2} + \cdots + c_{n}x^{n}$.
>
>If $r\in\mathbb{Q}$ is a root of $f$, so $f(r)=0$, and we write $r=\frac{p}{q}$ in lowest terms, then:
>- $p$ divides $c_{0}$
>- $q$ divides $c_{n}$

>[!proof]
>If $f(r) = f\left(\frac{p}{q}\right)= 0$, then we have,
>$$\begin{align*}
\sum\limits_{i=0}^{n}c_{i}\left(\frac{p}{q}\right)^{i} &= 0\\
\sum\limits_{i=0}^{n}c_{i}p^{i}q^{n-1} &= 0\\
\sum\limits_{i=0}^{n-1}c_{i}p^{i}q^{n-i} &= -c_{n}p^{n}\\
q\sum\limits_{i=0}^{n-1}c_{i}p^{i}q^{n-i-1} &= -c_{n}p^{n}
\end{align*}$$
>So then $q|c_{n}p^{n}$. However $q,p^{n}$ are coprime, so $q|c_{n}$.
>We now have a $q$ that can be factored out of the left side, and the remaining sum is an integer, so we have that $q\times (-k) = c_{n}p^{n}$ for some $k$.

---

>[!corollary]
>At home: use this to prove that $\sqrt[3]{6}$ is irrational.

---

>[!example]
>Show that $f(x)=2x^{3}+x-1$ has no rational roots.
>If $\frac{p}{q}$ were a root, then we would have that $p|1$, $q|2$. So $p\in \left\{1,-1\right\}, q\in \left\{1,-1,2,-2\right\}$. The possibilities are therefore $\frac{p}{q} = \pm 1, \frac{p}{q} = \pm \frac{1}{2}$. None of these are roots, so there are no rational roots.

---

>[!example]
>Find all rational or irrational roots of $f(x) = x^{3}-7x+6$. Any rational root must have $p|6,q|1$. So our possibilities are $\pm 1, \pm 2, \pm 3, \pm 6$. $x=1,x=2,x=-3$ are roots, and no others are roots. Therefore we have $f(x)=(x-1)(x-2)(x+3)$.

>[!remark]
>We know how to solve the quadratic equation for $f(x)=ax^{2} + bx + c$.
>We also have a cubic and quartic equation, however it has been proven that there is no quintic equation.

# The Pythagorean Triples
>[!def]
>A Pythagorean triple is a tuple of three numbers $(a,b,c)\in\mathbb{Z}$ such that $a^2+b^2=c^2$.

>[!theorem]
>If $a,b,c\in \mathbb{R}$ are side lengths of a right triangle, then $a^{2}+b^{2}=c^{2}$.

>[!remark]
>Any Pythagorean triple $(a,b,c)$ will remain a triple when multiplied by an integer.
>E.g., $(3,4,5)\mapsto (6,8,10)$ is still a triple.
>We call triples with coprime $a,b,c$ *primitive*.

---

>[!theorem]
>There is a two-parameter parameterisation of all the primitive Pythagorean triples. We may add a third parameter to allow scaling.
>The parameterisation is as follows:
>$$(2rs,r^{2}-s^{2},r^2+s^{2})\text{ or } (r^{2}-s^{2},2rs,r^{2}+s^{2})$$

>[!proof]
> Since $(2rs)^{2} + (r^{2}-s^{2})^{2} = (r^{2}+s^{2})^{2}$, the formula does in fact produce Pythagorean triples. Now we will prove that every Pythagorean triple is of this form.
> Fix $c\in \mathbb{N}$, and find all $(a,b)$ such that $a^{2}+b^{2}=c^{2}$.
> Let $x = \frac{a}{c}, y = \frac{b}{c}$. So $a^{2}+b^{2}=c^{2}\iff x^{2}+y^{2}=1$. So then all Pythagorean triples correspond to rational points on the unit circle.
> We already know that the rational points on the unit circle are of the form,
> $$\begin{align*}
> (x,y) &= \left(\frac{1-t^{2}}{1+t^{2}},\frac{2t}{1+t^{2}}\right)\text{, or,}\\
> (x,y)&= (-1,0),\quad t\in\mathbb{Q}
> \end{align*}$$
> Now let $t = \frac{s}{r}$ and recall that $x=\frac{a}{c},y=\frac{b}{c}$. We now have,
> $$\begin{align*}
> (a,b,c) &= \frac{c}{r^{2}+s^{2}}(r^{2}-s^{2},2rs,r^{2}+s^{2})
> \end{align*}$$
> We now must show that $z=\frac{c}{r^{2}+s^{2}}$ is an integer.
> Note that when $z$ is not an integer, it is a half-integer.
> Let $z = \frac{m}{n}$ in lowest terms. Since $(a,b,c)=z(r^{2}-s^{2},2rs,r^{2}+s^{2})$.
> Then since $a,c$ are integers, then $n|r^{2}-s^{2}+r^{2}+s^{2} \Rightarrow n|2r^{2}$, and $n|2s^{2}$. However $s,r$ are relatively prime, $s^{2},r^{2}$ are also relatively prime, so $n|2$.
> So, when $z$ is a half-integer, $r^{2}+s^{2}$ is even. But $r,s$ are coprime, so $r,s$ must both be odd. Now let $R = \frac{r+s}{2},S = \frac{r-s}{2}$, and note these are integers.
> $$\begin{align*}
> r &= R+S\\
> s &= R-S
> \end{align*}$$
> Then we have,
> $$\begin{align*}
> r^{2}-s^{2} = 4RS,\ 2rs = 2(R^{2}-S^{2}),\ r^{2}+s^{2} = 2(R^{2}+S^{2})
> \end{align*}$$

>[!tip]
>The key idea here was that the Pythagorean triples can instead be thought of as the rational numbers $(x,y)$ on the unit circle, which we have already parameterised.
>More fundamentally, it is often useful to consider geometric interpretations when attempting to find integer solutions to some problem.

