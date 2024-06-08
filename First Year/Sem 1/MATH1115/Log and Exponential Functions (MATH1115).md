>[!note]
>$\log$ will refer only to $\log_e$ in the course.

>[!def]
>For $x>0$, we will define,
>$$\begin{align*}
>\log(x) := \int_{1}^{x} \frac{1}{t}dt.
>\end{align*}$$
>>[!remark]
>>For $0<x<1$, we have,
>>$$\begin{align*}
>>\log(x) &= \int_{1}^{x} \frac{1}{t}dt = -\int_{x}^{1} \frac{1}{t}dt.
>>\end{align*}$$

>[!def]
>We will now define, for any $x\in\mathbb{R}$,
>$$\begin{align*}
>\exp(x) := (\log)^{-1}(x).
>\end{align*}$$
>We now also define $e = \exp(1)$.

# Properties of $\log$ and $\exp$
By the fundamental theorem of calculus, we have,
$$\begin{align*}
\log' x &= \frac{d}{dx}\left(\int_{1}^{x} \frac{1}{t}dt\right) = \frac{1}{x}.
\end{align*}$$
Now by chain rule, we also have,
$$\begin{align*}
\int \frac{g'}{g} &= \log g.
\end{align*}$$

>[!theorem]
> $$\begin{align*}
> \log xy &= \log x + \log y
> \end{align*}$$
>>[!proof]
>>Fix $y>0$, and let $f(x) = \log(xy)$.
>>Then $f'(x) = \frac{1}{xy}y = \frac{1}{x}$. So then $f'=log'\Rightarrow f=\log x + c$.
>>Now let $x=1$. We have $f(1y)=\log 1 + c = c = f(y)$.
>>So then $\log xy = \log x + \log y$.

>[!question]
>Suppose that $1 = \int_{1}^{m} \frac{1}{t}dt$. What is the mystery number $m$?
>>[!check] Solution.
>>Then we have,
>>$$\begin{align*}
>>\int_{1}^{x} \frac{1}{t}dt &= \log x\\
>>\Rightarrow \log m &= 1\\
>>\Rightarrow m=e.
\end{align*}$$


>[!theorem]
>$\exp(x)=e^{x}\ \forall x\in \mathbb{R}$.
>>[!lemma]
>>$\exp(x+y) = (\exp x)(\exp y)$.
>>>[!proof]
>>>$$\begin{align*}
>>>x &= \log(\exp(x))\\
>>>y &= \log(\exp(y)),\ \forall x,y\in \mathbb{R}\\
>>>\\\\
>>>x+y &= \log(\exp(x)) + \log(\exp(y))\\
>>>x+y &= \log[(\exp x)(\exp y)]\\
>>>\exp(x+y) &= \exp(\log[(\exp x)(\exp y)])\\
>>>\exp(x+y) &= (\exp x)(\exp y).
\end{align*}$$
>
>>[!proof]
>>Then consider $\exp(2)$. We have that this is $\exp(1+1)=\exp(1)\exp(1)=ee=e^{2}$. By induction we can continue this to show that $\exp(n)=e^{n}\ \forall n\in\mathbb{N}$.
>>Now consider $\exp(n+0) = \exp(n)\exp(0)=e^{n}$. Then $\exp(0)=1=e^{0}$.
>>Now consider $\exp(0)=\exp(n+(-n))=\exp(n)\exp(-n)=1$. So then we have that $\exp(-n) = \frac{1}{e^{n}}$.
>>So we now have $\exp(n)=e^{n}\ \forall n\in\mathbb{Z}$. We can further use similar arguments to eventually show that this also holds for $n\in \mathbb{Q}$.
>>
>>Now, as the rational numbers are dense, and $\exp$ is continuous, we can further define that $\exp(x)=e^{x}$ for all $x\in \mathbb{R}$.

>[!theorem]
>$\exp' = \exp$.
>
>>[!proof]
>>Consider $(\log^{-1})'$, using the fact that,
>>$$\begin{align*}
>>(f^{-1})'(x) &= \frac{1}{f'(f^{-1}(x))}.
>>\end{align*}$$
>>So then,
>>$$\begin{align*}
>>\exp'x &= \frac{1}{\frac{1}{\exp(x)}}=\exp x.
\end{align*}$$

# Growth

>[!remark]
>$\exp$ grows **very fast**.

>[!theorem]
>For any $n\in \mathbb{N}$, we have that,
>$$\begin{align*}
>\lim_{x \longrightarrow \infty} \frac{e^{x}}{x^{n}} &= \infty.
>\end{align*}$$
>I.e.,
>$$\begin{align*}
>\forall k\in \mathbb{N},\ \exists m\text{ s.t.} x>m\\
>\Rightarrow \frac{e^{x}}{x^{n}} > k.
>\end{align*}$$
>>[!proof] Sketch Proof.
>>This can be proven by first noting that $x > \log x\Rightarrow e^{x} > x$. This can itself be proven by considering upper bounds on $\log(x)$.
>>
>>Now suppose $n=1$. Then, recalling the previous lemma, we have,
>>$$\begin{align*}
>>\frac{e^{x}}{x} &= \frac{e^{\frac{x}{2}}e^{\frac{x}{2}}}{\frac{x}{2}\times 2}\\
>>&= \frac{1}{2} \left(\frac{e^{\frac{x}{2}}}{\frac{x}{2}}\right)e^{\frac{x}{2}} > \frac{1}{2}e^{\frac{x}{2}}.
>>\end{align*}$$
>>This same outline can be used to prove this statement for all $n$.

>[!remark]
>**P vs NP**
>If a problem is solvable in polynomial time then it is in P. If a problem is verifiable in polynomial time then it is in NP.

