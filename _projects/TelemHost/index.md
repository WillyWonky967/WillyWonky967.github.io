--- 
layout: post 
title: TelemHost - Ethernet PCB for Data Acquisition 
description: Improved the routing for the ethernet electronics traces by ensuring all ethernet traces were impedance matched using Altium's differential routing tools. Ensured impedance matched high speed ethernet traces were properly referenced to ground, and CAN bus routing was routed properly. 
skills: 
    - High Frequency Routing 

    - Impedance matching 
    - PCB Routing 
    - Altium Designer 
main-image: 

 ---
## High Fequency Routing 
description: When performing high frequency routing, the main things I had to worry about in regards to preserving signal integrity and termination were impedance matching and referencing. Using the built in impedance matching tools in Altium Designer, I was able to impedance match the traces by ensuring that the differential pairs between ETH_Tx and ETH_Rx had to be matched in trace length, as well as having 100Ω differential impedance. 

### Ethernet Routing Gallery
description: Here are images of the traces for ETH_Tx and ETH_Rx. 
--- 


---
