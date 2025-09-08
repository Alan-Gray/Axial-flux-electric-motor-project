# Electrical Design

|<img width="600" height="600" alt="coil" src="https://github.com/user-attachments/assets/5f0fc5c2-65ef-4652-a312-34c36b6c230f" />|
|:--:| 
| *A coreless coil* |

The electrical design focused on lowering the internal resistance of the coils. The largest contributor to the internal resistance is the thickness of the wire. Thicker wire will have less resistance and can handle higher currents, but the voltage will be lower as there are fewer turns in the coil. 

I chose to use use the thickest wire I had available, which was 18 gauge wire (1 mm diameter). Each coil had 50 turns of wire, which I wound by hand. 18 AWG wire is the thickest wire I can reasonably wind by hand, and if I want to use thicker wire Ill need to make a specialized winder of some kind. 

The impedance of the coils was measured using an impedance analyser. The impedance of a single coil was around 0.2 Ohms for low frequencies (<1kHz). The previous version had 10 Ohms per coil, so the new motor has 50 times less internal resistance per coil.

# Estimating Power Output - Theory
I'm using the equations found in "Axial Flux Permanent Magnet Brushless Machines (2nd edition)" to make my power calculations. My estimate centres around calculating an armature constant $K_e$, which specifies the voltage per RPM of the motor. Each equation will have its reference beside it so you can find them in the book.

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

## Estimating Power output - Results
From my calculations, I calculated the armature constant for a single coil to be 0.0058 V/RPM
