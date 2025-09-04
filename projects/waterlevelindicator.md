---
layout: project
type: project
image: img/s-l1200.jpg
title: "Water Level Indicator"
date: 2025
published: true
labels:
  - Software
  - Hardware
  - Raspberry Pi
summary: "Created at a Leeward Community College hackathon, this project aims to improve the user experience of a water dispensing machine. "
---

<div class="text-center p-4">
  <img width="200px" src="../img/Screenshot 2025-09-03 165311.png" class="img-thumbnail" >
  <img width="200px" src="../img/Screenshot 2025-09-03 165347.png" class="img-thumbnail" >
</div>

The Water Level Indicator project was a proof-of-concept submission for a hackathon during my Spring 2025 semester at Leeward Community College. During the initial drafting stages, I was voted in as the lead programmer because I had the most coding experience on the team. The goal of the project was to improve the user experience of a water dispensing machine by providing a clear, visual indication of the water level. 

Of course, installing such a device was outside the scope of the 1-week timeframe, so it was decided that it would be submitted as a proof-of-concept instead of a prototype. To demonstrate the validity of our project, we configured the water sensor to detect when the water level fell below a threshold of 0.036 inches. Once this event occurs, the LEDs in the computer motherboard automatically turn on, signaling the user to refill the container. This LED system was designed to prevent both underfilling and overfilling by clearly alerting the user when the water level is low.

Here is the code showing how the water sensor operated:

```cpp
import time
import explorerhat 
lowWaterThreshold = 0.036

while True:
  waterLevel = explorerhat.analog.one.read()
  if waterLevel > lowWaterThreshold :
    explorerhat.light.off()
  else :
    explorerhat.light.on()
  time.sleep(1)

```
