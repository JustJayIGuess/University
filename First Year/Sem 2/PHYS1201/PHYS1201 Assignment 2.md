>Jay Johnston, u7922560

>[!question] Question 1.
>![[Pasted image 20240809164531.png]]

![[Pasted image 20240809164554.png]]

First, observe that the total kinetic energy of the system with respect to the centre of mass is,
$$
K = \frac{1}{2}m(\dot{x_{1}}^{2} + \dot{x_{2}}^{2}),
$$
where $x_1(t),x_2(t)$ are the positions of the two electrons in Cartesian coordinates. The two electrons are of equal mass, however, so the centre of mass is the midpoint of the two position vectors. As $x_1,x_2$ are relative to this centre of mass, we then have that,
$$\begin{align*}
x_{1} &= -x_{2}\\
\dot{x}_{1} &= -\dot{x}_{2}\\
\dot{x}_{1}^{2}&= \dot{x}_{2}^{2}.
\end{align*}$$
So then we have the following expression of kinetic energy.
$$\begin{align*}
K &= \frac{1}{2}m(2\dot{x}_{1}^{2})\\
&= m\dot{x}_{1}^{2}.
\end{align*}$$
The separation vector $x$ between $x_{1}$ and $x_{2}$ then has magnitude,
$$\begin{align*}
|x| &= 2|x_{1}| \Rightarrow |\dot{x}_{1}| = \frac{1}{2}|\dot{x}|.
\end{align*}$$
So then we can express kinetic energy as,
$$\begin{align*}
K &= m(\frac{1}{2}|\dot{x}|)^2\\
&= \frac{1}{4}m\dot{x}^{2}.
\end{align*}$$
If we now replace $x$ with the equivalent separation vector $r$ in polar form, recalling that $\dot{x}^{2} = \dot{r}^{2} + r^{2}\dot{\theta}^{2}$, we have,
$$\begin{align*}
K &= \frac{1}{4}m(\dot{r}^{2} + r^{2}\dot{\theta}^{2}).
\end{align*}$$
Electric potential of point charges is given by,
$$\begin{align*}
V &= k\frac{q_{1}q_{2}}{r}.
\end{align*}$$
Taking $q_1,q_2$ to both be the charge on an electron, $e$, we then  have,
$$\begin{align*}
V &= \frac{ke^{2}}{r}.
\end{align*}$$
The Lagrangian is defined as $L = K-V$, so we finally have,
$$\begin{align*}
L &= K-V\\
&= \frac{1}{4}m(\dot{r}^{2} + r^{2}\dot{\theta}^{2}) - \frac{ke^{2}}{r}.
\end{align*}$$

![[Pasted image 20240809165852.png]]

The expression for the Lagrangian given in the previous question has no dependence on $\theta$, i.e., $\frac{\partial L}{\partial \theta} = 0$, so we have a canonical momentum $p_{\theta}$ given by,
$$\begin{align*}
p_{\theta} &= \frac{\partial L}{\partial \dot{\theta}}\\
&= \frac{1}{2}mr^{2}\dot{\theta}.
\end{align*}$$
This is the total angular momentum around the centre of mass in the system.

![[Pasted image 20240809170226.png]]

The phasor associated with either path is given by,
$$\begin{align*}
e^{\frac{iS_{0}}{\hbar}},
\end{align*}$$
so the overall probability amplitude is,
$$\begin{align*}
\varphi &= N\sum\limits_\text{paths} e^{\frac{iS}{\hbar}}\\
&= N\left(e^{\frac{iS_{0}}{\hbar}} + e^{\frac{iS_{0}}{\hbar}}\right)\\
&= 2Ne^{\frac{iS_{0}}{\hbar}}.
\end{align*}$$
The two phasors constructively interfered as they were identical.

![[Pasted image 20240809171724.png]]

The probability amplitude is now given by the following, as the two phasors are no longer identical.
$$\begin{align*}
\varphi &= N(e^{i\frac{S_{0}+\delta S}{\hbar}} + e^{i\frac{S_{0}-\delta S}{\hbar}})\\
&= Ne^{\frac{iS_{0}}{\hbar}}(e^{\frac{i\delta S}{\hbar}} + e^{\frac{-i\delta S}{\hbar}}).
\end{align*}$$
Now recall the identity that $2\cos\theta = e^{i\theta} + e^{-i\theta}$, allowing the above to be simplified to,
$$\begin{align*}
\varphi &= Ne^{\frac{iS_{0}}{\hbar}}\cos\left(\frac{\delta S}{\hbar}\right).
\end{align*}$$
Then the probability is given by,
$$\begin{align*}
P &= |\varphi|^{2}\\
&= N^{2}\cos^{2}\left(\frac{\delta S}{\hbar}\right),
\end{align*}$$
as $|e^{\frac{iS_{0}}{\hbar}}|=1$. So then the number of detected electrons is proportional to $\cos^{2}\left(\frac{\delta S}{\hbar}\right)$.

![[Pasted image 20240809173251.png]]

The first destructive interference occurs when $\cos^{2}(\frac{\delta S}{\hbar})=0\Leftrightarrow \cos\left(\frac{\delta S}{\hbar}\right)= 0.$ The first time this happens is when $\frac{\delta S}{\hbar} = \frac{\pi}{2}$;
$$\begin{align*}
\frac{\delta S}{\hbar} &= \frac{\pi}{2}\\

\end{align*}$$