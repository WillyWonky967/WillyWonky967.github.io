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
The TelemhHost is a PCB that processes live telemetry data 

--- 
## High Frequency Routing 
During the process of high frequency routing, I had to pay close attention to maintaining a 100 ohm differential impedance between the ethernet traces to prevent EMI and signal reflection. To do this, I used the differential pair length tuning tool in Altium Designer to ensure the lengths of my signals were the same by tusing accordion and trombone patterns in my routing. 
{% include image-gallery.html images="Website_Telemhost3.png" 
height="400" %}

## CAN Bus Routing 
When routing the signals for the CAN Bus, 