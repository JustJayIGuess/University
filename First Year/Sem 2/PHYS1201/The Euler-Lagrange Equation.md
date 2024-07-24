>[!def]
>The *Euler-Lagrange Equation* is,
>$$\begin{align*}
> \frac{d}{dt}\left(\frac{\partial L}{\partial \dot{x}}\right) &= \frac{\partial L}{\partial x},
>\end{align*}$$
>where $L$ is defined as the difference between the kinetic energy and the potential energy in the case of classical mechanics.
>This equation only applies when all forces are conservative, i.e. are the gradient of some scalar potential field.

>[!example]
>Consider a particle in a one-dimensional potential $V(x)$.
>Then $L = \frac{1}{2}m\dot{x}^{2} - V(x)$.
>So we have $\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{x}}\right) = m\ddot{x}$, and $\frac{\partial L}{\partial x} = -V'(x)$. The net force on the particle in the potential is defined as the gradient of the potential, so we have $F = m\ddot{x}$, or $F=ma$.

>[!example]
>Consider a particle in a three-dimensional potential $V(x,y,z)$.
>Then $L = \frac{1}{2}m(\dot{x}^{2} + \dot{y}^{2} + \dot{z}^{2}) - V(x,y,z)$.
>$$\begin{align*}
>\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{x}}\right) &= m\ddot{x}\\
>\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{y}}\right) &= m\ddot{y}\\
>\vdots
>\end{align*}$$
>And,
>$$\begin{align*}
>\frac{\partial L}{\partial x} &= -\frac{\partial V}{\partial x}\\
>\vdots
>\end{align*}$$
>So then we have,
>$$\begin{align*}
>m \begin{bmatrix}\ddot{x}\\\ddot{y}\\\ddot{z}\end{bmatrix} &= -\nabla V\\
>m\vec{a} &= \vec{F}.
>\end{align*}$$
>Once again we have Newton's second law.

# Polar Coordinates
We first aim to find the kinetic energy (scalar) in polar coordinates, recalling that $K = \frac{1}{2}m\vec{v}^{2}$.
If we have some displacement vector $\vec{r}$ in cartesian coordinates, we can express it as $\vec{r} = x\hat{e}_{x} + y\hat{e}_{y}$. Then $\vec{v}=\frac{d}{dt}\vec{r} = \dot{x}\hat{e}_{x} + \dot{y}\hat{e}_{y}$, so $\vec{v}^{2} = \dot{x}^{2} + \dot{y}^{2} + 2\dot{x}\dot{y}\hat{e}_{x}\hat{e}_{y} = \dot{x}^{2} + \dot{y}^{2}$.
So then $K = \frac{1}{2}m(\dot{x}^{2} + \dot{y}^{2})$.
In polar coordinates $\vec{r} = r\hat{e}_{r}$, with $\hat{e}_{r}(t)$ being a function of time and $\hat{e}_{\theta}(t)$ being perpendicular and in the direction of positive theta. Then $\vec{v} = \frac{d}{dt}(\vec{r}\hat{e}_{r}) = \dot{r}\hat{e}_{r} + r\dot{\hat{e}}_{r}$.
Now note that,
$$\begin{align*}
\frac{d\hat{e}_{r}}{dt} &= \frac{d \theta}{dt}\hat{e}_{\theta},
\end{align*}$$
so then $\vec{v} = \dot{r}\hat{e}_{r} + r\dot{\theta}\hat{e}_{\theta}$. As the two terms are perpendicular, we have,
$K = \frac{1}{2}m\vec{v}^{2} = \frac{1}{2}m(\dot{\vec{r}}^{2} + \vec{r}^{2}\dot{\theta}^{2})$.

# The Simple Pendulum
Consider a mass on the end of a massless rod that rotates about a frictionless pivot.
We will use polar coordinates to model this.
We have the following Euler-Lagrange equations:
$$\begin{align*}
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{r}}\right) &= \frac{\partial L}{\partial r},\\
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{\theta}}\right)&= \frac{\partial L}{\partial \theta}.
\end{align*}$$
We will have $r=L$ always.
The kinetic energy of the mass will be $K = \frac{1}{2}mL^{2}\dot{\theta}^{2}$ as the radius is fixed.
The potential energy above the minimum point at the bottom of the swing is given by $V=mgh=mgL(1-\cos \theta)$.
So then we have,
$$\begin{align*}
L &= \frac{1}{2}mL^{2}\dot{\theta}^{2} - mgL(1-\cos \theta).
\end{align*}$$
Then we have,
$$\begin{align*}
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{r}}\right) &= 0 = \frac{\partial L}{\partial r}\\
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{\theta}}\right) = mL^{2}\ddot{\theta} &= -mgL\sin \theta = \frac{\partial L}{\partial \theta}.\\
\\
\Rightarrow \ddot{\theta} + \frac{g}{L}\sin \theta &= 0.
\end{align*}$$

# Spring Pendulum
The kinetic energy of the mass will be $K = \frac{1}{2}mv^{2} = \frac{1}{2}m(\dot{r}^{2} + r^{2}\dot{\theta}^{2})$. The potential energy will be the sum of the spring energy and the gravitational energy, so, $U = -mgL\cos \theta + \frac{1}{2}k(L-r)^{2}$.
So then $L = K-U$;
$$\begin{align*}
L &= \frac{1}{2}m(\dot{r}^{2} + r^{2}\dot{\theta}^{2}) + mgL\cos \theta - \frac{1}{2}k(L-r)^{2}.
\end{align*}$$
Then in $\hat{e}_{r}$, we have,
$$\begin{align*}
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{r}}\right) &= m\ddot{r} = m\dot{\theta}(2r\ddot{\theta} + \dot{\theta}) = \frac{\partial L}{\partial r}
\end{align*}$$

