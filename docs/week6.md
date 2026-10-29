---
title: Week 6
nav_order: 8
nav_exclude: false
description: >-
    Week 6 activities
---

# Week 6 - Microcontroller programming
{:.no_toc}

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---
## Readings & Preparation

This week’s readings center on programming using Arduino.


### Tutorials / Readings

We recommend going through the tutorials in the order given.

1. [Arduino Overview (video)](https://www.youtube.com/watch?v=tiGw9PQbvrg). Quick, high level overview of what the Arduino is, what it's used for, and key concepts like setting voltages on digital pins with, using PWM, ADC on the analog input pins, as well as key elements code examples in the Arduino IDE. [9 minutes].

1. The following are key documentations from the official Arduino Docs website for understanding programming in the Arduino IDE. 
    1. [Arduino API.](https://docs.arduino.cc/learn/programming/reference/?_gl=1*19suhw0*_up*MQ..*_ga*NDg4NTI2OTQ5LjE3OTMyNDMxMTU.*_ga_NEXN8H46L5*czE3OTMyNDMxMTMkbzEkZzEkdDE3OTMyNDMyMjMkajM4JGwwJGg4MDg1MTIwMDM.) See the following key functions, and pay attention to the examples that use them in the tutorials to come; these enable most of the functionality we are interested in:
        1. **Digital I/O:** digitalRead, digitalWrite, pinMode
        1. **Analog I/O:** analogRead, analogWrite
        1. **Time:** delay, millis
        1. **Serial:** print, println
        1. **Data types:** int, println
        1. **Sketch:** void setup, void loop
        1. **Control Structure:** if, else, for, while   
        1. **Further Syntax:** block comment, single line comment, semicolon 
        1. **Arithmetic Operators:** all
        1. **Comparison Operators:** all
        1. **Boolean Operators:** all
    1. [Arduino Sketches.](https://docs.arduino.cc/learn/programming/sketches/?_gl=1*s4uz6u*_up*MQ..*_ga*NDg4NTI2OTQ5LjE3OTMyNDMxMTU.*_ga_NEXN8H46L5*czE3OTMyNDMxMTMkbzEkZzEkdDE3OTMyNDQwODUkajI4JGwwJGg4MDg1MTIwMDM.) Anatomy of an Arduino Sketch; setup & loop, variables, functions, as well as quick overview of pinMode, digitalWrite, and delay.
    1. [Arduino Variables.](https://docs.arduino.cc/learn/programming/variables/?_gl=1*1ui3kus*_up*MQ..*_ga*NDg4NTI2OTQ5LjE3OTMyNDMxMTU.*_ga_NEXN8H46L5*czE3OTMyNDMxMTMkbzEkZzEkdDE3OTMyNDQyODMkajU4JGwwJGg4MDg1MTIwMDM.) Using variables in the Arduino IDE, examples using int and writing to a pin. 
    1. [Arduino Functions.](https://docs.arduino.cc/learn/programming/functions/?_gl=1*o967ps*_up*MQ..*_ga*NDg4NTI2OTQ5LjE3OTMyNDMxMTU.*_ga_NEXN8H46L5*czE3OTMyNDMxMTMkbzEkZzEkdDE3OTMyNDQyODYkajU1JGwwJGg4MDg1MTIwMDM.) Writing functions in the Arduino IDE, examples using multiplication and for loops. 


1. [Arduino In-depth Starter Tutorial (video)](https://www.youtube.com/watch?v=BLrHTHUjPuw). An in-depth look at both the arduino hardware (expounding on the previous overview), and programming in the Arduino IDE. Covers code structure, variables, pinMode, conditionals (if statements), serial monitor, analogWrite, analogWrite, digitalRead, digitalWrite, delay, arduino library [85 minutes].



1. [Install Arduino IDE](https://makeabilitylab.github.io/physcomp/arduino/arduino-ide.html).
Download and Install the Arduino IDE on your laptop. See Step 1 for installation and Step 2 to open the IDE to confirm proper installation. 
1. [Arduino overview](https://docs.arduino.cc/tutorials/uno-rev3/intro-to-board/) . See the overview of our board (Elegoo / Arduino R3). Includes details on number of Digital/Analog pins and max current draw.

The following tutorials focus on controlling outputs.
1. [L1: Powering an LED with Arduino](https://makeabilitylab.github.io/physcomp/arduino/led-on.html). This will walk through turning on an LED with just the power rail and ground; no programming required. Leverages concepts already covered during our Electronics Week.
1. [L2: Blinking an LED](https://makeabilitylab.github.io/physcomp/arduino/led-blink.html). Introduces digital pins, setting pinMode to Output, digitalWrite, Compilation/Upload, and blinking using Delay.
1. [L3: Debugging with Serial](https://makeabilitylab.github.io/physcomp/arduino/serial-print.html). Use the Serial monitor and plotter for debugging and outputting states using Serial.print and Serial.println. Also printing multiple lines with labels.
1. [L4: Fading an LED](https://makeabilitylab.github.io/physcomp/arduino/led-fade.html). Use analogWrite and overview of how PWM works to fade an LED. Also printing multiple lines with labels.
1. [L6: Blinking two LEDs](https://makeabilitylab.github.io/physcomp/arduino/led-blink2.html). Shows how to wire LEDs to turn them on using either HIGH or LOW pin outputs.
1. [L4 advanced: Vibromotors](https://makeabilitylab.github.io/physcomp/advancedio/vibromotor.html). Shows how to use NPN transistors to control a vibromotor (a DC motor with eccentric mass). The core material will already have been covered in our **Electronics week**, so feel free to only skim.

The following tutorials focus on controlling inputs.
1. [L1: Using buttons](https://makeabilitylab.github.io/physcomp/arduino/buttons.html). Covers push buttons, setting pinMode to input, reading digital inputs, pull-down and pull-up resistors. 
1. [L4: Potentiometers](https://makeabilitylab.github.io/physcomp/arduino/potentiometers.html). Covers potentiometers as variable resistors and voltage dividers, using analogInput, and explains Arduino's ADC. 

The following are dedicated short tutorials on control structure.
1. [For loops](https://www.youtube.com/watch?v=YUqiPSJu8sI). How to write a For loop in Arduino. [8 minutes].
1. [If/Else statements](https://www.youtube.com/watch?v=p_xtHch2AO0). How to write a If/else statements in Arduino. [7 minutes].


### [Optional] Further resources


1. [Adafruit’s Arduino guide](https://learn.adafruit.com/series/learn-arduino). A plan with 17 mini-lessons with code examples.
1. [Arduino Uno Pinout Diagram](https://docs.arduino.cc/resources/pinouts/A000066-full-pinout.pdf). A labelled breakdown of all the pins on the Elegoo/Arduino Uno.


[//]: # What to do in the lab
[//]: #1. [Connect to Arduino](https://makeabilitylab.github.io/physcomp/arduino/arduino-ide.html). You should already have installed the Arduino IDE (**see readings**). Now go to Step 3 and select/confirm _Arduino Uno_ from the dropdown.
[//]: #1. Blink an breadboard-mounted LED on and off; 1 second on, 0.5 seconds off. _Hint: pinMode, digitalWrite, Delay._ 
[//]: #1. Using the same circuit, add code to use the serial monitor to print the LED state (off or on) in real time. _Hint: Serial.print, Serial.println_ 
[//]: #1. Blink an breadboard-mounted LED on and off; 1 second on, 0.5 seconds off. 





