# Wires
When analysing DC circuits, we assume that wires have zero resistance, and therefore zero voltage drop, across them. This means that we can deform circuit diagrams to make them easier to understand.

# Resistors
As we assume that resistive components are ideal, we assume that the current flowing through the component is proportional to the voltage across it, i.e.,
$$\begin{align*}
I &= \frac{V}{R}.
\end{align*}$$
Additionally, the power dissipated by the component is,
$$\begin{align*}
P &= VI\\
&= \frac{V^{2}}{R}\\
&= I^{2}R
\end{align*}$$
This approximation is very close for resistors with reasonable amounts of power running through them; when the resistor heats up the model breaks down. Similarly, light bulbs cannot be very accurately modelled like this, as they heat up by design.

# Batteries and Voltage Sources
>[!remark]
>Remember that in the model we use for DC circuits, a battery is only a voltage source, and not a current source.
>This means that, while having batteries in parallel may allow a higher maximum current to be drawn, adding batteries in parallel doesn't change the voltage or current in an ideal circuit.

Ideally, regardless of the load on the voltage source, the voltage will remain the same. In reality, the voltage may drop as the battery has some internal resistance.

# Ammeter
Ammeters measure current.
An ideal measurement doesn't disturb the circuit, so ideally an ammeter should have no effect on the circuit it is measuring. Ammeters are applied in series to a circuit to measure the current running through a point in the circuit.
In reality, the ammeter will have a very low, but non-zero resistance.

# Voltmeters
Voltmeters measure voltage.
Voltmeters are applied in parallel to the circuit to measure the voltage between two sampled points. Ideally this voltmeter will have an infinite resistance so that it doesn't disturb the circuit, however in practise it will have a very large but finite resistance.