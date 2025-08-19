# Coil Winding and Electrical Design

|<img width="1053" height="1068" alt="coil" src="https://github.com/user-attachments/assets/5f0fc5c2-65ef-4652-a312-34c36b6c230f" />|
|:--:| 
| *A coreless coil* |

The electrical design focused on lowering the internal resistance of the coils. The largest contributor to the internal resistance is the thickness of the wire. Thicker wire will have less resistance and can handle higher currents, but the voltage will be lower due to fewer turns in the coil. 

I chose to use use the thickest wire I had available, which was 18 gauge wire (1 mm diameter). Each coil had 50 turns of wire, which I wound by hand. I think 18 AWG wire is the thickest wire I can reasonably wind by hand, if I want to use thicker wire for a future version of the motor Ill need to make a specialized winder of some kind. 

The impedance of the coils was measured using an impedance analyser. The impedance of a single coil was around 0.2 Ohms for low frequencies (<1kHz). The previous version had 10 Ohms per coil, so the new motor has 50 times less internal resistance per coil.


