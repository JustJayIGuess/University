>[!remark]
>Recall that $f\in X\times Y$ is a function only if, for each $x\in X$, there is one unique $y_{x}\in  Y$ with $(x,y_{x})\in f$.
>Now consider switching the ordering of $(x,y_{x})$, i.e., $(x,y_{x})\mapsto(y_{x}, x)$
>This will only be a valid function if $f$ is injective, i.e., $f(x_{1})=f(x_{2})\Rightarrow x_{1}=x_{2}$.
>Note also that the new function must be defined on all $y\in Y$, so $f$ must be surjective also.

>[!def]
>Take some injective $f\in X\times Y$, i.e.,
>$$f(x_{1})=f(x_{2})\Rightarrow x_{1}=x_{2}.$$
>We now define the *inverse* $f^{-1} : \text{im}(f)\longrightarrow X$ as the function $f^{-1} = \left\{(y,x)\right\}$. Note that this is surjective by definition; we discard elements in the codomain that are not hit by $f$. This can be thought of as defining an intermediary function,
>$$\hat{f} : X\longrightarrow \text{im}(f)$$
>This is done in calculus, however we should consider surjectivity in other fields such as linear algebra.
>Note that $(f^{-1})^{-1} = f$.
>
>The inverse be thought of geometrically as reflecting the graph along the line $y=x$.

>[!example]
>If $f(x)=x^{3}$, we have $f^{-1} = \sqrt[3]{x}$.

>[!def]
>We define the *pre-image* of a subset $B$ in the context of a function $f : X \longrightarrow Y$ with $A\subseteq X$ and $B\subseteq Y$ as,
>$$\begin{align*}
f^{-1}(B) &= \left\{x\in X \mid f(x)\in B\right\}.
\end{align*}$$
>This does not require injectivity, however if the function is invertible, $f^{-1}(y_{0})=f^{-1}(\left\{y_{0}\right\})$, where the left $f^{-1}$ is the inverse and the other is the pre-image.
