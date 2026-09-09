---
layout: post
title: Wiring Harness - Design and implementation 
description: Designed a full automative wiring harness for a car's low and high voltage system by mapping wiring connections across the car, creating a wiring diagram for the team to use during assembly via RapidHarness, and designed methods to assemble the wiring harness as efficiently as possible. Through these methods, the team was able to get the wiring harness assembled over two months ahead of schedule. 
skills: 
  - Wiring Harness Design 
  - RapidHarness 
  - Excel 
  - Design Optimization 

main-image: /Website_WiringHarness1.png
--- 

--- 

### Wiring Harness Schematic 
{% include image-gallery.html images="Website_WiringHarness1.png" height="2000" %}
This is a picture of the wiring schematic I created using RapidHarness for the overall wiring harness. 
<br>

When designing the schematic, the first thing that I considered was the location of the main electrical connections throughout the car, such as where the main PCBs were as well as things like the fusebox, hv and lv batteries, global ground point and all the components in the shutdown circuit. I placed the locations of these ciomponents in the wiring diagram to approximately where they are approximately in the car, so as to make the diagram easier to read and follow along. 
<br>

---

## Node Points 
{% include image-gallery.html images="Website_WiringHarness2.jpg" height="500" %} 
This is a diagram indicating the positioning of the nodes points I have placed on the car. 
<br>

The locations of the node points were determined by the locations of important electrical connections on the car, such as PCBs with many electrical conenctions coming out of them or sensors. By placing their approximate locations on the chassis of the car, we were able to label them as node points, which were used in mounting wires and measuring the lengths of connections. 
<br> 

After placing down and labeling the node points, I measured the lengths between the node points, which were used to calculate the lengths of wire for the electrical connections of the car. The measurements were highly accurate, with several inches given for slack. As a result of this, we had a very clean wiring harness on the car, with images of the finished wiring harness found below. 

---

# Images of the Wiring Harness In Construction  
{% include image-gallery.html images="Website_WiringHarness8.jpg" height="500" %} 
This is a image of the wiring harness being constructed on the ground before being attached to the car. When aseembling the harness, we chose to assemble the connections on the ground first using an outline of the node point lengths on the actual car, before mounting the assembled harness in the end. Through this, we were able to work on the wiring harness before the chassis was done being assembled, and this helped us meet our assembly deadline two months in advance. 
---

# Images of the Wiring Harness on the Car 
{% include image-gallery.html images="Website_WiringHarness4.jpg" height="500" %} 
This is an imgage of part of the HVI, or the interface between the HV and LV system on the car during the Michigan 2026 Competition. The wires connecting the status LEDs on the top of the car are shown disconnected in this image, as the team was busy working on reassembling the system after a system failure. 
---
{% include image-gallery.html images="Website_WiringHarness5.jpg" height="500" %} 
This is a shot of the HV wiring in the wiring harness showing connections between the inverter and the tractive battery, as well as some of the wiring for the shock angles and the brakelight. The picture was taken at the Michigan 2026 Competition. 
---
{% include image-gallery.html images="Website_WiringHarness6.jpg" height="500" %} 
This is a shot of the wiring harness from the side view of the car, showing parts of the HV wiring and the status LED wiring. This image shows the physical geometry of the wiring harness mounted on the car. 
---
{% include image-gallery.html images="Website_WiringHarness7.jpg" height="500" %} 
This is a shot fo the vehicle control unit wiring located beneath the dashboard, as well as the brake and accelerator pedal wiring. 
---

## Wiring Table 
{% include image-gallery.html images="Website_WiringHarness3.png" height="500" %} 
This is an example from part of the wiring table for the car, with the subject in this image being taken from the connection table for the front half of the car. 
---

## Harness Justification
By using my plans for the wiring harness, we were able to complete the assembly of the wiring harness two months in advance, whcih allocated us more time for debugging the harness and for working on setting up more things around the car. 
---

