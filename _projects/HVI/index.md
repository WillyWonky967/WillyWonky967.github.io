---
layout: post
title: HVI -- PCB For Processing High Voltage Controlled Signals 
description: Created circuitry responsible for controlling a mission critical safety indicator check for the UC Davis FSAE car on the HVI, a PCB that houses the circuitry responsible for processing safety indicators and features that are controlled or triggered by high voltage interrupts. Rerouted the low voltage circuitry on the PCB to accomodate for the added electronics. 
skills: 
  - Differential Routing 
  - CAN Communication 
  - Altium PCB Layout 
  - Analog Filter Design 

main-image: /Website_HVI1.png 
--- 

## HVI Circuit Topology 
{% include image-gallery.html images="Website_HVI1.png" height="500" %}
This is the 3D view of the HVI PCB. 
--- 
{% include image-gallery.html images="Website_HVI4.png" height="500" %}
This is the 2d view of the low voltage side of the HVI PCB, which I rerouted after making my updates to the PCB schematic. 

# Lampcheck Circuit - What is it? 
In the FSAE EV competition, the lampcheck rule was recently added for the 2027 EV cmpetition which states that the *red and green indicator lights* located on the top of the driver's seat have to turn on for several seconds, before returning to normal operation in order to demonstrate the functionality of the status lights. These status lights are mission critical, as they are indicators of whether or not the vehicle is safe to drive, and thus the lampcheck is a **mission critical** piece of hardware for the vehicle, to ensure safety and to get the car validated during comp. 
---
## Lampcheck Circuit in Detail 
The lampcheck circuit consists of a *timer that enables a signal that overrides the normal function of the red and green light by forcing them to turn on for 2-3 seconds upon vehicle startup,* *timers and transistor logic which control the blinking of the lights,* as well as *transistor logic to select between the override state and the lights' normal function.*
---

### Override Signal Timer 
{% include image-gallery.html images="Website_HVI2.png" height="500" %}
This is an image of the circuit schematic for the override signal timer, controlled by an **active low 555 timer.** The 555 timer is configured in monostable operation, which acts as a one shot timer when it receives a trigger signal, which is *triggered by the 12V input upon startup.* In the trigger signal line, there is a *capacitor connected to ground which pulls the trigger voltage low for a split second* before becoming fully charged and stopping the voltage pulldown, which guarantees a **one shot timer output,** where the timer outputs a 2-3 second long signal once. The **reset signal is controlled by the 12V line,** which means that the reset line can never be pulled low as the timer is active low, thus **maintaining the one shot output** functionality of the timer. 
---

### Transistors to Switch Between Light States 
{% include image-gallery.html images="Website_HVI2.png" height="700" %}
This is an image of the circuit schematic for the *555 timer which controls the blinking of the red light,* the *transistors whose logic determines the normal operation of the green and red light,* and the *transistors whose logic determines whether or not the green and red light will be forcibly turned on by the override signal or operate as normal.* 
---
During normal operation, the **transistors in the top left will short the green_gnd connection to ground,** as the fault lines are **active low,** meaning that they are high when there are no faults. This means that whenever there is a 12V signal from the car entering startup, a ground connection will be created for the green light, and it will turn on. However, upon a fault, the **fault states will go low, creating a 12V signal to green_gnd, making the red light blink.** 