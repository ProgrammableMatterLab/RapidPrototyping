---
title: Week 1
nav_exclude: true
description: >-
    Week 1 activities
---

# Week 1 - Introduction
{:.no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Readings & Preparation

There are no readings due before the first lecture in week 1. 

## Lecture

*Coming soon*{: .text-red-300 }


### Co-design of a part geometry, electronics, and manufacturing/assembly process

Building physical products don't just involve designing for their intended functionality; they must also account for their manufacturing and assembly. Consider a computer mouse. It has some mechanical function (it should fit in your hand, it should be light, etc) and some electronic function (register button clicks, connect to a PC, etc.) These mechanical and electronic features must be co-designed; at the very least, the electronics should fit within the mechanical enclosure. But both features must also be designed to to support manufacturing and assembly. Many of these features become visible when we disassemble a computer mouse in our teardown assignment. We'll notice geometric features like ribs, bosses, grooves, fasteners, openings, compliant features, and connectors, and reason about how these connect to requirements for structural stiffness, alignment, tolerance, assembly sequence, user interaction, and access to internal components.

#### Manufacturing Related Features
Below is a list of manufacturing-related features to look out for. The computer mice we'll look at are injection molded, and will be designed with _Draft angle_ in mind. The designs we make in this class, for laser cutting and 3D printing, won't need to account for draft angle but will have their own unique and related constraints, which we'll introduce later. All the other features will be common to all these manufacturing workflows.
1. **Draft angle**: slight taper added to vertical walls that helps an injection-molded molded part release from its mold. This constraint is specific to injection molding, and we'll learn other constraints specific to laser cutting and 3D printing later.
1. **Bosses and grooves**: raised features used to locate, support, or fasten parts (like the PCB).
1. **Parting line**: where two assembled parts meet; often visible as a seam.
1. **Wall thickness**: affects strength, weight, and molding quality. Too thick and we waste material/cost; too thin and wall may break/warp.
1. **Ribs**: thin reinforcing features that increase wall stiffness to avoid making a wall too thick.
1. **Tolerances**: allowable variation in dimensions needed for parts to fit and function.
1. **Snap fit**: a compliant feature that temporarily deforms and locks parts together.
1. **Fasteners**: hardware such as screws, bolts, nuts, or threaded inserts used to join parts with.
1. **Assembly access**: openings or separable parts that allow components (like the PCB) to be inserted, connected, or serviced. Notice the mouse needs to assembled from disjoint parts so the PCB can be inserted and assembled. 
1. **Part access**: Unlike a 1-time assembly access, these are openings that allow components (like the USB wire, mouse wheel, and sensor) to permanently connect to or interface with the outside world.  
1. **Features for user Input transfer**: Features designed specifically for user interaction and ergonomics. Our computer mouse is sized for an average adult hand. It also provides tactile feedback - a _click_ - to tell the user when a button press is registered (consider and check yourself: does the _click_ come from the injection-molded part _or_ from the electronic button?)  

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

*This week, laser cutter training in groups of 5 and and mouse dis-assembly. Doing Laser training now for time, but won't use until next week. Laser cutting training takes approximately 75 minutes. 10 students can be trained at a time (5 students per laser cutter). Group A (10 students): Start with laser cutter training. Then do Mouse teardown. Group B (10 students): Start with Mouse teardown. Complete laser cutter training when Group A finishes, then return to mouse teardown if time.*{: .text-red-300 }

### Laser Cutter training

Training & Safety: you will attend a ~75 minute training will Mill staff during the lab. This will cover processing your design files (exported as .dxf from Onshape) in Illustrator and operating the laser. They will also cover safety protocols and fire hazards, and there will always be a Mill staff present who you can call on for help.

See [Week 2]({{ '/docs/week2/' | relative_url }}) for more information about the laser cutters.

### Mouse Teardown

You will disassemble and document a computer mouse provided by us. Your assignment will be to produce a teardown figure of your mouse, a bill of materials, and identify manufacturing features. Start during the lab, and finish on your own time.


#### Assignment learning objectives
The goals of this assignment are to:
1. Become familiar with how a device consisting of mechanical components, an enclosure, and electronics are co-designed.
1. Identify how constraints from the manufacturing process affect how a device is designed and assembled.
1. Observe different assembly mechanisms (snapfit and screws), and understand that physical assembly requires tight dimensional constraints in CAD (Readings will introduce dimensioning in CAD) 
1. Produce visually clear documentation of a physical assembly.


#### What to do in the lab
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
1. *TODO: Google Site account and make Martin's email admin*{: .text-red-300 }
1. *TODO: Fill in interest form and include Google site URL*{: .text-red-300 }
1. *TODO: TASK: Mouse Teardown documentation on Google Site*{: .text-red-300 }
1. Reading: Complete the [Week 2 Readings & Preparation]({{ '/docs/week2/' | relative_url }}).


### Task Deliverables: Mouse Teardown

There are 3 deliverables for the Mouse teardown: a Teardown figure, a BOM, and a feature analysis. 

At a minimum, you should complete:
1. An annotated teardown figure with clearly distinguishable parts.
1. An associated BOM.
1. A feature analysis table with at least 3 rows added to the example below.

As a bonus, you can try:
1. Remove the background from individual images to produce a crisp, clean teardown figure.
1. Add more feature rows to your feature analysis table.
1. Comment on how these features, for a mass-manufactured mouse, might hold or be modified for single-unit prototypes we make using 3D printing and laser cutting

*Document your work under a Week 1 heading on your Google Site (PROVIDE Google Site documentation EXAMPLE)*{: .text-red-300 }


#### 1. Mouse teardown figure
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

#### 2. Bill of Materials (BOM) 
A table listing the numbered list of the parts in the teardown image.

Table 1: Bill of Materials

| Item number| Item name (guess is ok) |
|---|---|
| 1 | Screw |
| 2 | Scroll Wheel |
| ... | Complete this | 
| N | Complete this | 


#### 3. Feature Analysis
A table that identifies evidence of co-design between the enclosure, electronics, and manufacturing/assembly process. 

Try to identify features that locate or align parts; constrain motion; transfer user input; provide access for cables, sensors, or buttons; stiffen thin walls; enable fastening or rapid assembly; allow the product to be opened, closed, or serviced. See the Manufacturing Related Features list above for inspiration. Fill in at least 3 more rows to the example table below.

Table 2: Feature Analysis Table

| Observed feature | Function | Likely design or assembly constraint | Evidence |
|---|---|---|---|
| Two-piece enclosure | Allows access to internal components | Electronics must be installed and serviced | Housing separates along a seam |
| Grooves plus screws | Aligns and secures the enclosure halves | Parts need both positional alignment and clamping | Grooves constrain motion; screw secures assembly |
| Complete this | Complete this | Complete this | Complete this |
| Complete this | Complete this | Complete this | Complete this |
| Complete this | Complete this | Complete this | Complete this |



