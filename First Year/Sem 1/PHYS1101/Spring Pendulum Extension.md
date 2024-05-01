The following code was used to implement the extension exercise.
```python
Web VPython 3.2

# Constants
mass = 5
rad = 0.2
drag_coeff = 0.7
air_dens = 1.1
area = pi * rad**2
grav = vector(0,-9.8,0)
natural_length = 10
spring_constant = 10
equilibrium_length = mass * mag(grav) / spring_constant + natural_length
pivot = vector(0,10,0)
reso_spring = 2*pi*sqrt(mass/spring_constant)
reso_pendulum = 2*pi*sqrt(equilibrium_length/mag(grav))

print(f"Spring reso: {reso_spring}\nPendulum reso: {reso_pendulum}")

# Initial state
driven_amplitude = 0.2
driven_period = 1.0

graph = gcurve()

# ---- Loop ----
dt = 0.01
while driven_period < 12:
    # Reset state
    max_displacement = 0
    t = 0
    weight = sphere(pos=vector(0,-4.9,0), vel=vector(0,0,0), radius=rad, make_trail=True)
    spring = helix(pos=pivot, axis=(weight.pos - pivot), color=color.blue)
    
    # Run for 100 simulated seconds
    while t<100:
        # Calculate forces and accelerations
        force_spring = spring_constant * (mag(spring.axis) - natural_length)
        acc_spring = -force_spring / mass * norm(spring.axis)
        force_drag = 1/2 * drag_coeff * area * air_dens * mag(weight.vel)**2
        acc_drag = -force_drag / mass * norm(weight.vel)
        
        # Update weight
        weight.vel += (acc_spring + acc_drag + grav) * dt
        weight.pos += weight.vel * dt
        
        # Update spring
        spring.axis = weight.pos - pivot
        pivot = driven_amplitude * vector(sin(2*pi*t/driven_period), cos(2*pi*t/driven_period), 0) + vector(0,10,0)
        spring.pos = pivot
        
        # Update max displacement
        max_displacement = max(max_displacement, mag(weight.pos))
        
        # Increment timestep
        t += dt
    # Increment driven oscillation period
    driven_period += 0.1
    # Graph max_displacement
    graph.plot(driven_period, max_displacement)
```

This gave the following graph as output.
![[Pasted image 20240428172007.png]]

The code also printed the predicted resonance periods to the console.
```
Spring reso: 4.442882938158366
Pendulum reso: 7.747471096974922
```

The predicted resonances very closely matched the graph found through simulation. The small amount of error may be due to the interactions between the spring and pendulum components of the system, the simulated drag or floating-point error in the simulation.
The spring resonance was also found to give a higher peak displacement than the pendulum component. This may be related to the choice of spring constant and acceleration due to gravity.