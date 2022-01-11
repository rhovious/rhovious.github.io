+++
author =  "Robert Hovious"

title =  "Desktop RGB Lamp"
description =  "Potentometer RGB controlled desk lamp using neopixels"
link =  "https://github.com/rhovious/RGBDeskLamp"
tags =  [
    "servo",
    "arduino",
    "c",
]# 
categories =  [
    "projects",
    
]

date =  2021-12-25
weight =  5
draft =  true
type =  "projects"

+++

[View Code on Github]({{< param link >}} {{< param title >}})

# Desktop RGB Lamp
## Modification of a retro desk lamp to be run from Neopixels. 

## About
Modification of a retro desk lamp to be run from Neopixels. 

### Hardware Required
* Arduino Board
  * Any arduino should work, using a Nano clone
* (3) 10k Potentometer
  * Used for adjusting R, G, and B values of the Neopixels.
* hook-up wires

### Circuit

   Pin | Description
--------|------
    A0 | Potentometer --> RED
    A0 | Potentometer --> GREEN
    A0 | Potentometer --> BLUE
    A0 | Neopixel Data Pin

## Assembly
* INSERT PIC OF BOARD WITHOUT MODULES IN IT
* *OTHER PICS

### Servo Circuit
Connection to the servo should go through your input pins directly to allow for a higher voltage. Connect servo power (+xxv) and ground to input power supply. The other pin should be connected to your servo control pin on the board 

## Programming

### Knob Circuit
The potentometer is simple mapping the value of the potentometer (0-1024) to an angle measuremeant (0-180)
