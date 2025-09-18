# CAD and Mechanical Design
|<img width="514" height="574" alt="CAD 1" src="https://github.com/user-attachments/assets/d0c01be2-f2b6-4861-bc28-d8f757b87049" />| <img width="500" height="580" alt="CAD 1" src="https://github.com/user-attachments/assets/2f04a9e5-76f3-4283-bf5e-74961976495e" />|
|:--:| :--: |
| *CAD model of final design* | *The three versions of the mechanical design* |

I had two goals for the mechanical design of the motor:
* Make the shaft spin well
* Make it easy to assemble

I made the CAD models in Fusion 360. I used an iterative design approach, where I would 3D print parts and see how they perform. After 3 versions, I landed on a design I was happy. 

## Shaft and rotor design
The biggest challange I faced was deciding how to attach the rotors to the shaft. I went throught many different versions, and eventually landed on a more modular design. 

|<img width="600" height="400" alt="shaft with hubs" src="https://github.com/user-attachments/assets/eae5e976-12c9-42f6-a7a5-4ebd416667cc" />| <img width="400" height="400" alt="Rotor and rotor hub" src="https://github.com/user-attachments/assets/37f7fda3-d39d-4497-b98d-1492962151ba" /> |
|:--:| :--:|
|*Shaft and rotor hubs*| *Rotor and Rotor hubs*|

The main reason I went for this design is that it lets me change the rotor hub design without needing to completely remake the rotor. Magnets are expensive, and I didn't want to glue the magnets to the rotor only to realize it doesnt fit on the shaft correctly. The hubs screw onto the shaft, and the rotor screws onto the plate. Whilst I was initially happy with the design, there were a couple flaws that became apparent whilst I was assembling the motor for the first time...

## The motor imploded (whoops)
Whilst 3D-printing the shaft was great for speed, it is **not** strong enough to keep thirty-two N52 magnets from being apart. This was also in part due to my rotor-and-rotor-hub design; when I tried to put on the second rotor, I didnt put it on fully straight, causing a massive imbalance and putting a big bending force on the shaft, which promtly broke in half. 

| ![IMG_4185](https://github.com/user-attachments/assets/dc50d471-a6bf-4258-b4e1-74474d972084) |![IMG_4187](https://github.com/user-attachments/assets/d4871822-5866-49b4-a867-4ace2eb54988) |
|:--:| :--:|
|*The two rotors a bit closer than I would like them to be...*| *not my proudest moment*|

The magnets were unharmed and could be salvaged, but it was painfully clear that I need to redesign how I attach the rotors on the shaft. I was too focused on making it easy to assemble that I didn't consider that it needs to be strong enough. The first thing to do is make the shaft out of a stronger material like steel, and to make the rotor a single peice. I'm actively working on this currently, and Ill update the page once I've made something that works well. 

For testing purposes, I rebuilt the current design with only one rotor to eliminate any internal forces. 
