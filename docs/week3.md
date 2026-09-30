---
title: Week 3
nav_order: 5
nav_exclude: true
description: >-
    Week 3 activities
---

# Week 3 - 3D Design & 3D Printing
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

This week's readings center on 3D design in Onshape, converting designs into machine instructions using Slicers, and fabrication using 3D printers.

### Tutorials / Readings

1. See our [Visual guide to creating 3D shapes](https://docs.google.com/presentation/d/12-XNApXlb_OBX1qUg1XBF8-zwFsiIKO5BWniCfVyFEA/edit?usp=sharing). This brief visual overview highlihts 4 key ways to create 3D geometries from 2D sketches. 
1. *Coming soon: Tutorial: Extrusion/Assembly of laser cut panels*{: .text-red-300 }
1. *Coming soon: Tutorial: Custom 3D printed mouse enclosure video*{: .text-red-300 }
1. [Onshape Stirling Engine design](https://www.youtube.com/watch?v=GYkZmE_6MpY). An **excellent** one-stop-shop from Onshape for creating multi-part 3D models, including assemblies, animation, and variables. We recommend you follow-along and reconstruct the entire assembly. [75 mins]
1. Complete The Mill's online [Slicer Tutorial](https://app.supademo.com/demo/cmqinhhc90001zb0judqlhjcf?utm_source=link) for PrusaSlicer.
1. Watch The Mill's (3-minute) [Slicer + 3D Printer Tutorial](https://www.youtube.com/watch?v=RS2ZAjKSuYc&list=PLBZaa2zz3DqG0cY6VFNdXidu7ONpXg30m&index=3) for printing on the Prusa MK4S.

### [Optional] Further resources
1. _Same suggestion as last week:_ There are many great resources online for learning CAD, and OnShape in particular, from scratch. Some additional recommended resources are Onshape's _New to CAD_ and _New to Onshape_ modules in [Onshape's Learning Center](https://learn.onshape.com/), the [Onshape Youtube channel](https://www.youtube.com/@OnshapeInc/featured), or in particular check out the many Youtube tutorials by Onshape-sponsored designer [Too Tall Toby.](https://www.youtube.com/@TooTallToby)

## Lecture

Since last week, you've worked on designing and laser-cutting a low-fidelity mouse enclosure. You've also completed additional readings on using Onshape and 3D printers to design and fabricate 3D parts. In this lecture, we will:
1. Discuss the readings and answer any questions that came up.
1. Give an overview on the 3D design and 3D printing, filling in some gaps beyond the readings.
1. Introduce this week's Lab.

[//]: # After the lecture, the slides will be posted *HERE.*{: .text-red-300 }

## Hardware & Software


### Hardware

#### 3D Printers

**3D printer model**: The Mill houses 24x 3D printers, all of them the [Prusa MK4S](https://www.prusa3d.com/product/original-prusa-mk4s-3d-printer-5/). These printers are all equipped wit a 0.4mm HF (High Flow) nozzle.

**Reservations**: of the 24x 3D printers in The Mill, half these are class-only, and half are open access. 
1. Class printers (12x). These are accessible only to students taking Mill-based classes like ours. These 12 class printers are moreover reserved exclusively for our class during our lab times. 
1. Open access printers (12x). These are accessible to all students, including you, on a first-come first-served basis. An exception is for our 3DP-focused labs on October 16th and October 23rd, when all printers are reserved for us.

**USBs**: you'll need a USB to transfer your printer files (gcode) to the printers. The Mill always tries to keep a large stash of USBs to use, but it might be useful to bring your own as a backup.

#### Material

**Material**: We will use 1.75mm PLA filament for all our 3D printing. Note that PLA is the only material permitted for 3D printing in the Mill. We've purchased mostly black PLA, please use this; we have a smaller number of white spools to offer slightly broader color options during the final project. Course materials will be stored in the Mill Storage Room, but we also have space for 3-4 spools on a rack next to the class 3D printers; the rack is labelled _AA 598_. 

**Labeling**: You must label any filament you use with two labels using masking tape. (Masking tape is available in the Mill and in the class storage area). If you're the first to use a new filament spool, add one strip of masking tape, labeling it with the class name _AA 598_; this should always be on. On a second strip, write your _first name_, _last name_, and _student ID_; you can remove this when you're done printing.  The Mill uses this to trace our class materials, but also to let the Mill staff to contact you if your print fails while you're away, so you know whether to re-run the print.


### Software

#### Onshape
We'll use Onshape, a browser-based CAD program, to design our models. You can use your own laptop for this.  

#### Slicers
We will use [PrusaSlicer](https://www.prusa3d.com/p/prusaslicer/) to _slice_ (process) our 3D models for 3D printing. You can use the Mill computers to access prusaslicer, but we recommend downloading and running it from your personal laptop. PrusaSlicer also comes in a slimmed-down browser version called [Easyprint](https://www.printables.com/slice) which you can also try.

You will export an Onshape model as a _.STL_ file, load it into PrusaSlicer, slice it, then export the _Gcode_. You will save the _Gcode_ to a USB for transfer to the printers.  Use the following settings:
1. Print settings: 0.2mm
1. Filament: Generic PLA
1. Printer: Original Prusa MK4S HF0.4 nozzle
1. Support: any, only if needed. 
1. Infill: 15% 




## Lab

This lab will have two activities: 
1. 3D printer training, which will cover PrusaSlicer and operating the Prusa printers, and 
1. Start the assignment by designing and printing even a partially complete design, so you're comfortable printing in your own time. 

The 3D printer training should take approximately 30 minutes, and Mill staff will be able to train 10-20 students at a time. Whenever you're not in the training, please proceed with starting this week's assignment.

### Design and print your own 3D model

You will begin work on your **assignment** task to produce a 3D-printed computer mouse enclosure. Start during the lab, and finish on your own time. You should have **completed all the readings** when you arrive in lab.

**You will need to submit the assignment individually, but feel free to work in pairs during lab.**

#### What to do in the lab

First, read the Assignment **Task** description below. Then proceed to read this section.

To succeed on the assignment task, your goal during the lab should be to design and print at least two small mating 3D printed parts. These could be a low-profile square (10 x 10 x 2 mm), and a slightly larger rectangle with a mating hole for that square that's toleranced upwards for the square to fit (try 10.15 x 10.15 x 2 mm). This will let you go through the process of design and fabrication on the 3D printer with mating parts:
1. Design 2 mating parts in Onshape. Dimension or offset to account for tolerance (enlarge holes for any mating parts).
1. Export your file as a .STL.
1. Use your own computer or a Mill computer to access PrusaSlicer. Orient your parts appropriately and use the Slicer settings give in the _Slicer_ section above.
1. _Slice_ the model to produce a gcode file, save to USB, and transfer to a printer.
1. After printing, try to mate your cut parts. You can borrow Calipers from the Mill to check dimensions if they need re-sizing.


## Assignments

1. **Task:** Complete this week's Task and publish your documentation on your Google Site.
1. **Reading:** *Coming soon*{: .text-red-300 }

[//]: # 1. **Reading:** Complete the [Week 4 Readings]({{ '/docs/week4/' | relative_url }}).

### Task: Laser-cut Mouse Enclosure

#### Task learning objectives
The goals of this assignment are to:
1. Learn to produce 3D models in Onshape and adjust for 3D printing tolerances for mating parts.
1. Use PrusaSlicer to process Onshape models for 3D printing.
1. 3D print mating parts.

#### Task deliverables

*Coming soon*{: .text-red-300 }
