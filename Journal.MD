# LED sequencer effect

This is a simple LED circuit using Transitor-Transistor-Logic circuit and through this it will make an LED go up one by one. I'm building an astable circuit because of the fact that I want the LED to light up for a specific duration. I want it to act like the lights are bouncing like on FRC LED lights!

## March 27, 2026 - Researching astable circuits

Today I worked on using the template as a draft and experimenting with it. Initially I wanted it to be monostable but I don't think a fixed duration would achieve that effect when I read through the Resolution Hardware Document. Through my research I learned about astable circuits and they can change brightnesses on there own as long as it is powered. I found a schematic from ElecCircuit.com of astable circuit led sequence. I ended up successfullying replicating the schematic from the template.

<img width="647" height="391" alt="Screenshot 2026-03-27 at 4 21 24 PM" src="https://github.com/user-attachments/assets/38ebf0e8-29cf-46f5-90fa-ce50d8f46906" />

The reason why I designed it this way was because there are transistors going to another capacitor, which stores energy. As the current flows, it goes to the transistor on the top left to the rest of the transitor and LED. I noticed they run parallel to each other. The way I built it was following a schematic I found online, and when I tested it the LEDs respectively turned on and off after a duration. I designed some of the resistor in between resistors to slow down some of the current as to make the LED turn off, since it runs on current for the brightness An issue I ran was something called max current, and solved it by adding another series of circult in parallel with a resistor to avoid the "path to ground with no resistance" problem.

I ran into a problem where none of my LEDs were working so I did undo and reverted back to a state where it worked normally.

### Time Spent: 1.5 Hours

## Date - [Heading]

How did I fix this issue?

![image](image.png)

### Time Spent: X Hours
