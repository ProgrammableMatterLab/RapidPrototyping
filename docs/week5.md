---
title: Week 5
nav_order: 7
nav_exclude: false
description: >-
    Week 5 activities
---

# Week 5 - Electronics
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

This week's readings center on electronics, covering introductory circuit design and prototyping physical circuits.

### Tutorials / Readings

The core readings center on Jon Froehlich's excellent introduction to electronics series. You do not need to complete the activity at the bottom of each page. 
1. [Lesson 1: Voltage, current, and resistance](https://makeabilitylab.github.io/physcomp/electronics/electricity-basics.html). This refreshes the foundations of current, voltage, and resistance.
1. [Lesson 2: Circuit Schematics](https://makeabilitylab.github.io/physcomp/electronics/schematics.html). You'll learn circuit schematics; the visual language used in datasheets, circuit simulators, and PCB layout software to describe circuits.
1. [Lesson 3: Ohm’s Law](https://makeabilitylab.github.io/physcomp/electronics/ohms-law.html). This will refresh Ohm’s Law, describing how current, voltage, and resistance relate.
1. [Lesson 4: Series and Parallel Resistors](https://makeabilitylab.github.io/physcomp/electronics/series-parallel.html). Covers series and parallel resistor circuits, how to analyze them, and why they matter. 
1. [Lesson 5: Using Resistors](https://makeabilitylab.github.io/physcomp/electronics/resistors.html). A deeper dive into resistors; how they work, how they’re made, and how they’re characterized.
1. [Lesson 6: LEDs](https://makeabilitylab.github.io/physcomp/electronics/leds.html). This introduces a semiconductor device, the diode, and shows how to use LEDs. 
1. [Lesson 7: Breadboards](https://makeabilitylab.github.io/physcomp/electronics/breadboards.html). Introduces breadboards as a prototyping tool.
1. [Lesson 8: Variable Resistors](https://makeabilitylab.github.io/physcomp/electronics/variable-resistors.html). This will go over variable resistors and potentiometers in particular.

In addition, please complete the following readings on circuit simulation, soldering, transistors, and motors.
1. [Intro to Falstad Circuit Simulator](https://www.youtube.com/watch?v=DtXR7jOm2_s). This is an introductory tutorial to Falstad CircuitJS, a browser-based circuit simulator. [20 minutes].
1. [Intro to soldering and de-soldering](https://www.youtube.com/watch?v=rK38rpUy568&t=167s). A beginner's demo for soldering. [6 minutes].
1. [Transistor overview](https://www.youtube.com/watch?v=J4oO7PT_nzQ). Introduction to bipolar transistors; covers NPN and PNP and modes of operation (amplifier/switch). [First 8.5 minutes only].
1. [Transistor worked example](https://www.youtube.com/watch?v=VJJuxQk5fTY). Worked example of using a transistor as an amplifier and inverter. [16 minutes].
1. [Transistor worked example 2](https://www.youtube.com/watch?v=5DoYuxDzczQ). Worked example of using an NPN transistor as a switch. [5 minutes].
1. [DC motor basics](https://itp.nyu.edu/physcomp/lessons/dc-motors-the-basics/). Covers the basics ov DC motors. Introduces most common types; DC, gearhead, control basics, and brief coverage of servos and steppers.

### [Optional] Further resources
1. Sparkfun's guide to [How to read schematics](https://learn.sparkfun.com/tutorials/how-to-read-a-schematic/all).




## Lecture

Since last week, you've worked on designing and building physical mechanisms. You've also completed additional readings on electronics. In this lecture, we will:
1. Discuss the readings and answer any questions that came up.
1. Give an overview on electronic prototyping.
1. Introduce this week's Lab.

You can access the Lecture 5 slides here: [Lecture 5 slides](https://docs.google.com/presentation/d/1a1gQpWYGDT1OaLJjrzUqTSsxNgZBGAhRKKj254MkHjA/edit?usp=sharing).

## Hardware & Software


### Hardware

#### Multimeters
We will have five multimeters that will be shared for the lab activity.

#### Soldering stations

The Mill has 3 Soldering stations. These are reserved for us 3-4pm during this lab (October 30). Wear the provided safety glasses during soldering

Soldering stations are generally first-come first-served, but they have been reserved exclusively for us on the following lab days/times:
1. Friday, October 30th from 3:00 PM - 4:00 PM
1. Friday, November 6th from 1:00 PM - 4:00 PM
1. Friday, November 13th & 20th, 3:00 PM - 4:00 PM
1. Friday, December 4th, 3:00 PM - 4:00 PM
1. Friday, December 11th, 1:00 PM - 4:00 PM

#### Materials

The lab will involve prototyping several circuits; below are the components we will use. Please only take as many units as specified below, unless otherwise specified. You can keep them with you for the assignment. 
1. Breadboard (x1)
1. Pushbuttons (x4)
1. Potentiometers (x1)
1. LEDs (x3)
1. NPN and PNP BJT transistors (x2 each)
1. DC motor, rated 3-6V (x1)
1. 9V battery and connector (x1)
1. Buck converter 9-12V to 5V (x1)
1. Resistors (as needed)
1. Jumper wires (x20 or as needed)
1. Terminal blocks, assorted sizes (6x total terminals for battery & buck; for example 3x 2-terminal blocks, or as needed)

We will also have the following resources which should stay in lab:
1. Multimeters (shared during lab - x5 available)
1. Solderable Perfboards (shared during lab - for solder practice)
1. 3D printed Blocks and heatset inserts (shared during lab - for solder practice) 

We will store extras for most components (LEDs, wires, resistors etc.) in the storage room so you can collect new components as you work on the assignment if needed. To complete the assignment, you will also need:
1. Solderable breadboard (x1)
1. Heat set inserts (around x4, or as needed)


[//]: # Elgeoo / Arduino Uno microcontroller

### Software

You will need the browser-based [Falstad Circuit Simulator](https://www.falstad.com/circuit/circuitjs.html) introduced during the readings.




## Lab

This lab will have the following activities: 
1. Prototyping electronic circuits on breadboards. 
1. Soldering and Heatset insert training, _3-4pm_.
1. Start the assignment task. 


If you have not soldered or used heatset inserts before, please attend solder training. The Mill has 3 soldering stations and are reserved us from 3-4pm.

### Electronic prototyping

You will begin work on your **assignment** task to produce an _Analog electronic device_. Start during the lab, and finish on your own time. You should have **completed all the readings** when you arrive in lab.

**You will need to submit the assignment individually, but feel free to work in pairs during lab.**

#### What to do in the lab

Please do the following:
1. First, read the Assignment _Task_ description below so you understand what you need to know when you leave lab.
1. Second, read the _Materials_ section above to know which components you'll need for the lab activity and assignment. 
1. Come back here and proceed to read this lab activity section section.

The following electronic prototyping problems are intended to get you familiar with working with electronics so you can ask questions during lab and prepare yourself to complete the Task on your own. These are not graded, so if you're already comfortable with some concepts you are welcome to skip some steps.


To succeed on the assignment task, your goal during the lab should be to design several electronic circuits in the Falstad simulator, build them physically, and inspect them using a multimeter. For all the problems below, simulate them in falstad first, then build them and check key currents/voltages with a multimeter
1. Build a circuit with a voltage source, and a single LED and resistor in series. See the **Tip** below and choose resistances accordingly
1. Replace the series resistor with another resistor value that dims the single LED.
1. Using a pushbutton, build a circuit to enable lighting the LED when the button is pressed.
1. Using a pushbutton, build a circuit to enable lighting the LED when the button is **NOT** pressed.
1. Remove the push button. Using a potentiometer, build a circuit to enable manually dimming/brightening the LED. Ensure that the max LED current is never exceeded, no matter what value is set by the pot.
1. Using a new circuit, make 3 LEDs light up with the same brightness.
1. Using a new circuit, make 3 LEDs light up with different brightnesses. 
1. Using a transistor, build a circuit to enable lighting an LED when a button is pressed.
1. Using a transistor, build a circuit to enable turning on a DC motor when a button is pressed.
1. Using a set of transistors and buttons, build a circuit that enables toggling the _direction_ of a DC motor. We recommend the simplest solution, which would be to use 4 buttons (one for each transistor), and require you to press 2 buttons at a time.
1. Ensure you **complete solder & heatset training** if you need, then feel free to begin working on the task assignment.

{: .highlight }
> **Key values for electronics**
> 
> **For our LEDs:** The maximum current tolerated by our LEDs is 20mA, and Forward Voltages are: Red/Yellow 2.0-2.2V; Blue/Green/White 3.0-3.2V. 
> 
> **For our power supplies:** The maximum current ratings of our buck converters is (input: 1.3A, output: 3A), and the batteries is 500mA. To be conservative and prevent voltage drops, ensure your circuit consumes less than 250mA in total. 

## Assignments

1. **Task:** Complete this week's Task and publish your documentation on your Google Site.
1. **Reading:** Complete the [Week 6 Readings]({{ '/docs/week6/' | relative_url }}).


<figure style="text-align: center;">
  <img src="{{ '/assets/images/W5-device.png' | relative_url }}"
       alt="device"
       style="display: block; max-width: 99%; height: auto; margin: 0 auto;">
  <figcaption>Figure 1: A circuit board encased in a 3D printed enclosure.</figcaption>
</figure>


[//]: # INSERT IMAGE



### Task: Analog electronic device

#### Task definition

By Analog electronic device, we mean an electronic circuit that uses only analog components (as opposed to a microcontroller) and is integrated into a fabricated enclosure. The circuit must be soldered onto a perfboard or solderable breadboard, which should be fastened using M3 bolts to the enclosure. 

To put this in context of what we've done before, think of it as building a computer mouse - but this time we're building both the enclosure and the electronics from scratch.



#### Task learning objectives
The goals of this assignment are to:
1. Understand how to design circuits consisting of inputs and outputs, with appropriate current-limiting resistors
1. Learn to draw and simulate circuit schematics
1. Learn how to protoype electronics on a breadboard
1. Understand how to solder electronics onto perfboards and fasten these to an enclosure

#### Task Deliverables

The deliverables center on electronic design and integration into a fabricated enclosure.

At a minimum, you should complete:
1. Circuit schematic and circuit simulation gif/video from the Falstad simulator.
1. CAD screenshots of your mechanical enclosure/parts.
1. Photos of your physical mechanical enclosure/parts, your soldered circuit board, and how the board is fastened to/inside the enclosure. 
1. Photos and video/gifs of your assembled device working. The device should:
   1. Have a function that you have articulated as a design objective.
   1. Incorporate at least 2 separate inputs (e.g. button, pot) and 2 separate outputs (e.g. LED, motor)
   1. Include a soldered perfboard or solderable breadboard, which is mounted to the enclosure using M3 bolts (via heatset inserts or sunken nuts)
   1. Justify your circuit design and your use of 3D printing / laser cutting for each part.


For full credit, you can try some of the following:
1. Increase circuit complexity / use more components
1. Thoughtful design objective, and a clean aesthetic with high quality integration of electronics and enclosure with intentional spatial layout of electronics.
1. Use a soldered H bridge and motor to actuate a mechanism integrated in your device; 
   1. For example, you might use buttons, a motor and set of LEDs to actuate a geartrain, using LEDs to display 3 different states for OFF, Clockwise, and Counter Clockwise motor directions. 
   1. The focus is on electronics and integration, so you are welcome to build off a mechanism you already designed for the previous task. For example, you may wish to take an existing mechanism from your Rube Goldberg machine to modify and electrify.


To submit your assignment, document it under a Week 5 heading on your Google Site, then publish it.