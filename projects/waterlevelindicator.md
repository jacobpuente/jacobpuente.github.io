---
layout: project
type: project
image: img/12467b9de78f16b492a0205cb1a538782106664a.jpg
title: "Water Level Indicator"
date: 2025
published: true
labels:
  - Software
  - Hardware
  - Raspberry Pi
summary: "Created at a Leeward Community College hackathon, this project uses sensors and LED lights to signal low water levels in a dispensing machine for timely refills."
---

<div class="text-center p-4">
  <img width="200px" src="../img/micromouse/micromouse-robot.png" class="img-thumbnail" >
  <img width="200px" src="../img/Screenshot 2025-09-03 165311.png" class="img-thumbnail" >
  <img width="200px" src="../img/Screenshot 2025-09-03 165347.png" class="img-thumbnail" >
</div>

This proof of concept project was developed during a hackathon at Leeward Community College, where I served as the lead programmer. The goal was to improve the user experience of a water dispensing machine by providing a clear, visual indication of the water level. We achieved this by integrating a water level sensor and LED lights into the water container. When the water level falls below a set threshold (0.036 inches), the LEDs automatically turn on, signaling the user to refill the container. Once the water level rises above the threshold, the LEDs turn off. This system prevents both underfilling and overfilling, making the process more efficient and intuitive for users. The setup is simple, effective, and easy to implement.

Here is the code that shows how we read values from the water sensor:

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
