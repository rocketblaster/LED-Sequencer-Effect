# LED Sequencer Effect

This is an LED sequencer circuit shaped airplane with LEDs lighting up the fiery engines. Running on 5 volts, it is made with 3x LEDs, transistors and resistors of different levels. It works by lighting up one LED at a time to represent the heat from the engine going up one by one! Tried to get an effect of moving fire but this is closest I managed to get.

<img width="1420" height="738" alt="image" src="https://github.com/user-attachments/assets/63eff19f-a41e-42a5-9c90-19bdd4ec214a" />
<img width="1486" height="728" alt="image" src="https://github.com/user-attachments/assets/61e7602f-e226-4b82-8332-35da4023d565" />

---

## Simulation

The circuit works as an astable multivibrator, meaning after a specific duration the led goes into an active and non active state temporarily. There is a switch in place if I don't want power to the LEDs while connected to power. How it works is it in parallel and one of the LEDs lights up then goes off. Because the capacitor stores energy and the transistors have a base starting from capacitor and LED it moves from one LED to the next so that the current can turn it on.

![Astable circuit 2](https://github.com/user-attachments/assets/948a35b9-43e0-4f03-bb8b-4baeda40c8f2)

[Link to Demo](https://is.gd/a9qMvy)

---
## Schematic

<img width="1730" height="946" alt="image" src="https://github.com/user-attachments/assets/919c12be-5fc2-4148-aceb-cb86671ed266" />


## PCB

<img width="1938" height="864" alt="image" src="https://github.com/user-attachments/assets/0bb3449b-d898-4771-acbf-792ce4075eea" />

---

This was super paintstaking to make but I pushed through anyways yay!
