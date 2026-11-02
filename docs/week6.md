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

1. [Arduino Overview (video)](https://www.youtube.com/watch?v=tiGw9PQbvrg). Quick, high level overview of what the Arduino is, what it's used for, and key concepts like setting voltages on digital pins with, using PWM, ADC on the analog input pins, as well as key elements of the Arduino IDE including code examples. [9 minutes].

1. The following are key documentations from the official Arduino Docs website for understanding programming in the Arduino IDE. 
    1. [Arduino API.](https://docs.arduino.cc/learn/programming/reference/?_gl=1*19suhw0*_up*MQ..*_ga*NDg4NTI2OTQ5LjE3OTMyNDMxMTU.*_ga_NEXN8H46L5*czE3OTMyNDMxMTMkbzEkZzEkdDE3OTMyNDMyMjMkajM4JGwwJGg4MDg1MTIwMDM.) See the following key functions, and pay attention to the examples that use them in the tutorials to come; these enable most of the functionality we are interested in:
        1. **Digital I/O:** digitalRead, digitalWrite, pinMode
        1. **Analog I/O:** analogRead, analogWrite
        1. **Time:** delay, millis
        1. **Serial:** print, println
        1. **Data types:** int
        1. **Sketch:** void setup, void loop
        1. **Control Structure:** if, else, for, while   
        1. **Further Syntax:** block comment, single line comment, semicolon 
        1. **Arithmetic Operators:** all
        1. **Comparison Operators:** all
        1. **Boolean Operators:** all
    1. [Arduino Sketches.](https://docs.arduino.cc/learn/programming/sketches/?_gl=1*s4uz6u*_up*MQ..*_ga*NDg4NTI2OTQ5LjE3OTMyNDMxMTU.*_ga_NEXN8H46L5*czE3OTMyNDMxMTMkbzEkZzEkdDE3OTMyNDQwODUkajI4JGwwJGg4MDg1MTIwMDM.) Anatomy of an Arduino Sketch; setup & loop, variables, functions, as well as quick overview of pinMode, digitalWrite, and delay.
    1. [Arduino Variables.](https://docs.arduino.cc/learn/programming/variables/?_gl=1*1ui3kus*_up*MQ..*_ga*NDg4NTI2OTQ5LjE3OTMyNDMxMTU.*_ga_NEXN8H46L5*czE3OTMyNDMxMTMkbzEkZzEkdDE3OTMyNDQyODMkajU4JGwwJGg4MDg1MTIwMDM.) Using variables in the Arduino IDE, examples using int and writing to a pin. 
    1. [Arduino Functions.](https://docs.arduino.cc/learn/programming/functions/?_gl=1*o967ps*_up*MQ..*_ga*NDg4NTI2OTQ5LjE3OTMyNDMxMTU.*_ga_NEXN8H46L5*czE3OTMyNDMxMTMkbzEkZzEkdDE3OTMyNDQyODYkajU1JGwwJGg4MDg1MTIwMDM.) Writing functions in the Arduino IDE, examples using multiplication and for loops. 


1. [Arduino In-depth Starter Tutorial (video)](https://www.youtube.com/watch?v=BLrHTHUjPuw). An in-depth look at both the arduino hardware (expounding on the previous overview), and programming in the Arduino IDE. Covers code structure, variables, pinMode, conditionals (if statements), serial monitor, analogRead, analogWrite, digitalRead, digitalWrite, delay, and Arduino libraries. [85 minutes].



1. [Install Arduino IDE](https://makeabilitylab.github.io/physcomp/arduino/arduino-ide.html).
Download and Install the Arduino IDE on your laptop. See Step 1 for installation and Step 2 to open the IDE to confirm proper installation. 
1. [Arduino overview](https://docs.arduino.cc/tutorials/uno-rev3/intro-to-board/) . See the overview of our board (Elegoo / Arduino Uno Rev3). Includes details on number of Digital/Analog pins and max current draw.

The following tutorials focus on controlling outputs.
1. [L1: Powering an LED with Arduino](https://makeabilitylab.github.io/physcomp/arduino/led-on.html). This will walk through turning on an LED with just the power rail and ground; no programming required. Leverages concepts already covered during our Electronics Week.
1. [L2: Blinking an LED](https://makeabilitylab.github.io/physcomp/arduino/led-blink.html). Introduces digital pins, setting pinMode to Output, digitalWrite, Compilation/Upload, and blinking using Delay.
1. [L3: Debugging with Serial](https://makeabilitylab.github.io/physcomp/arduino/serial-print.html). Uses the Serial monitor and plotter for debugging and outputting states using Serial.print and Serial.println. Also printing multiple lines with labels.
1. [L4: Fading an LED](https://makeabilitylab.github.io/physcomp/arduino/led-fade.html). Includes use of analogWrite and an overview of how PWM works to fade an LED.
1. [L6: Blinking two LEDs](https://makeabilitylab.github.io/physcomp/arduino/led-blink2.html). Shows how to wire LEDs to turn them on using either HIGH or LOW pin outputs.
1. [L4 advanced: Vibromotors](https://makeabilitylab.github.io/physcomp/advancedio/vibromotor.html). Shows how to use NPN transistors to control a vibromotor (a DC motor with an eccentric mass). The core material will already have been covered in our **Electronics week**, so feel free to only skim.

The following tutorials focus on controlling inputs.
1. [L1: Using buttons](https://makeabilitylab.github.io/physcomp/arduino/buttons.html). Covers push buttons, setting pinMode to input, reading digital inputs, pull-down and pull-up resistors. 
1. [L4: Potentiometers](https://makeabilitylab.github.io/physcomp/arduino/potentiometers.html). Covers potentiometers as variable resistors and voltage dividers, using analogInput, and explains Arduino's ADC. 

The following are dedicated short tutorials on control structure.
1. [For loops](https://www.youtube.com/watch?v=YUqiPSJu8sI). How to write a For loop in Arduino. [8 minutes].
1. [If/Else statements](https://www.youtube.com/watch?v=p_xtHch2AO0). How to write If/Else statements in Arduino. [7 minutes].


### [Optional] Further resources


1. [Adafruit’s Arduino guide](https://learn.adafruit.com/series/learn-arduino). A plan with 17 mini-lessons with code examples.
1. [Arduino Uno Pinout Diagram](https://docs.arduino.cc/resources/pinouts/A000066-full-pinout.pdf). A labelled breakdown of all the pins on the Elegoo/Arduino Uno.


## Lecture

Since last week, you've worked on designing and building circuits using breadboarding and soldering using a variety of components. In this lecture, we will:
1. Hold a recitation on programming for Arduino.

## Hardware & Software


This week will focus on programming the Elegoo/Arduino microcontroller using the Arduino IDE. We will rely on the electronics hardware previously introduced in week 5.

### Hardware

For the lab:
1. Elgeoo / Arduino Uno microcontroller
1. All electronics and kits introduced in [Week 5]({{ '/docs/week5/' | relative_url }}).
1. Your laptop

### Software

1. Arduino IDE



## Lab

This lab will have a single activity: 
1. Programming with Arduino. 

### Programming with Arduino

You will complete a number of programming challenges in the lab to prepare you to complete the **assignment** task, which will involve a _Programmable retrofit_ of the Analog electronic device you already completed. You should have **completed all the readings** when you arrive in lab.

**You will need to submit the assignment individually, but feel free to work in pairs during lab.**

#### What to do in the lab

Please do the following:
1. First, read the Assignment _Task_ description below so you understand what you need to know when you leave lab.
1. Come back here and proceed with the lab activity section.

The following Arduino exercises are intended to get you familiar with programming in the Arduino IDE, debugging, and writing and reading from electronics.  

**Important**: You will use your laptop to power the Arduino and flash programs to it. You will also use a battery and transistors to allow drawing higher currents from the battery instead of the Arduino. On the breadboard, ensure you connect the Arduino Ground to the battery Ground. You should build all the circuits on breadboards, and verify the current draw manually or using Falstad before connecting & powering up the Arduino.

[//]: # To succeed on the assignment task, your goal during the lab should be to design several electronic circuits in the Falstad simulator, build them physically, and inspect them using a multimeter. 

For all the problems below, ensure you use appropriate current-limiting resistors in your circuits and do not exceed the maximum current outputs of your devices (see the **Tip** below):
1. [Connect to Arduino](https://makeabilitylab.github.io/physcomp/arduino/arduino-ide.html). You should already have installed the Arduino IDE (see this week's **readings**). Now go to Step 3 and select/confirm _Arduino Uno_ from the dropdown.
1. Blink a breadboard-mounted LED on and off; 1 second on, 0.5 seconds off. Don't forget a current-limiting resistor. _Hint: pinMode, digitalWrite, Delay._ 
1. Write a For loop that fades and brightens an LED repeatedly. _Hint: For, analogWrite._
1. Using the same circuit, write a For loop that fades and brightens an LED only 3 times, then leaves the LED on. _Hint: If/Else._
1. Using a pushbutton, write a program to enable lighting the LED when the button is pressed. The button should not be physically connected to the LED; read the button state using the Arduino, and toggle current to the LED using the Arduino. _Hint: digitalRead, If/Else._
1. Using two pushbuttons, enable lighting the LED only when _both_ buttons are pressed. Again, buttons should not be physically connected to the LED. 
1. Using the same circuit, add code to use the serial monitor to print the Button/LED state (off or on) in real time. _Hint: Serial.print, Serial.println_. 
1. Using an NPN transistor, battery, and buck converter: build a circuit to enable turning on an LED when a single button is pressed. Note: the button should not be physically connected to the LED; use the Arduino to toggle the transistors on/off; and ensure the LED is _powered_ from the buck, **not** the Arduino.
1. Using a motor instead of an LED, update the previous circuit to enable turning on the DC motor when the button is pressed. Ensure the motor is _powered_ from the buck, **not** the Arduino.
1. Using a potentiometer instead of a button, update the previous circuit to enable changing the speed of the DC motor when the pot is turned. Ensure the motor is _powered_ from the buck, **not** the Arduino.


{: .highlight }
> **Key current limits**
> 
> **For the Arduino:** Individual pins (continuous current: 20mA; maximum for short duration: 40mA). Total current across all pins: 200mA.
> 
> **For our 9V battery & buck converters:** The maximum current ratings of our buck converters is (input: 1.3A, output: 3A), and the batteries is 500mA. To be conservative and prevent voltage drops, ensure your circuit consumes less than 250mA in total. 

## Assignments

1. **Task:** Complete this week's Task and publish your documentation on your Google Site.
1. **Reading:** Complete the [Week 7 Readings & Preparation]({{ '/docs/week7/' | relative_url }}).
1. **Final Project Interest Form:** Complete the [Final Project Interest Form](https://docs.google.com/forms/d/e/1FAIpQLSdbAoUYMhUNMhjvWky1pBBXVdBKtHgwij1lJUYA8SKR3pShUw/viewform?usp=dialog) before Veteran's Day (note there's no lecture that Wednesday). We will use your response to assign groups for Final Projects.


### Task: Programmable Retrofit

#### Task definition

Modify your **Week 5** analog electronic device by adding a meaningful programmable behavior using an Arduino. Use the Arduino to read inputs and control outputs in a way that replaces, extends, or automates the functions of your existing device. This retrofit should replace all _hardwired_ connections between inputs and outputs (e.g. a button that toggles an LED circuit open/closed) with _programmable_ connections (the arduino reads the button input, performs a logical operation, then writes a value to toggle the LED).

The Arduino can remain outside the Week 5 enclosure; you do not need to permanently mount it inside/onto the device. The only modifications you need to make to your Week 5 device are to make its functionality programmable via the Arduino. For the enclosure, this might involve no re-design at all, or may require re-printing part of the enclosure with a small hole to allow transceiving signals from the Arduino. For the electronics and perfboard, you will need to modify and re-solder certain existing connections as needed to create a programmable interface to the Arduino. You may find this [3-minute De-soldering Tutorial](https://www.youtube.com/watch?v=bG7yW9FigJA) useful in addition to the soldering/de-soldering tutorial from last week's readings.

You should modify the Week 5 device to be programmable, and extend any functions you wish, and update the design objectives you established in Week 5 as you see fit. 

#### Task learning objectives

The goals of this assignment are to:
1. Learn to write and debug Arduino programs.
1. Use an input from a physical circuit to control an output through a program.
1. Modify a previously soldered circuit and fabricated enclosure to meet an updated design objective.

#### Task Deliverables: Programmable retrofit

The deliverables center on adding a meaningful programmed behavior to the Week 5 device while preserving the existing device as much as practical.

At a minimum, you should complete:
1. Updated hardware to allow Arduino interfacing, including:
   1. A updated electronic schematic; just a static schematic image (without simulation) is sufficient (See **Tip** below).
   1. A physically soldered perfboard; a photo.
   1. (If needed) a minimally updated enclosure that allows Arduino interfacing; CAD and physical photos.
   1. A description of the changes you made and why.
1. A working Arduino program, that replaces all _hardwired_ connections between inputs and outputs with _programmable_ connections:
   1. Provide commented source code for your Arduino program, with comments explaining the purpose of the main variables, functions, and control logic.
   1. Use the Serial Monitor to display input values and operating modes while operating the device; provide gifs/videos.
   1. A description of what the code does and why.
1. The functional, programmed device, including:
   1. Photos and Videos/Gifs of the assembled device operating. 
   1. A description of your design intent (the intended behavior) and what the device actually does.
   1. How using the Arduino _replaces/automates_ the original Week 5 circuit.

For full credit, you can try some of the following:
1. Use programming in Arduino to _extend_ the functionality of the original circuit with more complex behavior than what existed before, explaining how and why. For example, rather than just replacing a button-enabled LED with the equivalent programmed behavior, implement a control structure using loops and conditionals to brighten/fade it via button press. 
1. Augment the original circuit with additional physical inputs and/or outputs, and program their behavior via Arduino.
1. Use _millis()_ to create non-blocking timed behavior rather than relying entirely on _delay()_.
1. Implement [Button de-bouncing](https://makeabilitylab.github.io/physcomp/arduino/debouncing.html), which is itself a reading topic for next week, or research and implement other strategies for making the device respond more reliably.
1. Add a programmed safety behavior, such as a timeout or emergency stop.
1. Improve the physical presentation of the modified device while maintaining programming/troubleshooting access (for example, implement clean wiring pass-throughs, or add an enclosure/mount for the Arduino, etc.)


To submit your assignment, document it under a Week 6 heading on your Google Site, then publish it.


{: .highlight }
> **Arduino and Falstad**
> 
> **Static schematic:** To design a static circuit in Falstad that shows our Arduino pins, we can just add labelled nodes. Go to Draw → Outputs and Labels → Add Labeled Node, and then label the Node with Pin 1, Pin 2 etc. Note this will not _simulate_ the functionality, but it will show your schematic and is sufficient for our purposes.
> 
> **Simulated schematic:** There are a number of tools that also allow simulating circuits controlled via Arduinos. We do not require you to use these, but if you wish, feel free to check out the [Falstad AVR8js 8-bit AVR Arduino simulator](https://falstad.com/circuit/avr8js/) which embeds Arduino code directly into Falstad, and [TinkerCAD Circuits](https://www.tinkercad.com/circuits) which is a beginner-friendly tool to visually breadboard circuits and run Arduino code on them.