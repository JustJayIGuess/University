>[!theorem]
>If $f,g$ are integrable on $[a,b]$, and we have $c\in \mathbb{R}$. Then $fg,cf,f+g$ are all integrable on $[a,b]$.

>[!theorem]
>If we have real numbers $a<b<c$, then
>$$\begin{align*}\int_{a}^{c}f\text{ exists}\Rightarrow \int_{a}^{b}f\text{ and }\int_{b}^{c}f \text{ exist}.\\ \int_{a}^{b}f \text{ and }\int_{b}^{c}f \text{ exist}\Rightarrow \int_{a}^{c}f\text{ exists}.\end{align*}$$

>[!theorem]
>Suppose $f$ is integrable on $[a,b]$, and define $F : [a,b] \longrightarrow \mathbb{R}$ with $F(x) = \int_{a}^{x}f$. Then $F$ is continuous.
>
>>[!proof]
>>We would like to show that,
>>$$\begin{align*}\lim_{x \longrightarrow c}F(x) &= F(c)\\
>>\lim_{x \longrightarrow c}\int_{a}^{x}f &= \int_{a}^{c}f.
>>\end{align*}$$
>>Note that for $x<c$, we have,
>>$$\begin{align*}
>>\int_{a}^{c}f &= \int_{a}^{x}f + \int_{x}^{c}f.
>>\end{align*}$$
>>Therefore we will aim to show that,
>>$$\begin{align*}
>>\lim_{x \longrightarrow c^{-}}\int_{x}^{c}f &= 0.
>>\end{align*}$$
>>$f$ is bounded, so we can let $m = \inf\left\{f(y) \mid y\in[a,b]\right\}$, $M = \sup\left\{f(y) \mid y\in[a,b]\right\}$. Then we have that,
>>$$\begin{align*}
>>m(c-x)\le \int_{x}^{c}f\le M(c-x).
>>\end{align*}$$
>>However the left and right side will approach zero as $x$ approaches $c$, so by the squeeze theorem, we have that,
>>$$\begin{align*}
>>\lim_{x \longrightarrow c^{-}}\int_{x}^{c}f &= 0.
>>\end{align*}$$

>[!theorem]
>In addition, suppose $f$ is continuous at $c\in(a,b)$. Then $F$ is differentiable at $c$ and $F'(c)=f(c)$.
>
>>[!proof]
>>We are interested in the expression,
>>$$\begin{align*}
>>\lim_{h \longrightarrow 0^{\pm}}\frac{F(c+h)-F(c)}{h} &= F'(c).
>>\end{align*}$$
>>Now note that,
>>$$\begin{align*}
>>F(c+h)-F(c) &= \int_{a}^{c+h}f - \int_{a}^{c}f = \int_{c}^{c+h}f.
>>\end{align*}$$
>>Now, we will let,
>>$$\begin{align*}
>>m_{h} &= \inf\left\{f(x) \mid c\le x \le c+h\right\}\Rightarrow (m_{h})(h)\le L(f,P)\forall P\text{ on }[c,c+h]\\
>>M_{h} &= \sup\left\{f(x) \mid c \le x\le c+h\right\}\Rightarrow (M_{h})(h)\ge U(f,P)\forall P\text{ on }[c,c+h].\\
>>&\Rightarrow m_{h}h\le \int_{c}^{c+h}f \le M_{h}h\\
>>&\Rightarrow m_{h}\le \frac{\int_{c}^{c+h}f}{h}\le M_{h}\\
>>&\Rightarrow m_{h}\le \frac{F(c+h)-f(c)}{h}\le M_{h}.
>>\end{align*}$$
>>Now, let $h \rightarrow 0^{+}$. We claim that $\lim_{h \longrightarrow 0^{+}}m_{h} = \lim_{h \longrightarrow 0^{+}}M_{h} = f(c)$. Recalling that $f$ is continuous at $c$, we can attain this result. Therefore, by the squeeze theorem, we have that $F$ is differentiable at $c$ with $F'(c)=f(c)$.

>[!theorem]
>If $f$ is integrable on $[a,b]$ and $f=g'$, then $\int_{a}^{b}f = g(b)-g(a)$.
>
>>[!proof]
>>Recall the [[Continuity#Theorems of Continuity|mean value theorem]]. So there is some $c\in[a,b]$ such that,
>>$$\begin{align*}
>>\frac{g(b)-g(a)}{b-a} &= g'(c)\\
>>g(b)-g(a)&= (b-a)g'(c)\\
>>g(b)-g(a) &= (b-a)f(c).
>>\end{align*}$$
>>$f$ is integrable and therefore bounded, so then we take the infimum $m$ and supremum $M$ to get,
>>$$\begin{gather*}
>>m \le f(c) \le M\\
>>m(b-a)\le g(b)-g(a)\le M(b-a).
>>\end{gather*}$$
>>Now take some partition of $[a,b]$, $P$, with $t_{i}\in P$. Then,
>>$$\begin{align*}
>>\exists c_{i}\in[t_{i-1},t_{i}]\text{ s.t. } \frac{g(t_{i})-g(t_{i-1})}{t_{i}-t_{i-1}} &= g'(c_{i})\\
>>m_{i}\le f(c_{i}) \le M_{i}\\
>>\Rightarrow m_{i}(t_{i}-t_{i-1})\le g(t_{i})-g(t_{i-1})&\le M_{i}(t_{i} - t_{i-1}).
>>\end{align*}$$
>>Now if we add these,
>>$$\begin{align*}
>>\underbrace{\sum\limits_{i}m_{i}(t_{i}-t_{i-1})}_{L(f,P)}\le g(b)-g(a)\le \underbrace{\sum\limits_{i}M_{i}(t_{i}-t_{i-1})}_{U(f,P)}.
>>\end{align*}$$
>>Then, as $f$ is integrable, $U(f,P) - L(f,P)\rightarrow 0$ for some sequence of partitions $P_{n}$, with each approaching $\int_{a}^{b} f$, so then by the squeeze theorem, $g(b)-g(a)=\int_{a}^{b} f$.

