---
layout: post
title: TelemNode - PCB For Sensor Data Acquisition and Telemetry 
description: Created a PCB that records analog sensor data recording physical measurements such as temperature, speed, or angles of components around an FSAE car into an MCU before trasmitting the digitized data via CAN from the MCU. I calculated the cutoff frequencies for anti-aliasing filters for the sensor inputs into MCU in order to prevent aliasing and preserve signal integrity. 
skills: 
  - Differential Routing 
  - CAN Communication 
  - Altium PCB Layout 
  - Analog Filter Design 

main-image: /project2.jpg
---

# Analog Filter Design (Anti Aliasing Filters)
When data is received from sensors which sample and collect data at specific frequencies, a problem that often occurs is aliasing, which occurs when the data is undersampled. Aliasing is a problem for the team's live telemetry tracking, because aliasing results in high frequencies above the Nyquist frequency masquerading as normal low frequencies, resulting in distorted data. The Nyquist frequency was obtained by dividing 1 by the response time multiplied by the percentage of the total signal received in the response time window, and I used a low pass RC filter to obtain the Nyquist frequency. However, there were still multiple considerations I had to make when designing my filters. 

## Square Wave Filter Design 
In Hall Effect sensors, the device switches rapidly switches on and off as magnetic poles move past the sensor, which produces a kind of square wave. However, the Nyquist frequency found using the methods above is not suitable for these square waves, as the cutoff frequency fitlers out all frequencies above the first harmonic of a sinusoidal wave. This is detrimental to the signal integrity of square waves produced by Hall Effect sensors, because square waves are composed of multiple odd numbered harmonics, which are odd multiples of the fundamental frequency. By getting rid of the odd harmonics which shape the square wave, the shape of the square wave ends up becoming distorted. 
{% include image-gallery.html images="SquareWaveHarmonics.jpg" height="500" %}
This is a picture of how odd harmonics form square waves, with frequencies up to the third harmonic are needed to maintain the overall shape fo the wave. As a result of this, I chose to use the third harmonic as the cutoff frequency of the filter, to maintain the shape of the square wave. 