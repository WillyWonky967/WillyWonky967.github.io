---
layout: post
title: Cooling Testing Rig Setup 
description: Configured and set up the electronics needed to test out a replica of the water cooled cooling loop on my team's FSAE car, meant for collecting pressure, temperature, and water flow data for the cooling subteam to use. I designed the electrical configurations for the water temperature and pressure sensors, programmed an STM32 to run the water pumps and fans within the cooling loop with programmable speeds, as well as programming an Arduino to save data to an SD card whcih I formatted. 
skills: 
  - Electronics Design 
  - C Programming 
  - STM32 Programming
  - Arduino Programming 
  - SD Card Formatting 

main-image: /Website_CoolingRig1.png
--- 

## Cooling Testing Rig Images 
{% include image-gallery.html images="Website_CoolingRig1.png" height="500" %}
This is the overall image of what the cooling loop looks like, with the its fans, pumps, heater, water collection system, sensors, tubing, and electronics. 
--- 
{% include image-gallery.html images="Website_CoolingRig2.png" height="500" %}
A closer up look at some of the electronics, notably the arduino and the attached SD card reader meant for data collection and a breadboard for the electronic circuits for the temperature and pressure sensors. 
--- 

## Cooling Testing Rig Arduino Configuration 
In order for the arduino to save data, I not only had to write firmware to program the arduino to save data to an SD card via SPI and an external SD card reader, but I also had to configure the circuit and format the SD card correctly. 
---
When configuring the SD card, I had to use an external SD card formatter to reformat it to Fat32, because the SD card was 32GB, and the SD card reader wasn't able to read or write data to the SD card in its original format. 
--- 

## Cooling Testing Rig Data Collection Results 
From our implementation of the SD card to log data from the pressure sensors and thermistor circuits we configured, the cooling subteam on the UC Davis FSAE team were able to gain valuable pressure and thermal readings. Through the data gained from the test rig, the cooling subteam was able to properly model the thermal and pressure characteristics of the real cooling loop on the car, and were thus able to mark down potential changes to future cooling loop designs. 