---
layout: page
title: Machine Building template
parent: Resources
nav_exclude: true
description: >-
    Machine Building template
---

# Machine Building template
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

# Machine Building Instructions

For the Machine Building lab, please see the documentation below for an account of how our 2D Drawing Machine is operated, and how to assemble it.

[Shareef: this is a linked website](https://sites.google.com/view/aa598-aut26-martin-nisser)


<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/IMAGE_NAME.png' | relative_url }}"
       alt="image description"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Shareef this is the figure formatting.</figcaption>
</figure>

Shareef: make numbered lists like this:
1. lorem ipsum.
1. lorem ipsum.

## Final Demo

_Gif of machine plotting UW logo_

_Gif of generating UW gcode with software_

_Video of machine controlled by joystick_

## Design and Assembly

### CAD

Sketches, sub-assemblies, key dimensioned CAD

### Electronics / Code

Electronics schematics and breaboarded circuits; estimates of maximum current draw; Arduino PseudoCode 

### Assembly instructions etc



## Software 

### Gcode generation

### Joystick control

---

# Additional Documentation for 2D Drawing Machine

## Design Objective

### Initial Sketch

<figure style="text-align: center;">
  <img src="{{ '/assets/images/machine-build/draw-machine-sketch.png' | relative_url }}"
       alt="image description"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure: Brainstorm sketch. Students' sketches should be annotated with key features; e.g. stepper motor, pen holder</figcaption>
</figure>

### Problem or Opportunity
What problem, need, frustration, or creative opportunity does the project address?

### Proposed Solution
- What physical device are you proposing, and how does it address the problem or opportunity? 
- Does it involve technical depth - does it incorporate all major class skills, or even go beyond them?
- Explain who this device is for, and in what context (when and where).

## Functional Requirements

The functional requirements of the 2D drawing machine are: 
1. Accepts an image upload from user as png/jpg
1. Parses & thresholds image to produce G-code as a drawable, line-based representation 
1. Physically draws pictures using a pen in 1 color
1. Allow joystick control as well as automatic control of the pen end effector
1. Does not drop pen; does not damage itself during operation

## Performance Requirements 

The performance requirements of the 2D drawing machine are: 
1. toolhead travel at 100mm/s in X-Y plane 
1. retract/extend pen in Z within 1s; 
1. draw images that are visually identical to parsed input image for 90% of attempts
1. etc.

## System Block Diagram 

Group blocks by physical component or functional area; show key information/Actuation flow


## Bill of Materials (BoM)

If not already in the documentation above

## Risk Assessment

### Risk identification 
Identify key risk(s): what part of the project are you most uncertain about successfully implementing, or what is most likely to fail? 
- software part

### Risk Mitigation/Downscope 
What will you do to mitigate these risks, and what is a fallback plan you can implement to still have your project succeed if the risk-prone part fails?
- Just joystick control

### Upscope 
If the risks prove mitigated and the original project scope proves easier to implement than expected, what extended features or capabilities will you augment the project with?  
- toolhead changer for drawing with 3 pen colors



## Gantt Chart & Responsibilities

Gantt Chart with key milestones for design/fabrication, electronics, code, and testing. It should span the 3 weeks between the PDR being issued and the Presentation Day. It should include entries that are specific to your project (e.g. "fabricate rack-and-pinion mechanism" not only "design and fabrication").
