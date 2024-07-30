1. Show that the Lagrangian is $L = \frac{1}{2}m\left(\dot{r}^{2} + r^{2}\dot{\theta}^{2}\right) + \frac{GmM_{T}}{r}$.

First note that we have $v = \dot{r}\hat{e}_{r} + r\dot{\theta}\hat{e}_{\theta}$, so then,
$$\begin{align*}
v^{2} &= v\cdot v\\
&= (\dot{r}\hat{e}_{r} + r\dot{\theta}\hat{e}_{\theta})\cdot(\dot{r}\hat{e}_{r} + r\dot{\theta}\hat{e}_{\theta})\\
&= \dot{r}^{2}(\hat{e}_{r}\cdot\hat{e}_{r}) + r^{2}\dot{\theta}^{2}(\hat{e}_\theta\cdot\hat{e}_{\theta})+ (...)(\hat{e}_{r}\cdot\hat{e}_{\theta})\\
&= \dot{r}^{2} + r^{2}\dot{\theta}^{2}.
\end{align*}$$
The kinetic energy is $K=\frac{1}{2}mv^{2} = \frac{1}{2}m(\dot{r}^{2} + r^{2}\dot{\theta}^{2})$, and the potential energy is given by $V = \frac{-GmM_{T}}{r}$, so the Lagrangian is,
$$\begin{align*}
L &= K-V\\
L &= \frac{1}{2}m(\dot{r}^{2}+r^{2}\dot{\theta}^{2}) + \frac{GmM_{T}}{r}.
\end{align*}$$

2. Starting from the definition of the angular momentum $\mathcal{L} = m\vec{r}\times \vec{v}$, show that its magnitude is $|\mathcal{L}| = mr^{2}\dot{\theta}$ and that its initial value is $mb|v_{0}|$.

The magnitude of the cross product $\vec{r}\times \vec{v}$ is equivalent to the area of the parallelogram spanned by $\vec{r}$ and $\vec{v}$.
$\vec{r}$ has length $r$, and the perpendicular height of the parallelogram is the component of $\vec{v}$ in the direction $\hat{e}_{\theta}$. We have that $\vec{v} = \dot{r}\hat{e}_{r} + r\dot{\theta}\hat{e}_{\theta}$, so then,
$$\begin{align*}
|\vec{r}\times\vec{v}| &= (r)(r\dot{\theta})\\
&= r^{2}\dot{\theta}\\
|\mathcal{L}| = |m\vec{r}\times \vec{v}| &= mr^{2}\dot{\theta}.
\end{align*}$$
Initially, the velocity is entirely in the $\hat{e}_{y}$ direction. The perpendicular height of the parallelogram spanned by $\vec{r}_{0}$ and $\vec{v}_{0}$ is then $b$, so we have,
$$\begin{align*}
|\mathcal{L}_{0}| &= |m\vec{r}_{0}\times \vec{v}_{0}|\\
&= mb|\vec{v}_{0}|.
\end{align*}$$

3. Identifying a cyclic variable, show that $|\mathcal{L}|$ is conserved and that,$$\dot{\theta} = \frac{b|\vec{v}_{0}|}{r^{2}}.$$
Inspecting the Lagrangian, we can see that there is no dependence on $\theta$.
$$\begin{align*}
L &= \frac{1}{2}m(\dot{r}^{2}+r^{2}\dot{\theta}^{2}) + \frac{GmM_{T}}{r}
\end{align*}$$
So we have a conserved canonical momentum,
$$\begin{align*}
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{\theta}}\right) &= 0\\
\frac{d}{dt}(mr^{2}\dot{\theta}) &= 0
\end{align*}$$
So the canonical momentum $p_{\theta} = mr^{2}\dot{\theta} = |\mathcal{L}|$ is conserved.
So then $|\mathcal{L}| = mr^{2}\dot{\theta} = mb|\vec{v}_{0}|$. We can rearrange this to show,
$$\begin{align*}
mr^{2}\dot{\theta} &= mb|\vec{v}_{0}|\\
\dot{\theta} &= \frac{b|\vec{v}_{0}|}{r^{2}}.
\end{align*}$$
