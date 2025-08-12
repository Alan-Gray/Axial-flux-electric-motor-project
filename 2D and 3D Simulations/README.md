# Magnetic Simulations
My goal for my simulations was to compare different designs and accurately determine the magnetic field density in the motor. To do this, I used a mix of 2D and 3D simulations. 

## 2D Simulations: 
The 2D simulations were used to compare my different ideas for the magnetic design. In particualr, I wanted to analyse how stator cores and rotor backing iron would affect the motor performance. My 2D simulations were made using FEMM 4.2.

### Simulations: 3mm magnets
| N38 Coreless| N38 Iron Core |
| :---------: | :-----------: |
|   <img width="300" height="400" alt="n38 coreless" src="https://github.com/user-attachments/assets/a4df24cc-7f22-4f6d-b442-360963e9af53" /> |  <img width="300" height="400" alt="n38 core" src="https://github.com/user-attachments/assets/ff126fdc-4c24-4f8a-a523-b958be218edb" /> |
| **N52 Coreless** | **N52 Iron Core** |
|     <img width="300" height="400" alt="n52 coreless" src="https://github.com/user-attachments/assets/324e899a-66cd-4aae-9350-e6c4c2b0363f" /> | <img width="300" height="400" alt="n52 core" src="https://github.com/user-attachments/assets/90b21da8-5861-4157-bf5e-38df54a81733" /> |

|<img width="1762" height="880" alt="3mm magnet graph" src="https://github.com/user-attachments/assets/6437bf9d-1194-4366-8302-0d9aab899e08" />|
|:--:| 
| *Graph of magnetic field strength across coil centres* |

### Simulations: 5mm magnets
| N38 Coreless| N38 Iron Core |
| :---------: | :-----------: |
| <img width="903" height="717" alt="n38 coreless" src="https://github.com/user-attachments/assets/74accf82-5e00-4a72-ad16-01d9a8118c4f" /> | <img width="773" height="703" alt="n38 core" src="https://github.com/user-attachments/assets/563a9b4d-bbeb-4bf2-b37c-346739ab78cf" /> |
| **N52 Coreless** | **N52 Iron Core** |
| <img width="400" height="366" alt="n52 coreless" src="https://github.com/user-attachments/assets/8c5ae237-d66c-4054-b898-93d79d7f2da4" /> | <img width="367" height="374" alt="n52 core" src="https://github.com/user-attachments/assets/85fae642-588a-476b-b9db-a5951fcd9e2e" />|
   
|<img width="1721" height="761" alt="5mm magnet graph" src="https://github.com/user-attachments/assets/365f5bab-0f25-4ddb-adaf-6b38341e4778" />|
|:--:| 
| *Graph of magnetic field strength across coil centres* |




## 3D Simulations: 
|<img width="1613" height="1238" alt="sim3" src="https://github.com/user-attachments/assets/1ad5a047-61dc-413a-b529-c1c3289ea933" />|
|:--:| 
| *3D magetic simulation* |
Whilst I had a good amount of experience using 2D simulations, 3D simulations were something new for this project. Orignially, I wanted to use ANSYS Maxwell. However, the student license imposed a mesh limit, making it hard for me simulate the full motor. 

After some searching, I found that some of the university computers had a full license of ANSYS Workbench. It was older and had less features, it was sufficient for my use case.  

|<img width="1920" height="1200" alt="2mm rotor 3" src="https://github.com/user-attachments/assets/c8f1b037-d327-406b-a27f-d5210aed20a2" />|
|:--:|
|*3D magnetic simulation*|







## Learning more about FEA 
Whilst I was looking for a different software to use, I found an open source solver called Elmer. It was more complex and hard to use but it forced me to understand more about finite element simulaitions and how they work. 

|<img width="1031" height="861" alt="Screenshot 2025-05-28 123052" src="https://github.com/user-attachments/assets/69edb2bb-1c57-416d-980c-96242bfc202c" />|
|:--:|
| *Tutorial simulation made in Elmer* |



|<img width="396" height="558" alt="Screenshot 2025-05-30 205739" src="https://github.com/user-attachments/assets/a556fda7-e729-4f68-8af1-a6b799691c2a" />, <img width="525" height="553" alt="Screenshot 2025-05-30 205746" src="https://github.com/user-attachments/assets/d32e435e-ab37-4420-b46c-80c75e5ab22f" />|
|:--:|
|*Le image*|
