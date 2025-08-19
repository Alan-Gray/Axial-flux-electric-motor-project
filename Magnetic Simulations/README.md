# Magnetic Simulations
My goal for my simulations was to compare different designs and determine the magnetic field density in the motor. To do this, I used a mix of 2D and 3D simulations. The 2D simulations were made in FEMM 4.2 and the 3D simulations were made in ANSYS Workbench.

## 2D Simulations: 
The 2D simulations were used to compare my different ideas for the magnetic design. In particualr, I wanted to analyse how stator cores and rotor backing iron would affect the motor performance. I also wanted to determine what magnet grade to use. These were rough comparisons as you cant fully simulate an axial flux motor in two dimensions, but they were still very useful to get an idea of what matters to produce a strong magnetic field.  

### Simulations : 5mm magnets - Coreless vs Cored stator coils
| N38 Coreless| N38 Iron Core |
| :---------: | :-----------: |
| <img width="903" height="717" alt="n38 coreless" src="https://github.com/user-attachments/assets/74accf82-5e00-4a72-ad16-01d9a8118c4f" /> | <img width="773" height="703" alt="n38 core" src="https://github.com/user-attachments/assets/563a9b4d-bbeb-4bf2-b37c-346739ab78cf" /> |
| **N52 Coreless** | **N52 Iron Core** |
| <img width="400" height="366" alt="n52 coreless" src="https://github.com/user-attachments/assets/8c5ae237-d66c-4054-b898-93d79d7f2da4" /> | <img width="367" height="374" alt="n52 core" src="https://github.com/user-attachments/assets/85fae642-588a-476b-b9db-a5951fcd9e2e" />|
   
|<img width="1721" height="761" alt="5mm magnet graph" src="https://github.com/user-attachments/assets/365f5bab-0f25-4ddb-adaf-6b38341e4778" />|
|:--:| 
| *Graph of magnetic field strength across coil centres. The magnetic field density is measured in the middle of the core going from top to bottom.* |

### Simulations : 5mm magnets - Rotor Backing Iron vs No Rotor Backing Iron 
| **N52 Coreless** | **N52 Iron Core** |
| :---------: | :-----------: |
| <img width="653" height="638" alt="iron core no rotor iron pic" src="https://github.com/user-attachments/assets/6003c4c9-69bd-4275-87e2-de21a14aaa9d" />| <img width="413" height="466" alt="iron core and rotor iron" src="https://github.com/user-attachments/assets/23ae702a-4e71-4e58-bd9f-93c49630e8aa" /> |
| <img width="738" height="440" alt="iron core no rotor iron" src="https://github.com/user-attachments/assets/d1882965-4e8d-4fad-a8ac-3da593ab49d1" /> | <img width="738" height="440" alt="iron core and rotor iron graph" src="https://github.com/user-attachments/assets/04452bfa-49bf-4a13-a89a-31d7e12ac4f6" /> |

I knew that stator cores and rotor backing iron would improve performance, but I didn't realise how much of an improvement it would be. Using stator cores more than doubles the magnetic field density, and rotor backing iron doubles it again. The simulations assume the magnetic material is iron which won't be the case for my motor (its to expensive), but it is still clear that I should include both stator cores and backing iron in the motor.   

The N52 magnets had roughly 16% higher magnetic field density than the N38 magnets, which alligns with datasheets available online. N38 magnets are much cheaper, which can be appealing if you're buying them in bulk. I'll be making a small order so I chose to use the N52 magnets. 

## 3D Simulations: 
After deciding to include both stator cores and rotor backing iron in the motor, I stared working on the 3D simulations to validate my findings and determine a more accurate figure for the magnetic field density. Whilst I had a good amount of experience using 2D simulations, 3D simulations were something new for this project. 

Orignially, I wanted to use ANSYS Maxwell. However, the student license imposed a mesh limit, making it hard for me simulate the full motor. After some searching, I found that some of the university computers had a full license of ANSYS Workbench. It was older and had less features, but it was sufficient for my use case. I had to do alot of troubleshooting to get it working and it was very satifying to see the first results of the simulations.

|<img width="1613" height="1238" alt="sim3" src="https://github.com/user-attachments/assets/1ad5a047-61dc-413a-b529-c1c3289ea933" />|
|:--:| 
|<img width="1920" height="1200" alt="2mm rotor 3" src="https://github.com/user-attachments/assets/c8f1b037-d327-406b-a27f-d5210aed20a2" />|
|:--:|
|*3D magnetic simulations*|

I got a couple insights from the 3D simulations that I previously hadn't considered. First, the centre of the rotor backing iron doesnt carry any flux (as seen above in the grey zone on the backing iron) meaning it can be removed without any decrease in magnetic performance. Secondly, only the cores of the stator should be made out of magnetic material or wierd flux paths arise. I originally thought I would need to maximize the surface that could "catch" the magnetic field which would "funnel" into the core, but this was incorrect. 


## Learning more about FEA 
Whilst I was looking for a different software to use, I found an open source program called Elmer GUI. It was more complex and hard to use but it forced me to understand more about finite element simulaitions and how they work. This included making my own mesh from step files using GMSH and playing around with non linear and linear convergence tolerances and iteration counts. 

|<img width="1031" height="861" alt="Screenshot 2025-05-28 123052" src="https://github.com/user-attachments/assets/69edb2bb-1c57-416d-980c-96242bfc202c" />|
|:--:|
| *My first simulation in elmer after following an online tutorial* |



|<img width="1413" height="1270" alt="mesh" src="https://github.com/user-attachments/assets/798cda8e-51b9-436b-bf34-197dbadb933a" /> |
|:--:|
|*mesh made in GMSH and imported into Elmer GUI*|
