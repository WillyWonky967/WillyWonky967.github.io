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

## Analog Filter Design (Anti Aliasing Filters)
When data is received from sensors which sample and collect data at specific frequencies, a problem that often occurs is aliasing, which occurs when the data is undersampled. To find the cutoff frequency of the anti-aliasing filters, I calculated the sensor bandwidth by dividing 1 by the response time of the sensors. 