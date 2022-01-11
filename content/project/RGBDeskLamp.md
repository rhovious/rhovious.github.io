+++
author =  "Robert Hovious"

title =  "Desktop RGB Lamp"
description =  "Potentometer RGB controlled desk lamp using neopixels"
link =  "https://rhovious.github.io/project2/"
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

# Desktop RGB Lamp
## Building a simple project that will allow moving of a 180* servo via a potentometer and 1306 screen.

## About
This project 

### Hardware Required
* Arduino Board
  * Any arduino should work, using a Nano clone
* Servo Motor
* 0.96 OLED
  * Used to show the current servo arm angle. Can be ommited and monitored using the serial monitor. I used an 0.96 SSD1306 display 64x128.
* 10k Potentometer
  * Used for adjusting the angle of the servo
* hook-up wires

### Circuit

   Pin | Description
--------|------
    25 | SDA --> OLED
    26 | SCL --> OLED
    A0 | Potentometer --> OLED
    9  |   Servo Pin

## Assembly
* INSERT PIC OF BOARD WITHOUT MODULES IN IT
* *OTHER PICS


### Potentometer Circuit
Wire the potentiometer so that its two outer pins are connected to power (+5V) and ground, and its middle pin is connected to A0 on the board.

### Display Circuit
Wire the display as required. It should have a connection to power (+5v) and ground. The other 2 pins should ne connected to SDA / SCL on the Nano.

### Servo Circuit
Connection to the servo should go through your input pins directly to allow for a higher voltage. Connect servo power (+xxv) and ground to input power supply. The other pin should be connected to your servo control pin on the board 

## Programming

### Knob Circuit
The potentometer is simple mapping the value of the potentometer (0-1024) to an angle measuremeant (0-180)
