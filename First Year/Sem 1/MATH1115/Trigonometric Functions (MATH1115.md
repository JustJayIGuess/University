>[!question]
>How should we go about defining trigonometric functions?
>
>>[!info] Suggestion.
>>Let $x$ be an arclength along the unit circle from $(1,0)$. Then we have the point $(\cos(x),\sin(x))$.
>
>>[!check] Answer.
>>We may use area to define trigonometric functions in terms of functions that we have already studied.

>[!def]
>$$\begin{align*}
>\pi := 2\int_{-1}^{1}\sqrt{1-x^{2}}dx.
\end{align*}$$
>
> ![[Trigonometric Functions (MATH1115 2024-05-09 12.18.23.excalidraw]]

>[!def]
>For any $-1\le x \le 1$, define,
>$$\begin{align*}
>A(x)=\frac{1}{2}x\sqrt{1-x^{2}} + \int_{x}^{1}\sqrt{1-t^{2}}dt
>\end{align*}$$
>
>>[!example]
>>$$\begin{align*}
>>A(1) &= \frac{1}{2}(1)\sqrt{1^{2}-1}+\int_{1}^1\sqrt{1-t^{2}}dt\\
>>&= 0 = \frac{1}{2}(0)\\
>> A(0) &= \frac{1}{2}(0)\sqrt{0^{2}-1} + \int_{0}^{1}\sqrt{1-t^{2}}dt\\
>>&= \frac{\pi}{4} = \frac{1}{2}\left(\frac{\pi}{2}\right)\\
>> A(-1) &= \frac{\pi}{2}= \frac{1}{2}(\pi)
>> \end{align*}$$

>[!def]
>For $x\in[0,\pi]$, define,
>$$\begin{align*}
>\cos(x) := \text{`$\cos(x)$' such that }A(\cos(x))=\frac{x}{2}
>\end{align*}$$
>
>>[!note]
>>$A(x)$ is decreasing, so it is injective and therefore has an inverse.
>
>So then,
>$$\begin{align*}
>A^{-1}(A(\cos(x))) &= A^{-1}\left(\frac{x}{2}\right)\\
>\cos(x) &= A^{-1}\left(\frac{x}{2}\right)
>\end{align*}$$

>[!def]
>Define $\sin(x)=\sqrt{1 - \cos^{2}(x)}$.

>[!lemma]
>$\cos'(x) = -\sin(x)$.
>>[!proof]
>>$$\begin{align*}
>>A'(x) &= \frac{d}{dx}\left(\frac{1}{2}x\sqrt{1-x^{2}}\right) + \frac{d}{dx}\left(\int_{x}^{1}\sqrt{1-t^{2}}dt\right)\\
> &= \frac{1}{2}\left(x \frac{d}{dx}(\sqrt{1-x^{2}})+\sqrt{1-x^{2}}\right) + [\sqrt{1-t^{2}}]|_{x}^{1}\\
> &= \frac{1}{2}\left(x \frac{d}{dx}(\sqrt{1-x^{2}})+\sqrt{1-x^{2}}\right) - \sqrt{1-x^{2}}\\
> &= \frac{1}{2}x\frac{d}{dx}(\sqrt{1-x^{2}}) - \sqrt{1-x^{2}}\\
> &= \frac{-1}{2\sqrt{1-x^{2}}}.
>> \end{align*}$$
>> $$\begin{align*}
>>(f^{-1})'(f(x)) &= \frac{1}{f'(x)}\\
>>\therefore (f^{-1})'(x) &= \frac{1}{f'(f^{-1}(x))}.
>>\end{align*}$$
>>So then we have that,
>>$$\begin{align*}
>>\cos(x) &= \left(2A\left(\frac{x}{2}\right)\right)^{-1}\\
>>\cos'(x) &= \frac{1}{\left(2A\left(\frac{x}{2}\right)\right)^{-1}\left(\left(2A\left(\frac{x}{2}\right)\right)^{-1}(x)\right)}\\
>>&= \frac{1}{\frac{-1}{\sqrt{1-\cos^{2}(x)}}}\\
>>&= -\sqrt{1-\cos^{2}(x)}\\
>>&= -\sin(x)
\end{align*}$$
