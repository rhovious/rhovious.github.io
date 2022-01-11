+++
author = "Robert Hovious"

title = "Servo Testing/Control Board"
description = "Servo Positional Control Using Pot and Display"
link = "https://github.com/rhovious/servoTester"
tags = [
    "servo",
    "arduino",
    "c",
]# 
categories = [
    "projects",
    
]

date = 2022-01-09
weight = 5
draft = false
type = "projects"

+++

[View Code on Github]({{< param link >}} {{< param title >}})

Building a simple board that will allow moving of a 180* servo via a potentometer and 1306 screen.

## About
This project serves the purpose of building a small servo control device. This device allows connection of a standard 180* rotation servo. The angle of the servois adjusted using the potentometer. The active angle of the servo is displayed on the connected screen

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


```c++


// Include the servo library:
#include <Servo.h>
// Create a new servo object:
Servo myservo;
// Define the servo pin:
#define servoPin 9
// Create a variable to store the servo position:
int angle = 0;
void setup() {
  // Attach the Servo variable to a pin:
  myservo.attach(servoPin);
}
void loop() {
  // Tell the servo to go to a particular angle:
  myservo.write(90);
  delay(1000);
  myservo.write(180);
  delay(1000);
  myservo.write(0);
  delay(1000);
  // Sweep from 0 to 180 degrees:
  for (angle = 0; angle <= 180; angle += 1) {
    myservo.write(angle);
    delay(15);
  }
  // And back from 180 to 0 degrees:
  for (angle = 180; angle >= 0; angle -= 1) {
    myservo.write(angle);
    delay(30);
  }
  delay(1000);
}
```