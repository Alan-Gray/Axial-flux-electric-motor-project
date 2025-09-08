# Estimating Power output
Most of my calculations treat the motor like a generator, as I am more familiar with that. I'm using the equations found in "Axial Flux Permanent Magnet Brushless Machines (2nd edition)" for this. The power estimate centres around calculating an armature constant $K_e$, which specifies the voltage per RPM of the motor. You can find each equation with its book reference below.

## Estimate - Result
The estimated armature constant for a single coil is 0.0058 V/RPM. At 1000 RPM, the coil would generate 5.8 volts. With an internal resistance of 0.2 $\Omega$, it would supply 84 watts to an optimised load (load resistance = internal resistance). However, this would melt the coil, as the current would be larger than the current rating of the wire. I consider this to be a good thing, as it shows that the motor won't be limited by it's magnetic or electrical design.

## Theory
### Armature constant - $K_e$
The equation for the armature contant is: 

$$ 
K_e = \pi\sqrt{2}pN_1k_{w1}\phi_f    \text{ \hspace{1cm} (eq 2.37)}
$$

Where: 
* p is the number of pole pairs 
* $N_1$ is the number of turns in a coil
* $k_{w1}$ is the winding factor
* $\phi_f$ is the flux across the airgap

This is essentially just Faradays law: 

$$V_{emf} = -N\frac{d\phi}{dt}$$

Where $\frac{d\phi}{dt}$ is expressed in terms of $\phi_f$ and RPM. The winding factor $k_{w1}$ is added to account for voltage drops caused by small phase differences within a coil as a magnet passes over them.   

### Airgap flux - $\phi_f$
The airgap flux $\phi_f$ can be found using the equation: 

$$
\phi_f = \alpha_i B_{mg}\frac{\pi}{8p}D_{outer}^2(1-k_d^2) \text{ \hspace{1cm} (eq 2.28)}
$$

Where: 
* $\alpha_i$ is the ratio between the average $B_{avg}$ and peak $B_{mg}$ magnetic flux density, $\frac{B_{avg}}{B_{mg}}$
* p is the number of pole pairs
* $D_{outer}$ is the outer diameter of the rotor
* $k_d$ is the ratio of the inner and outer diameter of the rotor, $\frac{D_{inner}}{D_{Outer}}$

We can simplify $\alpha_i * B_{mg}$ to $B_{avg}$. The average magnetic field strength can be tedious to solve analytically, which is why I used 3D simulations to estimate it. 

### Winding factor - $k_{w1}$
The winding factor $k_{w1}$ is a correction that accounts for small phase differences in parts of a coil/phase as the magents pass over them. The winding factor is the product of the distribution factor $k_{d1}$ and pitch factor $k_{p1}$. 

$$
k_{w1} = k_{d1}k_{p1}
$$
$$
k_{d1} = \frac{sin(\pi/2m_1)}{q_1sin[\pi/(2m_1q_1)]}
$$
$$
k_{p1}= sin(\beta\frac{\pi}{2})
$$
$$
\beta = \frac{w_c(r)}{\tau(r)}
$$

Where: 
* $m_1$ is the number of phases
* $s_1$ is the number of stator slots
* $q_1$ is the number of stator slots per pole per phase
* $\beta$ is the coil-pitch to pole-pitch ratio
* $w_c(r)$ is the coil pitch, $w_c(r) = \frac{\text{number of coils}}{\text{number of poles}}$
* $\tau(r)$ is the pole pitch, $\tau(r) = \frac{s_1}{p}$

