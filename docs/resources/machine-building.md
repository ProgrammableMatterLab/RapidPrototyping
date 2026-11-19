---
layout: page
title: Machine Building
parent: Resources
nav_exclude: false
description: >-
    Machine Building
---

# Machine Building
{: .no_toc .fs-9 }

## Overview

This page covers the machine building exercise. The purpose of the exercise and this documentation is to help you: 
- See the kind of work and iterations required to build a functioning device
- Plan and scope the technical aspects of your final projects
- Illustrate the documentation being requested of your final projects    

The machine detailed below is a 2D Drawing Machine. It contains detailed both **(1)** detailed instructions on how to assemble and operate it in lab and **(2)** documentation on its design and project management that illustrate many of the deliverables for the final project. The **Your project** boxes have tips documenting your own final project websites. 

<details markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
---

# Final Demo

Our drawing machine has two modes of operation, demonstrated below.

**Mode 1**: Draw from Image Upload. 
- This lets you upload an image to a webtool that converts it to Gcode that the Arduino uses for automatic drawing of that image.

**Mode 2**: Draw with Joystick.
- This lets you use the joystick to manually draw an image, which you can then 'replay'; the Arduino records the joystick commands and can automatically execute the same drawing.

## Mode 1: Automatic drawing from an image upload
{: .no_toc }

### Image upload & Gcode generation
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/final_upload.gif' | relative_url }}"
       alt="Animation: the converter page while it sends the W drawing to the machine"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The image converter page sending a drawing to the machine.</figcaption>
</figure>

### Automatic Drawing of Image 
<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/final_auto.gif' | relative_url }}"
       alt="Animation: the machine draws a W on its own from G-code that the converter page sends"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: GRBL drawing a UW logo sent from the image converter page.</figcaption>
</figure>

## Mode 2: Manual drawing using a joystick & Automatic replay
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/final_tracing.gif' | relative_url }}"
       alt="Animation: someone draws a path by hand with the joystick, then the machine draws the same path again on its own"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Drawing by hand with the joystick (JoystickDraw), then the machine redraws the path.</figcaption>
</figure>



{: .highlight }
> **Your project:** put a short GIF of your device working at the top of your page.

---

# Development Process

In this section, we have used our Drawing Machine to write up many of the deliverables being asked for from your final projects, spanning deliverables from the CoDR, PDR, CDR, and Final Build.
{: .fs-5 .fw-300 }



## Design Objective

### Initial Sketch

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/draw-machine-sketch.png' | relative_url }}"
       alt="Hand sketch of a pen plotter with a gantry frame, a pen, a stepper motor and a controller board"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Brainstorm sketch. Label the main parts on yours, like the stepper motor and the pen holder.</figcaption>
</figure>

### Problem or Opportunity

Drawing a picture by hand takes skill and time, and aren't easy to copy accurately; we'd like a machine to enable this. Breaking the 4th wall for a moment, as instructors we also have a meta problem, which is identifying a device that integrates the key course topics on CAD, 3D printing, electronics and code, that can be assembled and tested during a single lab, and showcases what a machine build could look like.

### Proposed Solution

- A 2-axis pen plotter. Two stepper motors move the pen in X and Y on GT2 belts and a servo lifts it. You upload a picture to a web page that makes G-code from it, or you draw with a joystick.
- It's for students in this class and fits on a tabletop. It draws up to 260 × 240 mm with any pen from 6 to 21 mm thick.
- With 13 printed parts, and a wide range of components introduced in the course, it relies largely on components and fabrication topics already covered. 
- It also integrates a custom G-code generation tool for automatic plotting; an example of a feature that goes _beyond_ the class topics, which is one of the full-credit suggestions.

{: .highlight }
> **Your project:** You are welcome and encouraged to leverage any skills/techniques/tools you have learnt outside of this class and bring them to bear on the final project. It could be applying a PID controller for motor control, FEA to maximize strength-to-weight ratio of a crucial bracket, or a web framework for a user interface. Tell us what you used and how.


## Functional Requirements

The functional requirements of the 2D drawing machine are:
1. Accepts an image upload from user as png/jpg. _The converter page opens PNG and JPG files._
1. Parses & thresholds image to produce G-code as a drawable, line-based representation. _It has three line styles and saves the result as a `.gcode` file._
1. Physically draws pictures using a pen in 1 color. _Any pen from 6 to 21 mm thick._
1. Allow joystick control as well as automatic control of the pen end effector. _GRBL draws automatically and JoystickDraw lets you steer by hand._
1. Does not drop pen; does not damage itself during operation. _The ratchet clamp holds the pen. Homing stops at the switches, and after that the firmware won't move past the edge of the work area._

{: .highlight }
> **Your project:** a functional requirement says what the device does. How well it does it belongs in the performance requirements. 

## Performance Requirements

The performance requirements of the 2D drawing machine are:
1. Toolhead travel at 100 mm/s in the X-Y plane. _We test it with `G0 X200` from home, which takes about 2.5 s._
1. Retract/extend pen in Z within 1 s. _Send `M5`, then `M3 S70`. The pen should touch the paper within 1 s._
1. Draw images that are visually identical to the parsed input image for 90% of attempts. _Draw the 100 mm test square 10 times. At least 9 should be within 1 mm, with closed corners._
1. Return to the same home within 0.5 mm. _Draw a cross, home, and draw it again. The two crosses should be less than 0.5 mm apart._

{: .highlight }
> **Your project:** give each performance requirement a number and a test you can run in the lab.


## Design Iterations

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/design_iterations.png' | relative_url }}"
       alt="Six pictures in two rows, all from the same angle and at the same scale: a hand sketch of a plotter on two side rails, the X axis on its own, then CAD versions V2, V3, V4 and V5.1. Circles mark what changed, with a close-up of the circled part for V3, V4 and V5.1."
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: From the first sketch to V5.1 with the 350 mm rods, the version you build. Stage 2 shows only the X axis of V2, and stages 2 and 3 have no belts drawn. V1, our first full CAD, is left out.</figcaption>
</figure>

| Stage | What we built | What we learned and changed next |
|---|---|---|
| 1 Sketch | A pen on a frame with a rail on each side, a stepper motor and a controller | Two rails have to be kept square to each other. We went with one rail and an arm that slides through the carriage, so there's nothing to keep square. |
| 2 One rail | A belt-driven X axis on its own: two 8 mm rods, the carriage, a NEMA17 motor and a GT2 belt | It worked, so we added the arm as the second axis. |
| 3 CAD V2 | The arm (Y axis) slides through the carriage on 8 short LM8UU bearings. Servo pen lift, one pen carrier per pen size, X ends on flat base plates, and every rod end locked by an M3 screw and nut | Eight bearings and a carrier for each pen size were more parts than we needed. |
| 4 CAD V3 | 4 long LM8LUU bearings, smaller X ends and one ratchet clamp for every pen size. Printed wedges and sliders, held by belt tension, replaced the rod-end screws | The wedges and sliders came loose whenever the belt went slack. |
| 5 CAD V4 | Back to a screw and nut on every rod end, as in V2. The belt ends press into toothed channels, and the pen slider runs on a dovetail on the arm head | The pen slider snagged on its dovetail. Both were printed standing up, so their layer lines caught on each other. |
| 6 CAD V5.1 | The pen slides on its own T rail (32), printed lying down. It touches the rail at two shoes with a 0.40 mm gap. We also refitted the X switch pocket. | We should have printed a test piece of the slide first. V5.1 comes with test pieces with gaps from 0.30 to 0.60 mm. |

[//]: # After V5.1 we changed the rod sizes. V5.1 was drawn with 430 mm rail rods and 300 mm arm rods, but the final build has four identical 8 × 400 mm rods. The printed parts didn't change. The X idler end sits 30 mm closer to the X motor and the arm tail 100 mm further out. In CAD that gives about 310 × 290 mm instead of 340 × 190 mm, but on our real machine the carriage stops at 260 mm in X, so we have a 260 × 240 mm work area.

{: .highlight }
> **Your project:** Show any major iterations and what changed. In general, get the most important/foundational thing working rudimentarily first, (for us that was one rail) and then iterate on it while adding other parts. To accelerate development, print small test pieces of key features (like toleranced sliding or snap fit features) before the real part, and start testing your code and electronics in parallel before the CAD is ready.



## System Block Diagram

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/block_diagram.png' | relative_url }}"
       alt="Block diagram. On the laptop the converter page turns a picture into G-code and sends it over USB to the Arduino Uno. UGS is optional, for saved .gcode files and typed commands. The Arduino runs GRBL or JoystickDraw and drives the stepper drivers, motors and servo. The joystick and the limit switches send their signals back to the Arduino. Power comes from the 12V adapter and the buck converter."
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Which part talks to which, and where the power comes from.</figcaption>
</figure>

{: .highlight }
> **Your project:** group the blocks by part or by function, and give information, power and motion their own arrow style.

## Schematic

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/schematic.png' | relative_url }}"
       alt="Schematic of the drawing machine with every pin connection: Arduino Uno, two TMC2209 stepper drivers and their stepper motors, two limit switches, servo, joystick, the 12V adapter through its DC jack, buck converter and 100µF capacitor"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Schematic of every electrical connection.</figcaption>
</figure>

The schematic shows which pin goes where, with each part drawn as a symbol. The [wiring diagram](#electronics) further down shows the same connections on the real parts and the breadboard, with a friendlier graphical representation and annotations. Wire from that, and use the schematic to check and explain the circuit.

{: .highlight }
> **Your project:** It's useful to provide both a schematic and a wiring diagram.

## Software

The Arduino runs one of two programs on the same wiring: JoystickDraw when you draw by hand, or GRBL when it draws a picture from the converter page.

### JoystickDraw pseudocode
{: .no_toc }

```
pins: STEP X2 Y3, DIR X5 Y6, EN 8, LIMIT X9 Y10, SERVO 11, JOYSTICK A4 A5 D12

setup()
  motors on, pen up
  read where the stick rests

loop()
  if not homed:
    if the button is clicked: home()
  else:
    if the button is clicked: pen down / pen up
    if the button is held 1.5 s: redraw()
    if the stick is pushed: move that way, faster the further it is pushed
    else: stop
    if the pen reaches the edge of the work area: stop that axis
    at each corner of the path: save the point, print it as G-code

home()
  pen up
  pull the arm in
    if the Y switch is pressed: stop, back off 3 mm
  move the carriage toward the X motor
    if the X switch is pressed: stop, back off 3 mm
  if a switch is never pressed: stop, print an error
  this corner is X0 Y0

redraw()
  pen up, go to where the recording starts
  for each saved point: set the pen as recorded, draw a straight line to it
  pen up, go home
  a click stops it at any time
```

JoystickDraw only uses the limit switches for homing. After that it keeps track of where the pen is and stops it at the edge of the work area.

### GRBL and the Image Converter page
{: .no_toc }

Our GRBL, the `grbl_pen` library, has a pen servo, two-switch homing and the plotter's settings built in. You [upload it](#arduino-programs) once, and from then on the Arduino reads G-code lines from USB and moves the motors and the servo.

The [Image Converter page]({{ '/assets/files/machine-build/Image_to_Gcode_tool/index.html' | relative_url }}) sends the G-code one line at a time and waits for GRBL's `ok` before it sends the next. We only use five commands: `G0` moves fast with the pen up, `G1` draws a straight line, `M3 S70` puts the pen down, `M5` lifts it and `$H` homes.

{: .highlight }
> **Your project:** write pseudocode for your main functions and your loop. It should fit on one screen.

## Bill of Materials (BoM)

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/parts_flatlay.png' | relative_url }}"
       alt="Every part for one machine laid out with part numbers, names and quantities: printed parts 01 to 10 and 32, the four rods, bearings, belts, pulleys, idlers, screws and nuts, the stepper motors, servo, limit switches and pen, and a line at the bottom listing the electronics on the table that are not drawn: Arduino Uno with USB cable, stepper drivers, breadboard, 12V power adapter, buck converter, jumper wires, joystick, capacitor and DC jack"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The parts for one machine. The electronics on the table (26 to 31 and 33 to 35) are listed at the bottom.</figcaption>
</figure>

Below is the BoM for the drawing machine. All these materials and components are provided in class. 


| Item | Units | Unit cost | Subtotal |
|---|---|---|---|
| PLA filament 1.75 mm, for printed parts 01 to 10 and 32 | 0.2 kg | $19.99/kg | $4.00 |
| Steel rod 8 × 350 mm, hardened, set of 4 (11, 12): two for the base rail, two for the arm | 4 | $5.42 (set of 4 $21.68) | $21.68 |
| Stepper motor NEMA 17, 1.5 A (14) | 2 | $9.13 | $18.26 |
| Micro servo MS18, SG90 size (23), priced as the similar MG90S | 1 | $5.49 | $5.49 |
| Limit switch KW12-3, roller lever (24) | 2 | $0.99 (est., 10-pack) | $1.98 |
| Pen, fine marker (25) | 1 | $1.06 (12-pack $12.69) | $1.06 |
| Arduino Uno R3 (26) | 1 | $27.60 | $27.60 |
| USB cable A to B (26) | 1 | $3.95 | $3.95 |
| Stepper driver BIGTREETECH TMC2209 V1.3 (27) | 2 | $7.89 | $15.78 |
| Breadboard, 830 points (28) | 1 | $5.95 | $5.95 |
| Power adapter 12V 2A (29) | 1 | $6.99 | $6.99 |
| Buck converter LM2596 (30) | 1 | $1.59 | $1.59 |
| Jumper wires M/M, 150 mm, pack of 40 (31) | 1 | $3.95 | $3.95 |
| Jumper wires F/M, 300 mm, pack of 40 (31), long leads to the carriage | 1 | $7.95 | $7.95 |
| Joystick HW-504 (33), ask the staff | 1 | $1.59 | $1.59 |
| Linear bearing LM8LUU, 45 mm long (13) | 4 | $2.12 | $8.48 |
| GT2 belt 6 mm + 20-tooth pulleys kit (17, 15) | 1.6 m | $2.85/m (kit $14.24: 5 m belt + 8 pulleys) | $4.56 |
| GT2 idler, 3 mm bore (16) | 2 | $1.84 | $3.68 |
| M3 screw and nut kit (18 to 22) | 1 kit | $6.29 (est.) | $6.29 |
| Capacitor 100µF, 25V (34) | 1 | $0.50 | $0.50 |
| DC jack to screw terminal (35) | 1 | $0.85 | $0.85 |
| **Total** |  |  | **about $152** |

So one machine costs about $152 in parts. The printed parts are 212 cm³ in CAD. With 3 walls, 20% infill, brim and supports that's about 0.2 kg of PLA.

{: .highlight }
> **Your project:** make two BoMs, one from the class parts and a separate requested BoM for items not provided in class already, including a purchasing links, units, unit cost and total (detailed instructions provided in the CoDR). Count the electronics and the filament too, and say why you need each thing you buy.

## Risk Assessment

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/risk_matrix.png' | relative_url }}"
       alt="Four by four risk matrix of likelihood against impact, with the four numbered risks and arrows to where each one lands after mitigation"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Each risk before (filled) and after (ring) its mitigation.</figcaption>
</figure>

1. We listed what could stop the project: parts, wiring, code, schedule, skills. Anything cheap to fix, like a badly fitting print or a slack belt, stayed off the list.
1. Each risk got a score, likelihood × impact, both from 1 to 4. For impact, 2 (moderate) meant a lost day, 3 (major) a lost feature and 4 (severe) no demo or a broken machine.
1. Red scores (12 to 16) needed action now and orange (6 to 9) this week. We kept an eye on yellow (3 to 4) and accepted green (1 to 2).
1. We worked on red and orange first. Mitigation moves a risk left on the matrix (less likely), and a downscope fallback moves it down (less harm) while still leaving a demo.
1. At every milestone we scored them again.

For example, R1 Software started as likely (3) × severe (4) = 12, red. Doing the simple line styles first makes it unlikely (2), and the joystick fallback limits the harm (2), so it ends up at 2 × 2 = 4.

### Risk Identification
{: .no_toc }

The two numbers are the score before and after mitigation.

- R1 Software (12, then 4). Making clean G-code from a picture was the part we were least sure of.
- R2 Schedule (9, then 4). The printer queue and the Thanksgiving break eat into build time.
- R3 Homing (8, then 2). A miswired switch or an axis running the wrong way drives the machine into its end and breaks parts.
- R4 Wiring damage (6, then 2). Unplugging a motor with 12V on, or putting 12V on a 5V pin, kills a driver or the Arduino.

### Risk Mitigation/Downscope
{: .no_toc }

Below are the risk mitigation strategies we took, and possible downscoping adjustments; design changes we could make that simplify the build but still give us a meaningful project and demo.

| Risk | Mitigation | Downscope (fallback) |
|---|---|---|
| R1 Software | Do the simple line styles first and test with the 100 mm square | Joystick only. Trace over a printed picture, record the path and let the machine copy it (JoystickDraw, hold 1.5 s) |
| R2 Schedule | Print in week 1, start the critical path on day 1, and keep 2 buffer days before the final | Shorten the drawing tests or cut scope, but keep the demo |
| R3 Homing | NC switches, test each switch by hand, and do the first homing from the middle with a hand on **Stop** | Push it to the home corner by hand, reset, **Unlock** (`$X`), then draw with UGS |
| R4 Wiring damage | Go through the checklist before 12V goes on, and set the buck converter to 5.0V before the servo goes on | Order spare drivers in week 1 |

### Upscope
{: .no_toc }

Below are possible upscoping adjustments; design changes we could make that augment the build with more advanced capabilities, if work proceeded faster than expected.

- A tool changer for drawing in 3 pen colors.
- Fill areas with hatching.
- A bigger work area with longer rods and belts.

{: .highlight }
> **Your project:** score your 3 to 5 biggest risks. Every red or orange one needs a fallback that still gets you to a demo.

## Gantt Chart & Responsibilities

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/gantt.png' | relative_url }}"
       alt="Gantt chart of the plan from Nov 20 to Dec 11 with one bar per task: red for mechanical work, blue for electronics, purple for code, dark slate for docs and tests, a green hatched 2-day buffer before the final, grey arrows for every dependency, the code tasks included, the critical path highlighted in yellow, shaded weekends and Thanksgiving, and thin lines for PDR, CDR and the final"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Our plan from Fri Nov 20, the day the PDR was handed out. The final demo is on Fri Dec 11.</figcaption>
</figure>

We listed the tasks, each with a duration and an owner, and worked out which tasks have to wait for which (you can't assemble before you print). Arrows show all these links, including those of the code tasks. The longest chain from start to final is the critical path, the shortest time the project can take. Then we added 2 buffer days before the final.

The bars are red for the mechanical work (CAD, printing, assembly), blue for the electronics, purple for code and dark slate for docs and tests. Each task's letter (M, E, C or D) goes with its color. Mechanical and electronics meet at Mount electronics (E3). We kept the buffer days, Dec 9 and 10 (green hatched), empty. There's no class on weekends or over Thanksgiving (Nov 26 and 27), so those days are shaded. The thin vertical lines are the PDR (Wed Nov 25), the CDR (Fri Dec 4) and the final.

The critical path, highlighted in yellow, is M1, M2, M3, E3, D1, D2, D3 and the buffer, 13 working days. E1, E2 and the code tasks could each slip 3 days without moving the final.

| Role | Owns |
|---|---|
| Mechanical | CAD V1 + fit test pieces, Print parts, Assemble mechanics |
| Electronics | Breadboard + motor test, Limit switches + servo, Mount electronics |
| Code | Flash GRBL, Joystick program, Image-to-G-code converter |
| Docs and tests | First homing + test square, Drawing tests + tuning, Docs + demo video |

### Updated Gantt chart
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/gantt_updated.png' | relative_url }}"
       alt="The same Gantt chart on Thu Dec 3, in the same colors: the electronics bars are longer than the thin grey bars of the plan, a Today line marks Dec 3, the yellow critical path now runs through the electronics, grey arrows from E2 show why Flash GRBL and the joystick program moved to Dec 3, and one buffer day is grey hatched as used while the other is still green"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Thin grey bars show the original plan where it changed, and colored bars show what happened and the new plan.</figcaption>
</figure>

Here is an updated Gantt chart, one week after the original was made. This is ours on Thu Dec 3, marked by the Today line.

The electronics ran 4 days late. Breadboard + motor test (E1) took 5 days instead of 2 because a stepper driver failed when a motor was unplugged with 12V on. The spare we'd ordered in week 1 (the R4 fallback) went in on Nov 30. Limit switches + servo (E2) took 2 days instead of 1. The Y limit switch read "pressed" all the time because of a broken wire.

The electronics had 3 days of slack, so Mount electronics (E3) only moved one day, from Dec 2 to Dec 3 (in progress today). D1 to D3 now run Dec 4 to 9. We used one of our two buffer days (grey hatched) and the final didn't move.

The mechanical work finished on time on Dec 1 and now has a day of slack, so the critical path runs through the electronics: E1, E2, E3, D1, D2, D3 and the buffer. Flash GRBL (C1) and the joystick program (C2) also wait for E2 (see the arrows from E2), so they moved to Dec 3 and have no slack left either.

{: .highlight }
> **Your project:** In your Gantt chart, name bars after your own parts, like "print rack-and-pinion" instead of "fabrication", and give each bar one owner. Mark the PDR, CDR and final, and leave 1 to 2 buffer days before the final. At each milestone, show the plan next to what happened, mark today and say where your buffer went.



---

## Functional Overview

At the beginning of the Final Project, in the CoDR, you're asked to provide a rough sketch of what your device will look like, annotated with key features. For the Final Build, you can provide a high-quality rendering annotated with key features that were ultimately integrated into your build. 

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/overview_annotated.png' | relative_url }}"
       alt="The drawing machine with labels on its main mechanical, electronic and code features"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The drawing machine and what each part does.</figcaption>
</figure>



## CAD & Mechanical Overview

This section details an exploded CAD diagram annotated with BoM components, and some potentially non-obvious design rationales for key parts.

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/exploded.png' | relative_url }}"
       alt="Exploded view of the whole machine with parts 01 to 25 and the pen rail (32) numbered, a legend with the quantity of each part, and a line at the bottom that lists the parts not drawn: the Arduino Uno, stepper drivers, breadboard, 12V power adapter, buck converter, jumper wires, joystick, capacitor and DC jack (26 to 31 and 33 to 35)"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Exploded view. We use these part numbers all over this page.</figcaption>
</figure>

| Part | Decision | Why |
|---|---|---|
| Rail (11, 13) | Two 8 mm steel rods on linear bearings | Stiff and smooth for little money. Printed slides would bend and wear. |
| Drive (14 to 17) | GT2 belts, 20-tooth pulleys, 1/8 step | 40 steps per mm. Belts are cheap and better suited to transmitting stepper rotary to gantry linear motion than e.g. rack-and-pinion. |
| Joints (19, 22) | Each rod end locked by one M3 screw and nut | No glue, so any part comes off for a reprint. You tension a belt by sliding a part along its rods. |
| Pen lift (09, 23) | Gravity lowers the pen and the servo only lifts it | Same pen pressure every time |
| Pen rail (32) | A separate T rail that the slider touches at two shoes only | It doesn't snag like the V4 dovetail did, and it prints lying down so the layer lines run along the slide |
| Pen clamp (10) | Yoke on two ratchet racks | Takes any pen from 6 to 21 mm without tools |


<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/key_dimensions.png' | relative_url }}"
       alt="Top view of the plotter at home with dimension lines for the 457 mm length, the 110 mm base, the 350 mm rail rods, the 350 mm arm rods and the 260 by 240 mm work area, a side view with the 140 mm height, and a close-up of the 5 mm pen lift"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Main dimensions in mm.</figcaption>
</figure>

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/pen_lift.png' | relative_url }}"
       alt="Two close-ups of the pen holder, pen up and pen down, with the arm head (07), pen slider (09), pen yoke (10), servo horn (23), pen (25) and pen rail (32) numbered and the 5 mm gap between the pen tip and the paper marked"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The pen holder with the pen up (M5, lifted 5 mm) and down (M3 S70).</figcaption>
</figure>

[//]: # Downloads: [whole machine, V5.1 with the 350 mm rods (STEP)]({{ '/assets/machine-build/Machine_V5.1_rods400.step' | relative_url }}) · [pen rail fit test pieces (STEP)]({{ '/assets/machine-build/PenSlide_V5.1_test_pieces.step' | relative_url }}).

{: .highlight }
> **Your project:** include an exploded view with part numbers, one view with the dimensions that matter, and a short table of your design decisions and why you made them.

# Assembly Instructions

This section details how to assemble and operate the machine, including all mechanical assembly steps, wiring diagrams, and software/arduino files. All these components are provided for you. 

{: .important }
> On build day, do [assembly](#assembly-instructions) steps 1 to 9 and the [wiring](#electronics). Then upload GRBL ([Arduino programs](#arduino-programs)) and go through steps 1 to 5 of [the image converter website](#the-image-converter-website).


## Mechanical Parts

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/steps_overview.png' | relative_url }}"
       alt="The nine assembly steps as thumbnails: four sub-assemblies, then five steps that put them together"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: All nine steps. Steps 1 to 4 are sub-assemblies, and steps 5 to 9 join them.</figcaption>
</figure>

### Before you start
{: .no_toc }

You'll need these tools:

- 2.5 mm hex key for all the M3 screws
- 1.5 mm hex key for the set screws of the two pulleys (2.0 mm if yours are M4)
- Small Phillips screwdriver for the servo's two small screws
- Cutters or strong scissors for the belts (optional)
- Tweezers or long-nose pliers for the nuts (optional)

**Belt adjustment**: We have pre-cut the two belts (part 17) for you. You should not have to make adjustments, but in case you do, please **let us know first**. You'll need to ensure you cut square, between two teeth. Counting teeth (2 mm each) is more accurate than measuring:

- X belt, **920 mm** (460 teeth), for step 6
- Y belt, **552 mm** (276 teeth), for step 8

Put two leads on each limit switch (terminals 1 and 2) before you mount it. Leave the far ends bare, since the Y switch's wire slot is only 2.4 mm wide and a plug won't go through.

All 11 nuts sit in slots or pockets, so you won't need a wrench. You can build steps 1 to 4 in any order, or split them up.

### 1. Carriage: Bearings and Stops
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/step1.png' | relative_url }}"
       alt="Step 1: the carriage with a bearing clicked into each lower ring from the spring-finger end, and a bearing and then a stop slid into each upper ring from the front"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The carriage with its four bearings and two stops.</figcaption>
</figure>

1. Hold the carriage in your hand. Don't press it down on the table.
1. Push a bearing into each lower ring from the spring-finger end until it clicks.
1. Slide a bearing into each upper ring from the front until it stops.
1. Slide a stop in front of each upper bearing and press its peg down.

Each lower bearing should now sit behind two hooks, and each stop should lie flat with its peg in the hole.

### 2. Motor Plate Unit
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/step2.png' | relative_url }}"
       alt="Step 2: the motor plate upside down on the motor on the bench, with the idler, pulley and limit switch added"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The motor plate on the Y motor, with the idler, pulley and Y limit switch.</figcaption>
</figure>

1. Stand the motor with its shaft up and lay the plate on it, pegs up.
1. Fix it with four M3 × 8, with the motor cable toward the plate's small tab.
1. Put the idler on the round boss, push an M3 × 20 through it and fit the nut in the pocket underneath.
1. Slide the pulley on rim first, with its teeth level with the idler groove, and tighten it.
1. Thread the switch leads through the slot first, then click the switch onto the pegs with the lever past the edge.

The idler should spin freely.

### 3. The Two X Ends
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/step3.png' | relative_url }}"
       alt="Step 3: the X motor end and the X idler end seen from the rail side, with the motor, pulley, switch and idler fitted and the four rod-lock screws started"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The X motor end and the X idler end, seen from the rail side.</figcaption>
</figure>

1. On the motor end, put the motor on the face without ribs and fix it with four M3 × 8 from the rib side.
1. Put the pulley on collar first, with the collar against the plate and the teeth under the notch. Tighten it.
1. Feed the switch leads through first, then push the switch into the pocket in the beam with the lever sticking out.
1. On the idler end, put the idler in the slot and push an M3 × 25 through from the side with the round recess. The nut goes on the other side.
1. On both ends, push a nut into each side slot and start each M3 × 10 by two turns.

The motor cable has to point up or outward, never down or toward the beam. Only snug up the idler screw so the idler can still spin.

### 4. Arm Head: Nuts, Servo, Rods
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/step4.png' | relative_url }}"
       alt="Step 4: the arm head with its nuts and the servo fitted, and both 350 mm arm rods pushed into the back of the head"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The arm head with the servo and both arm rods.</figcaption>
</figure>

1. Drop a nut down each nut slot of the head and start both M3 × 10.
1. Lower the servo into the pocket with the shaft to the front and the cable in the gap.
1. Fix the outer servo tab with the small screw and lead the cable straight up.
1. Push two 350 mm rods into the back sockets until they stop, and tighten. All four rods are the same, so any two will do.
1. Leave the single-arm servo horn and its tiny screw in the bag. They go on later.

The rods shouldn't pull out, and the servo shaft should sit near the middle of the head.

### 5. Rail: Rods, Carriage, X Ends
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/step5.png' | relative_url }}"
       alt="Step 5: the two rail rods in the X motor end, the carriage slid on with its spring-finger end last, and the X idler end pushed on last"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The carriage on the rail rods between the two X ends.</figcaption>
</figure>

1. Push the other two 350 mm rods fully into the motor end and tighten its two side screws.
1. Slide the carriage on, spring-finger end last, with the bearing stops and the screw boss on the side of the motor body.
1. Push the idler end onto the rods until it stops and leave its screws loose.
1. Press both ends flat on the table and slide the carriage from end to end.

The carriage should glide the whole way.

### 6. X Belt
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/step6.png' | relative_url }}"
       alt="Step 6: each end of the X belt pressed into a belt anchor, the anchors clicked up into the keel under the carriage, and the idler end pulled outward to tension the belt"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The X belt ends pressed into their anchors under the carriage.</figcaption>
</figure>

1. Stand the two anchors hook to hook, hooks up and grooves toward you. That gives you the left and the right one.
1. Press one belt end into the left anchor, round the U with the teeth inward.
1. Tip the rail back and push this anchor up into the left keel pocket until it clicks.
1. Thread the belt round the idler and the pulley, and fit the right anchor the same way.
1. With the rail flat, pull the idler end outward until the belt is taut, then tighten its screws.

Before each click, check that the cut end sits flush in the bottom leg, the groove faces the pen side and the loose belt is below the anchor. A clicked anchor is hard to get out again.

### 7. Arm Through the Carriage, Tail
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/step7.png' | relative_url }}"
       alt="Step 7: the arm rods pushed through the upper bearings of the carriage from the pen side, and the arm tail fitted on the rail side"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The arm rods through the upper bearings, with the tail on the rail side.</figcaption>
</figure>

1. Look into both upper rings and check that each stop lies flat with its peg in the hole.
1. With the servo on top, push the two rods through the upper bearings from the pen side.
1. Drop a nut into each top slot of the tail and start both M3 × 10.
1. Push the tail onto the rod ends, raised block up, until it stops.
1. Tighten the tail screws lightly and slide the arm in and out.

The arm should slide with a light push. The servo and the tail's raised block both end up on the X motor side.

### 8. Motor Plate and Y Belt
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/step8.png' | relative_url }}"
       alt="Step 8: a nut in the carriage boss, one end of the Y belt pressed into the arm head, the motor plate lowered onto the belt loop, and the other belt end pressed into the arm tail"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The Y belt from the arm head, round the motor plate, to the arm tail.</figcaption>
</figure>

1. Pull the arm out and push a nut flat, corner first, into the boss slot.
1. Press one belt end into the head channel, round the U with the teeth inward and the end beside the servo.
1. Loop the belt behind the plate's pulley and in front of its idler.
1. Lower the plate about 3 mm forward of where it sits, slide it back under the arch and fit its screw.
1. Press the other end into the tail channel, teeth outward. Pull the tail back to tension the belt and tighten it.

The plate should lie flat on both walls, with the belt in the wall slot and clear of every screw head.

### 9. Pen Holder
{: .no_toc }

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/step9.png' | relative_url }}"
       alt="Step 9: the pen rail screwed to the front of the arm head, the pen slider slid on from the top, and the yoke and pen added, still without the servo horn"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The pen rail, slider, yoke and pen on the arm head, still without the servo horn.</figcaption>
</figure>

1. Screw the pen rail to the front of the head, foot down, with two M3 × 10. There are no nuts. The screws cut their own thread, so stop when they're snug.
1. Slide the pen slider down onto the rail from the top.
1. Squeeze the yoke's two tabs and set it between the racks, pad toward the V.
1. Stand the pen in the V with its tip a finger's width above the table and click the yoke in.

The slider should drop freely when you lift it and let go. Keep the pen off the table for now, or homing will drag it.

### Servo horn (later)
{: .no_toc #later-servo-horn }

You fit the horn in step 4 of [the image converter website](#the-image-converter-website), once the servo has power. You need the single-arm servo horn and its tiny screw (part **23**, in the servo bag).

1. Press **Pen up** (M5) and wait until the servo has turned and holds.
1. Lift the pen slider off the pen rail.
1. Press the horn on so it points at the pen rail with its tip about 35 degrees up (see the step 9 figure).
1. Fix the horn with its tiny screw and lower the slider back onto the rail.

With the pen up (M5) the slider should rest on the horn, about 5 mm higher. With the pen down (M3 S70) the horn is level and 3 mm below the ledge.

## Electronics

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/wiring.png' | relative_url }}"
       alt="Wiring diagram with the Arduino Uno, two TMC2209 stepper drivers, two stepper motors, the servo, two limit switches, the joystick, the 12V adapter, the buck converter and the 100µF capacitor on a breadboard"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The real parts wired on a breadboard.</figcaption>
</figure>

| Arduino Uno (26) | Goes to |
|---|---|
| D2, D5 | X driver STEP, DIR |
| D3, D6 | Y driver STEP, DIR |
| D8 | EN of both drivers (LOW = motors on) |
| D9, D10 | X and Y limit switch (24), terminal 2 (terminal 1 to ground) |
| D11 | Servo (23) signal (orange) |
| A4, A5, D12 | Joystick (33) VRx, VRy, SW (JoystickDraw only) |
| 5V | VIO of both drivers, joystick +5V |
| A0, A1, A2 | Leave empty (GRBL uses them) |

1. On each stepper driver (27), connect the motor (14) leads Black to A1, Blue to A2, Green to B1 and Red to B2.
1. On the servo (23), the brown wire goes to ground, red to the 5V of the buck converter (30), never the Arduino's 5V, and orange to D11.
1. Plug the 12V adapter (29) into the DC jack (35) and wire the jack's two screw terminals to the 12V and ground rails (+ to 12V). Feed VM on both drivers and the buck converter from 12V, with the 100µF capacitor (34) across 12V and ground near the drivers (+ leg on 12V). Power the Arduino from USB and join all the grounds.
1. The Y motor and Y switch ride on the carriage and the servo rides on the arm, so their cables move. Leave a loop long enough for the carriage to reach both ends of the rail, and give the servo cable extra so the arm can also slide all the way out.

{: .important }
> **Before you plug in 12V**, check that all grounds are joined, no 12V wire is on a 5V row, both motors are plugged in and the servo is unplugged. Set the buck converter to 5.0V with a multimeter before you connect the servo. Never plug or unplug a motor while 12V is on.

We added up the worst-case current of each load and picked an adapter with room to spare.

{: style="break-inside: avoid;" }
| Load | Supply | Current (estimate) |
|---|---|---|
| 2 stepper motors with drivers | 12V | 2 × 0.3 A |
| Servo, through the buck converter | 12V | up to 0.35 A for a moment (0.7 A at 5V) |
| Arduino, driver logic, joystick | USB 5V | 0.05 A |
| **Total from the 12V adapter** | | **about 1 A, so a 12V 2A adapter is enough** |

{: .highlight }
> **Your project:** show every pin in your wiring diagram, and use a current table to back up your choice of power supply.


## Arduino sketches & Software Overview

Our drawing machine has two modes of operation.

**Mode 1**: Draw from Image Upload. 
- This lets you upload an image to a webtool that converts it to Gcode that the Arduino uses for automatic drawing of that image.
- This uses the [grbl_pen.zip]({{ '/assets/files/machine-build/grbl_pen.zip' | relative_url }}) Arduino sketch and the [Image Converter page]({{ '/assets/files/machine-build/Image_to_Gcode_tool/index.html' | relative_url }})

**Mode 2**: Draw with Joystick.
- This lets you use the joystick to manually draw an image, which you can then 'replay'; the Arduino records the joystick commands and can automatically execute the same drawing.
- This uses only the [JoystickDraw.zip]({{ '/assets/files/machine-build/JoystickDraw.zip' | relative_url }}) Arduino sketch.

To switch modes, remember that you must upload the new corresponding sketch. See the overview in the table below.

| Mode | Draw from Image Upload | Draw with Joystick |
| Files needed | GRBL + Image converter page | JoystickDraw |
|---|---|---|
| What it does | Turns a picture into G-code and draws it | You drive the pen with a joystick, and it can redraw what you drew |
| Upload | Add [grbl_pen.zip]({{ '/assets/files/machine-build/grbl_pen.zip' | relative_url }}) with **Sketch > Include Library > Add .ZIP Library**, open **File > Examples > grbl_pen > grblPenUpload** and press **Upload** | Open `JoystickDraw.ino` from [JoystickDraw.zip]({{ '/assets/files/machine-build/JoystickDraw.zip' | relative_url }}) and press **Upload** |
| Laptop side | [Converter page]({{ '/assets/files/machine-build/Image_to_Gcode_tool/index.html' | relative_url }}) in Chrome or Edge. Universal G-code Sender (UGS) for saved `.gcode` files and typed commands (`M5`, `G0 X200`) | Serial Monitor at 115200 baud (optional) |

**Troubleshooting**: Note that if **File > Examples** only shows `grblUpload` and `grblWrite_BuildInfo`, you have the original GRBL library, so add `grbl_pen.zip` first. To check the upload, open the Serial Monitor at 115200 baud and look for a line starting with `[MSG:grbl_pen`. Close the Serial Monitor before you connect the converter page.

## The Image Converter website

The [Image Converter page]({{ '/assets/files/machine-build/Image_to_Gcode_tool/index.html' | relative_url }}) is one HTML file. In Chrome or Edge on a laptop it makes the G-code and sends it to the machine over USB. In Safari or on a phone you can only download the G-code.

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/pipeline.png' | relative_url }}"
       alt="Five panels from a picture to a drawing: the picture, its lines, the G-code, sending over USB, and the machine drawing"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: How a picture turns into a drawing.</figcaption>
</figure>

1. Upload GRBL. In the converter page, press **Connect to machine** and pick the Arduino's port. It says "Locked" until you home, which is normal.
1. Test the switches by pressing each lever by hand. The page should show "pressed". If it shows "pressed" all the time, a wire is loose.
1. Move the carriage and arm to the middle by hand, plug in 12V and press **Home**, with a hand ready on **Stop**. The arm should pull in and the carriage should move toward the X motor. If an axis goes the wrong way, press **Stop**, then **Flip X direction** or **Flip Y direction** (under **Machine setup and tests**) and **Home** again.
1. Calibrate the pen lift. You only do this once. Plug in the servo (buck converter at 5.0V) and tape down a sheet with one corner slightly outside the pen tip. Press **Pen up** and fit the servo horn ([Servo horn](#later-servo-horn)). Press **Load pen**, squeeze the yoke's tabs to open it, let the pen drop onto the paper, click the yoke shut and press **Pen up**.
1. Press **Draw 100 mm test square** (under **Machine setup and tests**) and measure it. Each side should be 100 mm. Then load a picture, pick a line style and press **Draw**.

The whole 260 × 240 mm work area fits on an A3 or Tabloid (11 × 17 in) sheet with the long side along the rail. Letter and A4 are too narrow, but you can draw smaller on them: the converter scales the picture to the **Drawing width** you set.

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/homing.gif' | relative_url }}"
       alt="Animation: the carriage and arm run to the home corner until both limit switches are pressed"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Homing. Both axes run to their switches, and that corner becomes X0 Y0.</figcaption>
</figure>

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/converter.png' | relative_url }}"
       alt="Screenshot of the converter page with a line drawing of a house and sun turned into pen strokes inside the machine's work area, and the machine connected, homed and ready to draw"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: The converter page, connected and homed, with a picture ready to draw.</figcaption>
</figure>

## Joystick control

{: style="break-inside: avoid;" }
1. Upload JoystickDraw and click the joystick to home.
1. Push the stick to move. The further you push, the faster it goes, up to 40 mm/s. Click for pen down or pen up.
1. Hold the button for 1.5 s to redraw your path (up to 300 corners). The machine goes home when it's done, and a click stops it. The Serial Monitor prints the path as G-code, so you can save it as a `.gcode` file and draw it again with GRBL and UGS.
1. If an axis homes the wrong way, unplug 12V, set `FLIP_X` or `FLIP_Y` to `true` at the top of the sketch and upload again. If the stick feels mirrored, set `STICK_FLIP_X` or `STICK_FLIP_Y`.

<details markdown="block">
  <summary>
    Troubleshooting
  </summary>
  {: .text-delta }

| What you see | Likely cause | Fix |
|---|---|---|
| "Locked" or `error:9` | Not homed yet | Press **Home** |
| `ALARM:9` after Home | An axis ran away from its switch, there's no 12V, or the lever never gets pressed | Flip that axis, and check 12V and the switch position |
| `ALARM:8` after Home | A switch reads pressed all the time | Wire terminal 1 to ground and terminal 2 to the pin |
| The pen doesn't lift, or hangs above the paper at Pen down | The horn is one spline tooth off | Refit the horn one tooth up or down, or raise **Pen down value (S)** (converter page, under **More settings**) |
| A motor buzzes but doesn't turn | Coil wires mixed up | Black A1, Blue A2, Green B1, Red B2 |
| The drawing shifts part-way | Slack belt, loose pulley or snagged cable | Tension the belt and tighten the pulley set screws |
| The Arduino resets when the pen moves | Servo powered from the Arduino | Power the servo from the buck converter |
| JoystickDraw says "Joystick not centred" | VRx/VRy not on A4/A5, or no 5V | Check the joystick wires and press reset |

</details>

## Step by step: the two ways to draw

The machine has two modes. Each mode is a different program on the Arduino, and the wiring is the same for both. To switch modes, upload the other program. Everything you need is written or linked on this page.

### Before you start
{: .no_toc }

1. Plug the Arduino into the laptop with the USB cable. Leave the 12V adapter unplugged while you upload.
1. In the Arduino IDE, pick **Tools > Board > Arduino AVR Boards > Arduino Uno**, then pick the Arduino's port under **Tools > Port** (`COM3` or similar on Windows, `/dev/cu.usbmodem...` on Mac).

### Mode 1: Draw from Image Upload (GRBL and the converter page)
{: .no_toc }

**1. Download the library.** Download [grbl_pen.zip]({{ '/assets/files/machine-build/grbl_pen.zip' | relative_url }}). Don't unzip it.

**2. Install the library.** In the Arduino IDE, choose **Sketch > Include Library > Add .ZIP Library** and pick `grbl_pen.zip`. You only do this once per laptop.

**3. Upload the example code.** Choose **File > Examples > grbl_pen > grblPenUpload** and press **Upload**. A "Low memory available" warning is normal. To check it worked, open **Tools > Serial Monitor** at 115200 baud. You should see `Grbl 1.1h ['$' for help]` and `[MSG:grbl_pen: ...]`. Then close the Serial Monitor, because only one app can use the USB port at a time.

**4. Open the converter page.** It is hosted on this site, so there is nothing to install. Open the [converter page]({{ '/assets/files/machine-build/Image_to_Gcode_tool/index.html' | relative_url }}) in Chrome or Edge on a laptop. Safari, Firefox and phones can't talk to the Arduino. There you can only download the G-code.

**5. Draw.** The page walks you through five numbered steps.

1. At the top, keep **Pen lift + homing** selected.
1. **1 Picture:** choose a JPG or PNG, drop it on the box, or paste it.
1. **2 Style:** **Outline** draws clean lines. Use **Follow drawn lines** for a line drawing and **Trace around shapes** for a photo or filled shapes. **Squiggle rows** and **Scribble** shade the picture instead.
1. **3 Size and position:** set the **Drawing width** and how far **From home** the drawing starts. It must fit inside the 260 × 240 mm work area.
1. **4 Preview:** check the lines and the drawing time.
1. **5 Draw on the machine:** plug in 12V, press **Connect to machine** and pick the Arduino's port. Press **Home** with a hand ready on **Stop**. Tape down the paper, press **Load pen**, fit the pen, press **Pen up**, then press **Draw**. **Pause** and **Stop** work at any time.

The first time you use a machine, also do the checks in [The image converter website](#the-image-converter-website) (switches, motor directions, pen lift and the 100 mm test square).

### Mode 2: Draw with Joystick (JoystickDraw)
{: .no_toc }

**1. Download the sketch.** Download [JoystickDraw.zip]({{ '/assets/files/machine-build/JoystickDraw.zip' | relative_url }}) and unzip it. Keep the `JoystickDraw` folder with `JoystickDraw.ino` inside it, because the Arduino IDE needs the folder and the file to have the same name.

**2. Upload it.** Open `JoystickDraw.ino` (**File > Open**) and press **Upload**. It needs no extra library.

**3. Draw.**

1. Plug in 12V and click the joystick. The machine homes.
1. Push the stick to move the pen, and click to put the pen down or lift it.
1. Hold the button for 1.5 s and the machine redraws your path on its own.

See [Joystick control](#joystick-control) for the details. To go back to Mode 1, upload **grblPenUpload** again. The library stays installed.
