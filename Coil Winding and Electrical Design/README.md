# Coil Winding and Electrical Design

|<img width="600" height="600" alt="coil" src="https://github.com/user-attachments/assets/5f0fc5c2-65ef-4652-a312-34c36b6c230f" />|
|:--:| 
| *A coreless coil* |

The electrical design focused on lowering the internal resistance of the coils. The largest contributor to the internal resistance is the thickness of the wire. Thicker wire will have less resistance and can handle higher currents, but the voltage will be lower as there are fewer turns in the coil. 

I chose to use use the thickest wire I had available, which was 18 gauge wire (1 mm diameter). Each coil had 50 turns of wire, which I wound by hand. 18 AWG wire is the thickest wire I can reasonably wind by hand, and if I want to use thicker wire Ill need to make a specialized winder of some kind. 

The impedance of the coils was measured using an impedance analyser. The impedance of a single coil was around 0.2 Ohms for low frequencies (<1kHz). The previous version had 10 Ohms per coil, so the new motor has 50 times less internal resistance per coil.

## Estimating Power output and calculations

I used the equations found in the book "Axial Flux Permanent Magnet Brushless Machines (2nd edition)" to make my power output estimations. My estimation centred around calculating an armature constant $K_e$, which specifies the voltage per RPM of the motor. The following equations were used to estimate the armature constant for a single coil. 

The equation for the armature contant is: 
$$
K_e = \pi\sqrt{2}pN_1k_{w1}\phi_f
$$
Where: 
* p is the number of pole pairs
* $N_1$ is the number of turns in a coil
* $k_{w1}$ is the winding factor
* $\phi_f$ is the flux across the airgap

#$$
\phi_f = \alpha_i B_{mg}\frac{\pi}{8p}D{outer}^2(1-k_d^2)
$$
