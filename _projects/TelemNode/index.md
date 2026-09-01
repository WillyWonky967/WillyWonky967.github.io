---
layout: post
title: TelemNode - PCB For Sensor Data Acquisition and Telemetry 
description: Created a PCB that records analog sensor data recording physical measurements such as temperature, speed, or angles of components around an FSAE car into an MCU before trasmitting the digitized data via CAN from the MCU. I calculated the cutoff frequencies for anti-aliasing filters for the sensor inputs into MCU in order to prevent aliasing and preserve signal integrity. 
skills: 
  - Differential Routing 
  - CAN Communication 
  - Altium PCB Layout 
  - Analog Filter Design 

main-image: /Website_Telemnode2.png
--- 

--- 

### TelemNode Images
This is the 2D view of the TelemNode PCB
{% include image-gallery.html images="Website_Telemnode1.png" height="500" %}
--- 
This is the top view of the TelemNode PCB
{% include image-gallery.html images="Website_Telemnode2.png" height="500" %}
---
This is the bottom view of the TelemNode PCB 
{% include image-gallery.html images="Website_Telemnode3.png" height="500" %}

---

## Analog Filter Design (Anti Aliasing Filters)
When data is received from sensors which sample and collect data at specific frequencies, a problem that often occurs is aliasing, which occurs when the data is undersampled. Aliasing is a problem for the team's live telemetry tracking, because aliasing results in high frequencies above the Nyquist frequency masquerading as normal low frequencies, resulting in distorted data. The Nyquist frequency was obtained by dividing 1 by the response time multiplied by the percentage of the total signal received in the response time window, and I used a low pass RC filter to obtain the Nyquist frequency. However, there were still multiple considerations I had to make when designing my filters. 

---

## Square Wave Filter Design 
In Hall Effect sensors, the device switches rapidly switches on and off as magnetic poles move past the sensor, which produces a kind of square wave. However, the Nyquist frequency found using the methods above is not suitable for these square waves, as the cutoff frequency fitlers out all frequencies above the first harmonic of a sinusoidal wave. This is detrimental to the signal integrity of square waves produced by Hall Effect sensors, because square waves are composed of multiple odd numbered harmonics, which are odd multiples of the fundamental frequency. By getting rid of the odd harmonics which shape the square wave, the shape of the square wave ends up becoming distorted. 

{% include image-gallery.html images="SquareWaveHarmonics.jpg" height="500" %}
This is a picture of how odd harmonics form square waves, with frequencies up to the third harmonic are needed to maintain the overall shape fo the wave. As a result of this, I chose to use the third harmonic as the cutoff frequency of the filter, to maintain the shape of the square wave. By doing this, I was able to maintain signal integrity for the square waves from the Hall Effect sensors. 

---

# PCB Design Strategies 
## Heirarichal Design 
In my strategy for desinging the PCB, I used heirarcichal design to my advantage, by creating a child class for the strain gauge amplifiers, which was replicated throughout the design to amplify the outputs of all the strain gauges in my project. By using child classes, I was able to save time and space with the design of the schematic 

{% include image-gallery.html images="Website_Telemnode4.png" height="500" %}
This is an image of the top layer heirarchy showing how all strain gauge amplifiers are child circuits of the same parent circuit 

{% include image-gallery.html images="Website_Telemnode6.png" height="500" %}
This is the circuit topology of the parent strain gauge amplifier circuit 

## Rooms
When it came to laying out the PCB, I used a room in order to capture the layout of the strain gauge amplifier circuit configuration, and I copied the layout throughout the PCB, in order to save time on routing by replicating the same circuit that was constantly repeated. 

{% include image-gallery.html images="Website_Telemnode5.png" height="500" %}
This is an image of all the duplicates of the strain gauge amplifier room laid out on the circuit, where every clone of the room has the same identical layout. 