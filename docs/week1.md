---
title: Week 1
nav_order: 3
nav_exclude: false
description: >-
    Week 1 activities
---

# Week 1 - Introduction
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

There are no readings due before the first lecture in week 1. 

## Lecture

In this lecture, we will:
1. Introduce Rapid Prototyping as a course topic
1. Cover course logistics
1. Introduce this week's topic on Design for Manufacturing
1. Introduce the Week 1 Lab & assignment

[//]: # After the lecture, the slides will be posted *HERE.*{: .text-red-300 }

## Hardware & Software


### Hardware

#### Laser cutters
See [Week 2]({{ '/docs/week2/' | relative_url }}) for more information about the laser cutters.

#### Computer mouse
A computer mouse will be provided for you for disassembly.

#### Mini screw driver 
A mini screw driver (SL3.2) will be provided for you for the mouse disassembly.

### Software

#### Powerpoint
For the mouse teardown assignment, we recommend using Powerpoint for formatting images to remove background.


## Lab

This lab will have two activities: 
1. laser cutter training, to prepare us for next week's laser cutting, and 
1. a computer mouse teardown, which is the first step of this week's assignment. 

Laser cutting training should take around 60 minutes, and 5 students can be trained per laser cutter at a time. Whenever you're not in the training, please proceed with the Mouse teardown.

### Laser Cutter training

The laser cutter training will be conducted by Mill staff. This will cover processing your design files (exported as .dxf from Onshape) in Illustrator and operating the laser. They will also cover safety protocols and fire hazards, and there will always be a Mill staff present who you can call on for help.

See [Week 2]({{ '/docs/week2/' | relative_url }}) for more information about the laser cutters.

### Mouse Teardown

You will disassemble and document a computer mouse provided by us. Your **assignment** will be to produce a teardown figure of your mouse, a bill of materials, and identify manufacturing features. Start during the lab, and finish on your own time.

**You will need to submit the assignment individually, but feel free to work in pairs during lab.**




#### What to do in the lab
First, read the Assignment **Task** description below. Then proceed with the below:
1. Connect the mouse to your laptop to confirm it works. 
1. Using the screwdriver, probe the identification sticker on the bottom of the mouse for a soft spot. Pierce the sticker here, and unscrew the screw holding it together. 
1. On the back of the mouse (where your palm rests), drive the screwdriver into the seam between the upper and lower parts and turn the screwdriver to wedge it open.
1. Disassemble all the components, being careful not to lose anything. 
1. See the **Assignment** for what to do next. To create the teardown image, you'll want to take photos of all the parts in two orientations: 
    1. A birds-eye view (For individual part images)
    1. An orthographic view (with all parts in the orientation that they were assembled in) 
1. Before you leave the lab, we recommend you re-assemble the mouse and connect to your laptop to confirm it still works. You can store the screw separately if you want to disassemble it later without a screwdriver. Keep the mouse and bring it with you to each class.


## Assignments

<!-- 1. Complete the [Week 2 Readings](week2.md).  -->
1. **Google Site:** Create a Google Site and make Martin the owner. See the [Portfolio website]({{ '/docs/resources/portfolio-site/' | relative_url }}) page for instructions.
1. **Survey:** Complete the [Pre-course Survey](https://docs.google.com/forms/d/e/1FAIpQLSemDkMrhTDm3Ho1eRpTx3yTXziqjfriJrNQkwkUZ57E3SHFig/viewform?usp=dialog). Note we will collect your published Google Site URL here.
1. **Task:** Complete this week's Task and publish your documentation on your Google Site.
1. **Reading:** Complete the [Week 2 Readings & Preparation]({{ '/docs/week2/' | relative_url }}).



### Task: Mouse Teardown

#### Task learning objectives
The goals of this assignment are to:
1. Become familiar with how a device consisting of mechanical components, an enclosure, and electronics are co-designed.
1. Identify how constraints from the manufacturing process affect how a device is designed and assembled.
1. Observe different assembly mechanisms (snapfit and screws), and understand that physical assembly requires tight dimensional constraints in CAD (Readings will introduce dimensioning in CAD) 
1. Produce visually clear documentation of a physical assembly.

#### Task deliverables
There are 3 deliverables for the Mouse teardown: a Teardown figure, a BOM, and a feature analysis. 

At a minimum, you should complete:
1. An annotated teardown figure with clearly distinguishable parts.
1. An associated BOM.
1. A feature analysis table with at least 3 rows added to the example below.

For full credit, you can try:
1. Remove the background from individual images to produce a crisp, clean teardown figure.
1. Add more feature rows to your feature analysis table.
1. Comment on how these features, for a mass-manufactured mouse, might hold or be modified for single-unit prototypes we make using 3D printing and laser cutting

To submit your assignment, document it under a Week 1 heading on your Google Site, then publish it. The [Portfolio website]({{ '/docs/resources/portfolio-site/' | relative_url }}) page includes a draft [example of a Week 1 submission](https://sites.google.com/view/aa598-aut26-martin-nisser/assignments/week-1).


##### Deliverable 1. Mouse teardown figure
A figure with labelled and numbered parts in individual and assembled configurations.
1. For label names, guess at either its name or its function.
1. Include explosion lines showing how the parts go together
1. We recommend using Powerpoint to create this image. However, you may use any software you like (Figma, Illustrator, PMS Paint, etc).
    1. You can use a blank canvas (for example, a blank Powerpoint slide) or populate your teardown on [this template]({{ '/assets/images/W1_mouse_explosion_template.pdf' | relative_url }}).
    1. You should format your images to remove background clutter. See _Removing background from images_ below.

<figure style="text-align: center;">
  <img src="{{ '/assets/images/W1_mouse_explosion_example.png' | relative_url }}"
       alt="Mouse explosion example"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure 1: Mouse teardown (not our mouse model). (Left) Individual parts. (Right) Exploded view.</figcaption>
</figure>

{: .highlight }
> **Removing background from images**
>
> Presentation quality is an important skill in rapid prototyping. For a clean Teardown document like the example shown, you should remove the background from your images. This doesn't need to be perfect, but spend a few minutes to make things presentable. UW students have access to an AI-based background remover through [Adobe Express](https://www.adobe.com/express/feature/image/remove-background) which you could try. However, we recommend using a clipping mask in Powerpoint for explicit control over what to remove:
> 1. Insert your image on a Powerpoint slide.
> 1. Draw a shape to use as a clipping mask. From the home tab, go to Drawing->Freeform:Shape (Or go to Insert->Drawing->Freeform:Shape)
> 1. Select the image first, then hold the Shift key and select the shape. Go to the Shape Format tab. 
>     1. To keep the image region inside the shape, click Merge Shapes and choose Intersect.
>     1. To keep the image region outside the shape, click Merge Shapes and choose Subtract.

##### Deliverable 2. Bill of Materials (BOM) 
A table listing the numbered list of the parts in the teardown image.

Table 1: Bill of Materials

| Item number| Item name (guess is ok) |
|---|---|
| 1 | Screw |
| 2 | Scroll Wheel |
| ... | Complete this | 
| N | Complete this | 


##### Deliverable 3. Feature Analysis
A table that identifies evidence of co-design between the enclosure, electronics, and manufacturing/assembly process. 

Try to identify features that locate or align parts; constrain motion; transfer user input; provide access for cables, sensors, or buttons; stiffen thin walls; enable fastening or rapid assembly; allow the product to be opened, closed, or serviced. See the Manufacturing Related Features list on the [Design for Manufacturing]({{ '/docs/resources/dfm/' | relative_url }}) page for inspiration. Fill in at least 3 more rows to the example table below.

Table 2: Feature Analysis Table

| Observed feature | Function | Likely design or assembly constraint | Evidence |
|---|---|---|---|
| Two-piece enclosure | Allows access to internal components | Electronics must be installed and serviced | Housing separates along a seam |
| Grooves plus screws | Aligns and secures the enclosure halves | Parts need both positional alignment and clamping | Grooves constrain motion; screw secures assembly |
| Complete this | Complete this | Complete this | Complete this |
| Complete this | Complete this | Complete this | Complete this |
| Complete this | Complete this | Complete this | Complete this |



