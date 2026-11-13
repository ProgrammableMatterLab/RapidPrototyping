---
title: Week 7
nav_order: 9
nav_exclude: false
description: >-
    Week 7 activities
---

# Week 7 - Doing more with Arduino
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

This week’s readings center on using Arduino for stronger control of more advanced electronic components. 

### Tutorials / Readings

We recommend going through the tutorials in the order given.

1. [Ultrasonic Distance Sensor Tutorial](https://www.makerguides.com/hc-sr04-arduino-tutorial/). This tutorial from Makerguides introduces the HC-SR04 Ultrasonic Distance Sensor, how to wire it electronically and how to use Arduino to read from it.
1. [L1: Smoothing Input](https://makeabilitylab.github.io/physcomp/advancedio/smoothing-input.html). A tutorial covering how to smoothen noisy analog input readings. Covers averaging filters, moving averages, and median filters.
1. [L3: Button de-bouncing](https://makeabilitylab.github.io/physcomp/arduino/debouncing.html). A tutorial covering how to debounce - to remove chatter from - inputs like pushbuttons.
1. [L3: Servo Motors](https://makeabilitylab.github.io/physcomp/advancedio/servo.html). A tutorial covering how to use Servo motors; components that use closed-loop feedback to precisely control angular position.
1. [Stepper Motor tutorial](https://www.youtube.com/watch?v=7spK_BkMJys). A tutorial covering controlling Nema 17 stepper motors using Arduino. Covers stepper motor basics, discusses differences between drivers, and includes Arduino code snippets. [30 minutes].
1. [Limit switches tutorial](https://www.youtube.com/watch?v=YwO5OnJGHho). A brief introduction to what limit switches do followed by a tutorial covering how to use them with stepper motors, including Arduino code snippets. [20 minutes].
1. [L1: Intro to Serial](https://makeabilitylab.github.io/physcomp/communication/serial-intro.html). A tutorial covering communication over Serial. You've previously seen how to read data _from_ the Arduino for display on your computer's Serial monitor; this tutorial will go into more detail and also show how to user the serial monitor to write data _to_ the Arduino from your keyboard.



### [Optional] Further resources
1. [Inside Arduino](https://makeabilitylab.github.io/physcomp/arduino/inside-arduino.html). A more detailed overview covering some of the inner workings of the key functions we use: how the analogRead ADC works and how fast it samples data; what delay() actually does, how digitalWrite works, etc. 

## Lecture

**Note**: there is no lecture this week as it is Veteran's Day, which is a UW Holiday.


## Hardware & Software

This week will involve extending our electronics and programming capabilites. We will continue programming the Elegoo/Arduino micrcontroller using the Arduino IDE, introducing new components on top of the electronics hardware previously introduced in week 5.

### Hardware

Please bring and prepare to re-use the components from previous weeks:
1. Elgeoo / Arduino Uno microcontroller
1. All electronics and kits introduced in [Week 5]({{ '/docs/week5/' | relative_url }}).
1. Your laptop

This week we'll experiment with the following new components; please return to us when done so we can keep them in storage:
1. HC-SR04 Ultrasonic Distance Sensor (x1)
1. Micro Servo Motor MS18 (Sg90 9g) (x1)
1. Nema 17 Stepper Motor (x1)
1. TMC2209 Stepper Driver (x1)
1. Limit switch (x1)
1. 12V output power adapter (x1)


### Software

1. Arduino IDE
1. [Falstad Circuit Simulator](https://www.falstad.com/circuit/circuitjs.html)





## Lab

This lab will have the following activities:

1. Brief lecture introducing Final Project specification and groups.
1. Lab activity introducing using Arduino to control more electronics.
1. (Optionally) Begin coordinating with your Final Project Group for this week's task. 

### Doing more with Arduino

You will complete a number of challenges in the lab using a new set of components that will round out key capabilities we can enable using Arduino: limit switches, stepper motors and servo motors. You will also see ultrasonic distance sensors and use power adapters, make your inputs more reliable, and control the Arduino by typing into the Serial Monitor. **You should have completed all the readings when you arrive in lab.**

You should work in pairs for the lab activity.

#### What to do in the lab

Please do the following:

1. First, read the Assignment Task description below so you understand what you need from your Final Project teammates over the week ahead.
1. Come back here and proceed with the lab activity section.

The following exercises are intended to get you familiar with reading limit switches and ultrasonic distance sensors, and with controlling motors using the Arduino. 

See the [Advanced Components]({{ '/docs/resources/Week7_components/' | relative_url }}) page for more details and guidance for each component. Note that these details _supplement_ - but do not replace - the readings.

**Important:** The stepper motor and the servo draw more current than the Arduino can supply. Power the stepper driver from the 12V power adapter, and the servo from the 5V buck converter (via the power adapter). On the breadboard, ensure you connect the Arduino Ground to the Grounds of the power adapter, buck converter and drivers. Never connect or disconnect the stepper motor while the power adapter is on: this can destroy the driver. Build all the circuits on breadboards, and check your wiring before powering up.

For all the problems below, do not exceed the maximum currents and voltages of your devices (see the **Tip** below):

1. Using a pushbutton, write a program that toggles an LED on or off each time the button is pressed, and prints the total number of presses to the Serial Monitor. Press the button slowly several times: does the count always go up by exactly one? Hint: digitalRead, INPUT_PULLUP, Serial.println.
1. Update the previous program to debounce the button, so that every press is counted exactly once. Hint: millis; see the [Button de-bouncing](https://makeabilitylab.github.io/physcomp/arduino/debouncing.html) reading.
1. Using a limit switch, write a program that prints "open" or "pressed" to the Serial Monitor each time the switch changes state. Hint: a limit switch has C (common), NO (normally open) and NC (normally closed) terminals; the pair you use decides whether pressing it reads HIGH or LOW. Limit switches bounce just like buttons.
1. Using a servo motor, write a program that sweeps the servo from 0° to 180° and back, repeatedly. Attach a servo horn (the small plastic arm that comes with the servo) so you can see the angle. Ensure the servo is powered from the buck converter, not the Arduino. Hint: Servo library, attach, write, for.
1. Using the Serial Monitor, write a program that moves the servo to an angle you type on your keyboard. Ignore any value outside 0–180° and print a message instead. Hint: Serial.available, Serial.readStringUntil, toInt.
1. Using the ultrasonic distance sensor, write a program that prints the distance to your hand, in cm, to the Serial Monitor. Hint: pulseIn; see the [Ultrasonic Distance Sensor](https://www.makerguides.com/hc-sr04-arduino-tutorial/) reading.
1. Update the previous circuit to set the servo angle from the distance to your hand (for example, 5cm = 0° and 40cm = 180°). Smooth the distance readings so the servo does not twitch, and print both the raw and the smoothed distance. Hint: moving average, map, constrain; see the [Smoothing Input](https://makeabilitylab.github.io/physcomp/advancedio/smoothing-input.html) reading.
1. Using a stepper motor and a TMC2209 driver, write a program that turns the stepper exactly one revolution clockwise, pauses for 1 second, then turns one revolution counter-clockwise. Ensure the motor is powered from the power adapter, not the Arduino. Hint: STEP, DIR and EN pins, for; how many steps make one revolution? (see the Tip below).
1. Using a pushbutton, update the previous circuit so that the stepper turns continuously and reverses direction each time the button is pressed. Hint: debouncing; while a for loop is stepping the motor, the Arduino cannot read the button, so try micros.
1. Using a limit switch, write a homing routine: when the Arduino starts, the stepper turns slowly toward the limit switch until the switch is pressed, then stops, backs off a little, and records that position as zero. Since the motor is not mounted in a machine yet, press the limit switch by hand while the motor turns, to stand in for the machine reaching the end of its travel. Hint: while.
1. Update the previous program so that the stepper moves to a position (in steps) typed into the Serial Monitor, never moves past a maximum position, and stops immediately if the limit switch is pressed during a move. Hint: keep count of every step the motor takes.



{: .highlight }
> **Key values**
>
> **Arduino:** individual pins: continuous current 20mA, maximum for a short duration 40mA. Total current across all pins: 200mA. Never power a motor or servo from an Arduino pin.
>
> **Buck converter:** input 1.3A max, output 3A max.
>
> **TMC2209 stepper driver:** motor supply (VM) 4.75–29V; logic supply (VIO) 3.3–5V, from the Arduino's 5V. The driver only turns the motor while EN is LOW. With MS1 and MS2 left unconnected, it uses 8 microsteps per step. The motor current has been preset by the TAs: do not turn the small trim pot on the driver. The driver gets hot while running; do not touch it. Only the driver's two long rows of pins go into the breadboard: the DIAG and INDEX pins next to EN are outputs and must not share EN's breadboard row.
>
> **Stepper motor:** 200 steps per revolution (1.8° per step), so 200 × 8 = 1600 STEP pulses per revolution with the TMC2209. It has two coils (4 wires); the two wires of one coil measure a few Ω on a multimeter.
>
> **Servos (MS18 / MG90s):** 4.8–6V. They can draw several hundred mA when starting or when blocked.
>
> **Limit switches:** three terminals: C (common), NO (normally open) and NC (normally closed).
>
> **HC-SR04:** 5V; range about 2–400cm; wait about 60ms between readings.

## Assignments

**Important**: Note the assignment deadline below. Please begin by seeing the [Final Project]({{ '/final-project/' | relative_url }}) page for _group assignments_ and more detailed information about the final project, including upcoming _deadlines_.

1. **Reading:** No reading.
1. **Google Site:** Create a _new_ Google Site for your Group Project. 
1. **Conceptual Design Review**: Conceptual design of 3 project idea proposals.

<figure style="text-align: center;">
  <img src="{{ '/assets/images/W7-blueprint.png' | relative_url }}"
       alt="device"
       style="display: block; max-width: 99%; height: auto; margin: 0 auto;">
  <figcaption>Figure 1: Final Project Brainstorm.</figcaption>
</figure>

### Google Site for Final Project

You will create a new Google Site as a group to document your final project. See the steps below.
1. See the [Final Project]({{ '/final-project/' | relative_url }}) page for _group assignments_ and contact details.
1. Create a _new_ Google Site for your Group Project. 
1. Transfer ownership to Martin (nisser@uw.edu) and ensure all group members are editors. 
1. Publish your site with the web address set to a concatenated string of the class acronym and your Group number; for example, Group 3's project would be: _AA598-AUT26-Group-3_. 
1. On the home page, clearly display the Group number and list the group members (first and last name).
1. Link your group project site to your _personal_ website by adding a "Final Project" entry to your assignments drop-down on your personal website. 




### Conceptual Design Review (CoDR)

A Conceptual Design Review (CDR) is a high-level analysis of a project idea. It is typically the first design review for any system, and its purpose is to flesh out system-level challenges and risks.  You will brainstorm final project ideas as a group and choose **3 projects proposals** to analyze and complete a CoDR for.

#### Deadlines

- **Issued**: Friday November 13, 1pm (Week 7 lab)
- **Due**: Thursday November 19, 11:59pm (day after Week 8 lecture). 

Note this deadline is set so staff can answer lingering questions during Wednesday lecture, while giving staff time to review submitted CoDRs before that Friday's lab. We will discuss the proposals with you and select a project **during Friday lab.**

#### Deliverables

There is 1 deliverable:
- Publish your CoDR to your Group Project Website.

To submit your CoDR, document it under a "CoDR" heading on your Group's Google Site, then publish it. Remember: You must transfer ownership to Martin _and_ publish your website for your submission to be complete. 

See below for the sections required for **each of the three project proposals**.

---

#### Project Description 


The project description should communicate the concept clearly enough for others to understand its intended use case, its capabilities, and why it's useful. Please first see the [Final Project]({{ '/final-project/' | relative_url }}) page for guidance on scoping. Include the following information (approximately 300 words):

##### Project Title

Give the project an appropriately named title.

##### Problem or Opportunity
What problem, need, frustration, or creative opportunity does the project address?

##### Proposed Solution
- What physical device are you proposing, and how does it address the problem or opportunity? 
- Is it novel - does it accomplish something that you can't buy an existing device to do? 
- Is it creative - is it artistic in nature, or does it solve a problem that's already solved, but do so in a creative new way?
- Does it involve technical depth - does it incorporate all major class skills, or even go beyond them?

##### Use Case and Target User
Explain who this device is for, and in what context (when and where).

##### Demo
Your final presentation will include a live demonstration of the physical device: what exactly will you show it doing?



#### Project Design Sketch & System Requirements


##### Sketches 

Provide a sketch or other visual representation that communicates what the physical project will look like and what it will do. Hand-drawn sketches are welcome. Briefly annotate or label the sketch with key features related to its:
1. _Function/code_ (e.g. pressing this button makes the robot move forward)
1. _Electronics_ (e.g. 2 stepper motors; 1 ultrasonic distance sensor)
1. _CAD/Geometry_ (e.g. electronics enclosure; rack-and-pinion mechanism)

##### System Level Requirements 

Alongside the sketch, identify the key System Level Requirements for your project. For example, for a 2D drawing machine, this might be: 
1. Accepts an image upload from user as png/jpg
1. Parses & thresholds image to produce G-code as a drawable, line-based representation 
1. Physically draws pictures using a pen in 1 color
1. Allow joystick control as well as automatic control of the pen end effector
1. Does not drop pen; does not damage itself during operation

#### Bill of Materials (BoM)

You will have access to all of the materials and components that have been introduced in the course far. You can also make requests for additional materials and components; we will consider all requests but can't guarantee making these available. To keep this tractable and ensure timely delivery, you will be asked to specify such requests during the CoDR below.

##### Class BoM
Identify a BoM that makes use only of class components and materials. Provide a table with: 
1. The item name (e.g. Stepper motors, or black PLA)
1. How many units of each item; for example 3x (stepper motors); or 1kg (Black PLA)

##### Extended BoM

Optionally, identify and request an extended BoM beyond the class materials/components. Note that these are not guaranteed. Provide a table with: 
1. The item name (e.g. Stepper motors, or black PLA)
1. How many units of each item; for example 3x (stepper motors); or 1kg (Black PLA)
1. An Amazon link for purchasing
1. The unit cost from Amazon
1. A justification for each item
1. The total cost of the Extended BoM


#### Risk Assessment

##### Risk identification 
Identify key risk(s): what part of the project are you most uncertain about successfully implementing, or what is most likely to fail? 

##### Risk Mitigation/Downscope 
What will you do to mitigate these risks, and what is a fallback plan you can implement to still have your project succeed if the risk-prone part fails?

##### Upscope 
If the risks prove mitigated and the original project scope proves easier to implement than expected, what extended features or capabilities will you augment the project with?  


#### Project Evaluation and Comparison

Once you have completed the above deliverables for each of the three project propsals, end with a brief summary  comparing the three concepts. Include a table, assigning a grade for each proposed project between 1 (worst) and 5 (best), for Novelty, Creativity, Usefulness, Technical Depth, Feasability, and Risk; report the summed total grade for each proposal.
