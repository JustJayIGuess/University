>[!question] Question 1.
>Show that the Lagrangian is $L = \frac{1}{2}m\left(\dot{r}^{2} + r^{2}\dot{\theta}^{2}\right) + \frac{GmM_{T}}{r}$.

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

>[!question] Question 2.
> Starting from the definition of the angular momentum $\mathcal{L} = m\vec{r}\times \vec{v}$, show that its magnitude is $|\mathcal{L}| = mr^{2}\dot{\theta}$ and that its initial value is $mb|v_{0}|.$

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

>[!question] Question 3.
>Identifying a cyclic variable, show that $|\mathcal{L}|$ is conserved and that,
>
>$$\dot{\theta} = \frac{b|\vec{v}_{0}|}{r^{2}}.$$

Inspecting the Lagrangian, we can see that there is no dependence on $\theta$.
$$\begin{align*}
L &= \frac{1}{2}m(\dot{r}^{2}+r^{2}\dot{\theta}^{2}) + \frac{GmM_{T}}{r}
\end{align*}$$
So we have a conserved canonical momentum,
$$\begin{align*}
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{\theta}}\right) &= 0\\
\frac{d}{dt}(mr^{2}\dot{\theta}) &= 0.
\end{align*}$$
So the canonical momentum $p_{\theta} = mr^{2}\dot{\theta} = |\mathcal{L}|$ is conserved.
So then $|\mathcal{L}| = mr^{2}\dot{\theta} = mb|\vec{v}_{0}|$. We can rearrange this to show,
$$\begin{align*}
mr^{2}\dot{\theta} &= mb|\vec{v}_{0}|\\
\dot{\theta} &= \frac{b|\vec{v}_{0}|}{r^{2}}.
\end{align*}$$

>[!question] Question 4.
> Show that the equation of motion for $r$ can be expressed in the form $\ddot{r} = \frac{A}{r^{3}} - \frac{B}{r^{2}}$. Give the expressions for $A$ and $B$.

We can use the Euler-Lagrange equation in $r$ to get the equation of motion for $\ddot{r}$.
$$\begin{align*}
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{r}}\right) &= \frac{\partial L}{\partial r}\\
m\ddot{r} &= mr\dot{\theta}^{2} - \frac{GM_{T}m}{r^{2}}\\
\ddot{r} &= r\left(\frac{b|\vec{v}_{0}|}{r^{2}}\right)^{2} - \frac{GM_{T}m}{r^{2}}\\
\ddot{r} &= \frac{b^{2}\vec{v_{0}}^{2}}{r^{3}} - \frac{GM_{T}m}{r^{2}}\\
\\
A = b^{2}\vec{v_{0}}^{2}&,\quad B=GM_{T}m.
\end{align*}$$

>[!question] Question 5.
>The solution to the above equation of motion is plotted in the bottom-right part of the figure (solid line). Will the asteroid hit the Earth? Assuming that at $t = 0$ the variation of $\theta$ is small enough so that the velocity vector is $v_{0} = \dot{r}\hat{e}_{r} + r\dot{\theta}\hat{e}_{\theta} \approx \dot{r}\hat{e}_{r}$, give $|v_{0}|$ in km/s? Noting that near $r_{\text{min}}$ this approximation is not valid anymore evaluate the velocity $|v|$ when $r = r_{\text{min}}$ in km/s?

![[Pasted image 20240730191820.png|400]]

The plotted graph shows that the closest approach of the asteroid is at $1\times 10^{7}\text{m}$. The radius of the Earth is $\frac{d}{2} = \frac{12.7}{2}\times 10^{6} = 6.35\times 10^{6}\text{m}$, so the asteroid will not hit the Earth.
The graph has a slope of $\dot{r} = \frac{0 - 3\times 10^{7}}{3\times 10^{3}} = 10^{4}\text{m/s} = 3.6\times10^{5}\text{km/hr}$. So then $|\vec{v}_{0}| \approx 10^{4}\text{m/s}$.
$$\begin{align*}
\dot{\theta} &= \frac{b|\vec{v}_{0}|}{r^{2}}\\
&= \frac{(1.3\times10^{7})(10^{4})}{(10^{7})^{2}}\\
&= 1.3\times 10^{-3}\text{rad/s}
\end{align*}$$
Then, as $\vec{v} = \dot{r}\hat{e}_{r} + r\dot{\theta}\hat{e}_{\theta}$ and $\dot{r}\approx 0$. So $|\vec{v}| \approx r\dot{\theta}\hat{e}_{\theta}$.
$$\begin{align*}
|\vec{v}| &\approx 1\times10^{7}\times 1.3\times 10^{-3}\\
|\vec{v}|&\approx 1.3\times 10^{4}\text{m/s}.
\end{align*}$$
