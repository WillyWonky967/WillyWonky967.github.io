--- 
layout: post 
title: TelemHost - Ethernet PCB for Data Acquisition 
description: Improved the routing for the ethernet electronics traces by ensuring all ethernet traces were impedance matched using Altium's differential routing tools. Ensured impedance matched high speed ethernet traces were properly referenced to ground, and CAN bus routing was routed properly. 
skills: 
    - High Frequency Routing
    - Impedance matching 
    - PCB Routing 
    - Altium Designer 
main-image:  /Website_Telemhost1.png 

--- 

--- 
### PCB Topology of TelemHost (Top view)
{% include image-gallery.html images="Website_Telemhost1.png" 
height="400" %}
This is an imgage of the topology of the TelemHost PCB as seen from the top view 

### PCB Topology of TelemHost (Rear View)
{% include image-gallery.html images="Website_Telemhost2.png" 
height="400" %}
This is an image of the topology of the TelemHost PCB as seen from the bottom view 

--- 
# What Exactly Does the TelemHost Do? 
The TelemHost is a PCB that processes live telemetry data from external sensors throughout the car via the CAN bus, and it transfers live data via an ethernet router off the PCB while storing backup data on an SD card mounted on the PCB. In addition, the PCB collects real time position and acceleration data via a specialized sensor called Xsens, which communicates with the microcontroller via UART. 

The TelemHost has an ethernet PHY transceiver and an RJ45 connector to receive and transceive data, along with an ethernet transformer between the connector and the PHY to provide galvanic isolation, match impedances, and to balance signal voltages. The ethernet PHY recieves its clock signals from the MCU to have a transfer speed of 100Mbps. 
--- 

## Ethernet Circuitry Overview
{% include image-gallery.html images="Website_Telemhost4.png" 
height="400" %}
---

## High Frequency Routing 
During the process of high frequency routing, I had to pay close attention to maintaining a 100 ohm differential impedance between the ethernet traces to prevent EMI and signal reflection. To do this, I used the differential pair length tuning tool in Altium Designer to ensure the lengths of my signals were the same by tusing accordion and trombone patterns in my routing. 
---
{% include image-gallery.html images="Website_Telemhost3.png" 
height="400" %}
This is an example of some of the high frequency routing for the Ethernet Rx and Tx signals on the bottom layer of the PCB. Note the tromboning and length matching techniques used on the PCB. 
--- 


## CAN Bus Routing 
When routing the CAN bus, I had to add two CAN transcievers for converting differentially routed signals from the external CAN bus to digital data values that get routed to the MCU. There are two different transceivers due to accomodate for two different CAN lines used on teh carm with one being TCAN or the bus lines we use for overall data coillection, and ECAN, which is ised to handle framing, mailboxes, and error checking in the main MCU. 
---
{% include image-gallery.html images="Website_Telemhost5.png" 
height="400" %}
This is an image of the CAN transcievers on the schematic sheet 
--- 
{% include image-gallery.html images="Website_Telemhost6.png" 
height="400" %}
Image of the routing for the TCAN transceiver, showing differential signals being converted into digital signals for the MCU 