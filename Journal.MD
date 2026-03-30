# LED sequencer effect

This is a simple LED circuit using Transitor-Transistor-Logic circuit and through this it will make an LED go up one by one. I'm building an astable circuit because of the fact that I want the LED to light up for a specific duration. I want it to act like the lights are bouncing like on FRC LED lights!

## March 27, 2026 - Researching astable circuits

Today I worked on using the template as a draft and experimenting with it. Initially I wanted it to be monostable but I don't think a fixed duration would achieve that effect when I read through the Resolution Hardware Document. Through my research I learned about astable circuits and they can change brightnesses on there own as long as it is powered. I found a schematic from ElecCircuit.com of astable circuit led sequence. I ended up successfullying replicating the schematic from the template.

I saw no difference for when all the resistors were at a value of 1k, but I think there was a slight change in timing when I changed it to 1.5k and because it slows more current down it, it meant the brightness is more immediate.

<img width="647" height="391" alt="Screenshot 2026-03-27 at 4 21 24 PM" src="https://github.com/user-attachments/assets/38ebf0e8-29cf-46f5-90fa-ce50d8f46906" />

The reason why I designed it this way was because there are transistors going to another capacitor, which stores energy. As the current flows, it goes to the transistor on the top left to the rest of the transitor and LED. I noticed they run parallel to each other. The way I built it was following a schematic I found online, and when I tested it the LEDs respectively turned on and off after a duration. I designed some of the resistor values in between resistors to be higher in order to slow down some of the current as to make the LED turn off, since it runs on current for the brightness. An issue I ran was something called max current, and solved it by adding another series of circult in parallel with a resistor to avoid the "path to ground with no resistance" problem.

![Astable circuit](https://github.com/user-attachments/assets/da1b5b6c-ec57-4646-8b20-736ea92bea02)

I ran into a problem where none of my LEDs were working so I did undo and reverted back to a state where it worked normally.

### Time Spent: 1.5 Hours

## March 28, 2026 - Last iterations PCB Fabrication!

For this I started to follow the tutorial located in the Resolution Hardware Week 2 document.
The following components I used includes: 3x 1.5k resistor, 4x 1k resistor, 3x LEDs, 3x 20uf capacitor, 3x NPN transitors. I ran into a problem researching these materials, and what if they're aren't as common? I found out that it is totally fine to have different resistor values more than 1k and 20uf capacitor values. While adding my components into KiCad, I asked myself, do I need a switch? I have not been able to incorprate this in earlier but astable circuits they run on their own. Sometimes I would like to control my power source by cutting it off. So decided to add a switch! I'm finally done with the design now and I'm happy with this. Time to get to work creating the PCB. When I tested with the switch everything got cut off and the circuit was running as usual, so nothing changed.

<img width="1005" height="560" alt="Screenshot 2026-03-28 at 7 34 51 PM" src="https://github.com/user-attachments/assets/c069d912-5d36-43f1-81f3-bf8ccfc92a04" />

I started to place the following components listed onto the schematic editor in KiCad. I noticed the ? and it indicates to write number next to it to make identifying the type of parts easier, especially if they are the same.

<img width="830" height="404" alt="Screenshot 2026-03-28 at 7 48 49 PM" src="https://github.com/user-attachments/assets/3d7c6fa2-c591-4d81-befd-c796401cdfb4" />

I also experienced a problem with the numbering for my resistors, especially since this is a weird parallel circuit I found online. I designed it to be in chronological order of where the power comes form the voltage source instead and trying to keep it consistent with LED and transistors.

<img width="874" height="480" alt="Screenshot 2026-03-28 at 8 01 39 PM" src="https://github.com/user-attachments/assets/8396a37d-f340-42b8-a4b0-2d2b7c350c20" />

I started to sketch out my schematic referencing my diagram. As for the resistor numbering, a schematic is usually read from left to right so I also based my order off of that.

<img width="1776" height="1128" alt="image" src="https://github.com/user-attachments/assets/d8e541d5-0156-42ad-9dc8-0ca7656089ff" />

I'm missing a voltage source, but the problem is... mine's two terminal! I decided to research the two-terminal voltage source by looking it up. According to a few forum posts, I've notice this symbol below. Now I just need to check out what it looks like by reseaching the data sheet if it help.

<img width="360" height="277" alt="Screenshot 2026-03-28 at 8 28 24 PM" src="https://github.com/user-attachments/assets/ca255ad9-a421-4682-8c09-438387207bf3" /><img width="393" height="275" alt="Screenshot 2026-03-28 at 8 34 25 PM" src="https://github.com/user-attachments/assets/d6110350-fbd7-4a71-ad34-4b9e2f6ca0be" />

Through a little bit of google search, VCC and GND are global. Voltage Source above usually is only for simulation and the battery indicates physical power. I want to use VCC and GND and I found out in the simulation that it stills work like normal as the two terminals previously when it tested it.

<img width="840" height="464" alt="Screenshot 2026-03-28 at 8 38 02 PM" src="https://github.com/user-attachments/assets/63469f74-12cf-42c3-ad03-0068a7800d15" />

Here is the VCC and GND in schematic editor. I believe they behave the exact same way and since VCC and GND are global, so I designed it this way.

<img width="850" height="525" alt="Screenshot 2026-03-28 at 8 42 19 PM" src="https://github.com/user-attachments/assets/bbbe41f9-ff18-4702-b967-3a4b9f40ad0d" />

Because the power and ground are important symbols, I have decided to rotate them so the voltage points up and the ground points down. I also added the values of my resistors and transitors with a voltage source connector. Though I'm not sure if it is supposed to be there by itself. After setting the values up, I assigned my footprints following the document guide. It seems the footprints don't really want exact values (eg. 1k ohm) and moreso of the measurements but I can also try finding it in the library through a drop-down in KiCad

<img width="1135" height="576" alt="Screenshot 2026-03-28 at 8 52 56 PM" src="https://github.com/user-attachments/assets/e8c70062-3503-47ea-bed8-44c86023a823" />

Now that I'm done with the schematic I will start translating it over to PCB editor mode and I updated my schematic. I managed to update the schematic onto the PCB editor, but I want to create a personalized shape, and I wonder what sort of cool thing I can make with an LED chaser with my creativity. I dug through some of my interests, and I remembered airplanes in the sky often having alternating flashing lights on the side and the tails. I think I'll create an airplane PCB outline in Figma and trace it.

### Time Spent: 2 Hours

## March 29, 2026 - Final iterations & moving on

For an airplane PCB online, I'm too late in the process to change. Well I can change, but this is great notes for next time! Only two LEDs alternate rapidly while the other is just on its own. Since my LEDs go up one by one, why not make a traffic light signal?

While I researched a new astable circuit where two can be on at the same time with one off, this was a painfully slow circuit. I ended up giving in to the simple one on the other off sequence instead. I changed the resistor values from 10k to 1k but nothing changed, though the capacitor from 47 to 10 did make the LED go out quicker and the others on. When I tested it out I had to wait a few seconds for the blinking to happen. The tutorial said 9v but I changed to 5v to slow the current down. I don't think I'll use this and just go with the previous one as the final.
<img width="5354" height="2229" alt="image" src="https://private-user-images.githubusercontent.com/271066488/571008211-7ee50bc1-c055-4b76-95f4-e5530ae1c10c.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NzQ4MjQ3OTUsIm5iZiI6MTc3NDgyNDQ5NSwicGF0aCI6Ii8yNzEwNjY0ODgvNTcxMDA4MjExLTdlZTUwYmMxLWMwNTUtNGI3Ni05NWY0LWU1NTMwYWUxYzEwYy5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwMzI5JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDMyOVQyMjQ4MTVaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02NjVmYzc5NDc4NWYyYWZiYjdhMWVhMjJkMWRmMzZlY2UzMTAxYmNiZjQ3ZGNlYTA0MTA4MDdlN2FlOTgyMGY4JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.w2OcSkh_b3m-63VtvAA5CsSNTZziRcnewN9tLyh9o8E" />

I thought the traffic light was a little simple and not personal to me, so I was thinking about what things would look cool with my current design, and I looked through my art gallery. I loved drawing dragons especially electric and fire dragons. So I was thinking of drawing a dragon breathing fire or charging electricity in its tail with LEDs there of course to show movement, as I was reminded of the pokemon legendaries Reshiram and Zekrom. Water based dragon creatures that have bioluminescent traits that glow on their body is cool too. I love airplanes and dragons. So I realized I could make a fighter jet design with the leds going on and off in a sequence for the jet engine! I think that's a great idea so I'll pursue one and this jet will be a single engine as I have three leds.

I started to sketch out the image in procreate and recreate an outline in Figma.

<img width="5354" height="2229" alt="image" src="https://github.com/user-attachments/assets/3e7a63cf-b0be-4fed-bc89-6a9d26338357" />

I attempted to import my SVG vector from Figma, but it turned out huge! I decided to search up how to solve this problem and I can't resize it in KiCad. Especially since it needs to be within 100mx100m. Luckily I was able to resize it by converting pixels to MM using Figma and it fits within the constraint. Now I have another issue, do my components fit?

<img width="1488" height="1040" alt="image" src="https://github.com/user-attachments/assets/a6d7aee0-9f0e-4e05-a786-ff2fde411538" />

I honestly don't think layout will work on this PCB, so I'll redo my PCB so the airplanes on the front. Aircraft are very elongated which can make it hard to fit components onto them in this shape. Well actually, it can work, I just have to remove the inner outlines within the shape.

<img width="1782" height="852" alt="image" src="https://github.com/user-attachments/assets/3fcb5ead-3c9b-45c8-8e6b-ffdff2c0ebc5" />

I persisted and it seems to work! I just need to adjust my traces as usual. Following the schematic, I aligned whatever resistors connected to the transistors be close to each other and the LEDs I'll figure out the tracers later.

<img width="1770" height="996" alt="image" src="https://github.com/user-attachments/assets/6399444b-4fe0-489a-8c6c-e8c89d4f4c26" /><img width="713" height="410" alt="Screenshot 2026-03-29 at 5 11 54 PM" src="https://github.com/user-attachments/assets/d0cd3c76-647f-4e98-84b8-66ead270c124" />

### Time Spent: 3 Hours
