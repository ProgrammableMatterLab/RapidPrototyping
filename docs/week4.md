---
title: Week 4
nav_order: 6
nav_exclude: false
description: >-
    Week 4 activities
---

# Week 4 - Joining and mechanisms
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

This week's readings center on integrating parts into mechanisms: designing and building physical mechanisms, using fasteners, and creating assemblies and animations in Onshape.

### Tutorials / Readings

We recommend going through the tutorials in the order they are listed.

[//]: # 1. *Making things Move chapter 8; pretty cursory*{: .text-red-300 }
[//]: # 1. *Assembly readings*{: .text-red-300 }
[//]: # 1. *Soldering for heat sets?*{: .text-red-300 }

1. [Gear basics](https://www.youtube.com/watch?v=ZhDO16FDmxA). A slightly robotic narration and background music, but otherwise a concise introduction to gear types and design, with some applications. We will not go further down the rabbithole that is gear design; our focus is on fabricating them and Onshape provides tools for this, but this video provides useful background. [15 minutes].
1. [Spur gears and 3D printed screw threads](https://www.youtube.com/watch?v=2UIJc4k1EjI). This Teaching Tech tutorial covers adding features via FeatureScript, designing spur gears in Onshape, 3D printing and using regular threaded fasteners, as well as assemblies and animations. We recommend adding and testing the Spur Gear FeatureScript in particular. [18 minutes].
1. [Rack and Pinion design](https://www.youtube.com/watch?v=wLZq1ZXhPfE). Designing and Rack and Pinion mechanism in Onshape. Focuses on designing a custom rack to mesh with a spur gear generated via FeatureScript. [8 minutes].  
1. [Onshape Assemblies and Animations](https://www.youtube.com/watch?v=cHXK91gtknE). Covers slider, revolute, and rack and pinion mates, including animations in Onshape. [11 minutes].
1. [More key mechanisms](https://www.youtube.com/watch?v=vzM_-Rr5mtw). Covers some key mechanisms, design principles behind them, example applications, and project ideas. Covers Cams, Geneva mechanisms, Ratchet & Pawl, Oldham coupling, Four-bar linkage, Scotch yoke, and leaf spring. [13 minutes].
1. [3D-printed compliant mechanisms](https://www.youtube.com/watch?v=xV36ITRjP_4). A show-and-tell by Teaching Tech of a variety of compliant 3D printed mechanisms, several taken from the BYU CMR website. Includes slicing/printing tips. [17 minutes].
1. [Four bar linkages](https://www.youtube.com/watch?v=XvYNqj4awM8). A tutorial by Teaching Tech on designing four-bar linkages in Onshape, printing them, and actuating with a motor. [11 minutes].
1. Formlabs' reference for [fasteners and inserts for 3D printed parts](https://formlabs.com/blog/adding-screw-threads-3d-printed-parts/).

### [Optional] Further resources
1. [507 Mechanical movements](https://www.fivehundredseven.com/507). 3D printed recreations of several mechanisms from Henry T. Brown's "507 Mechanical Movements" written in the 1860s. Modeled in Onshape and printed on a Formlabs resin printer.
1. [Compliant mechanisms](https://compliantmechanisms.byu.edu/maker-resources). See the Maker Resources on the BYU Compliant Mechanisms and Robotics Group for examples and CAD files to many mechanisms.
1. [100 mechanisms](https://www.youtube.com/watch?v=nhd0NdZDjWw). A long sequence of animations of a variety of mechanisms for further inspiration.


## Lecture

Since last week, you've worked on designing and 3D printing a high-fidelity mouse enclosure. You've also completed additional readings on integrating parts into mechanisms. In this lecture, we will:
1. Discuss the readings and answer any questions that came up.
1. Give an overview on mechanism design and assemblies, filling in some gaps beyond the readings.
1. Introduce this week's Lab.

[//]: # You can access the Lecture 4 slides here: [Lecture 4 slides]().



## Hardware & Software

This week's assignment will predominantly rely on hardware and software already introduced in week 2 (for laser cutting) and week 3 (for 3D printing). Please refer to those pages if needed.

The lab will involve a separate hardware kit, detailed in the **lab** section below.

[//]: # ### Hardware

[//]: # #### Soldering irons
[//]: # For heat set inserts. Mention need safety glasses for soldering





## Lab

This lab will have the following activities: 
1. In a groups of 2, assemble all the mechanisms in the [Mechanism Kit]({{ '/docs/resources/mech-kit/' | relative_url }}).
1. After you finish the Mechanism Kit activity, start brainstorming/designing for the assignment task. If you wish, you are welcome to work on the assignment in groups, and may want to use lab time to form and discuss with your group. See the Assignment for details on group submissions.



### Mechanism kit assembly

The first lab activity will be to form groups and complete the Mechanism Kit activity. You should complete this activity during the lab, and return the kits to us at the end of lab. Note that the Mechanism Kit activity is ungraded and is separate from the assignment task.

You should have **completed all the readings** when you arrive in lab.

#### What to do in the lab

The Mechanism Kit activity will involve assembling and inspecting several key mechanisms built from laser-cut and 3D printed parts. The intent is to let you familiarize yourselves with several functional mechanisms, and build an intuition for how you might design and incorporate similar mechanisms into your assignment task. Do the following:
1. See the [Mechanism Kit]({{ '/docs/resources/mech-kit/' | relative_url }}) page. In pairs, follow the instructions and assemble each mechanism.
1. Once finished, disassemble your kit, account for all parts, and return them to us.
1. Proceed with remaining lab activities.

## Assignment

1. **Task:** Complete this week's Task and publish your documentation on your Google Site.
1. **Reading:** Complete the [Week 5 Readings]({{ '/docs/week5/' | relative_url }}).



<figure style="text-align: center;">
  <img src="{{ '/assets/images/W4-rube-gold.png' | relative_url }}"
       alt="3DP Mouse"
       style="display: block; max-width: 90%; height: auto; margin: 0 auto;">
  <figcaption>Figure 1: A laser-cut Rube Goldberg Machine.</figcaption>
</figure>

### Task: Rube Goldberg Machine

<center>
  <strong>Rube Goldberg machine</strong><br>
  <em>A machine that accomplishes by complex means what seemingly could be done simply.</em>
</center>


#### Task definition

The intention behind this task is to give you the creative freedom to design and build a device you find interesting. **The only constraint is that it should have moving parts, i.e. mechanisms.** You are encouraged to integrate both laser-cut and printed parts as appropriate.  

Given this intent, you are welcome to interpret [Rube Goldberg machine](https://en.wikipedia.org/wiki/Rube_Goldberg_machine) broadly. For example, an alternative that you're equally welcome to pursue is a [kinetic art sculpture](https://en.wikipedia.org/wiki/Kinetic_art). Please skim through this [Kinetic Art compilation](https://www.youtube.com/watch?v=0_22x26qYPA) for inspiration. 

The artifact you produce can be 3D printed, laser-cut, or both; it can be fully 3D, or it can be 2.5D by mounting fabricated parts to a pegboard, for example. You are also welcome to complete this task in groups; more details on this below.


#### Task learning objectives
The goals of this assignment are to:
1. Learn to produce assemblies in Onshape, including setting mechanism DoFs for animations.
1. Manufacture functional mechanisms using 3D printing and laser cutting.

#### Task Deliverables

The deliverables for the Rube Goldberg Machine center on: CAD documentation, fabrication documentation, and final physical prototype, including videos/gifs of working mechanisms. 

At a minimum, you should complete:
1. CAD screenshots showing the development of your design, with dimensioning.
1. A video/gif of a CAD animation of at least one of your mechanisms. 
1. Photos taken of your fabricated parts
1. Photos and video/gifs of your assembled physical machine. The machine should: 
    1. Have a function that you can articulate as a design objective.
    1. Have moving parts by incorporating at least 1 mechanism.
    1. Have at least 10 individual parts (per person, if in group)
    1. You should justify your use of 3D printing / laser cutting for each part.  
1. In your documentation, you should discuss the development of your work; your design decisions, things you tried that did or didn't work, helpful resources you used, suprising outcomes etc.

For full credit, you can try some of the following:
1. A video/gif of an onshape animation of _all_ mechanisms in your machine. If you have mechanisms that Onshape struggles to animate, you can manually move parts in your assembly to demonstrate their degrees of freedom have been set using the appropriate mate connectors.
1. Increase the complexity of your machine; build more parts, integrate more mechanisms, introduce additional unique mechanisms beyond those covered in class. 

To submit your assignment, document it under a Week 4 heading on your Google Site, then publish it.

#### Instructions for assignments done in groups

To allow the design and fabrication of more complex machines, you are welcome to work in groups of up to 3 for this assignment. Please note the following instructions:
1. You will need to submit the assignment individually under a Week 4 heading on your website.
1. Report the team members (first and last name), and which parts each member was responsible for.
1. Your submission should include specific documentation on _your_ contribution to the group project. As usual, this should document your design decisions, things you tried that did or didn't work, helpful resources you used, suprising outcomes etc.   
1. Your submission should also include documentation of the entire group project, including CAD and photos/videos of individual parts and the final assembly. You may share all the same _media_ (CAD screenshots, photos, gifs etc.) with group members, but your website _write-up_ should be individual.

{: .highlight }
> **Mechanism design**
> 
> A detailed exposition of the design of every mechanism - the kinematics, forces/torques, and velocity profiles - is out of scope of this class, where we're interested in the shortest path to building something that works. There are many resources online to help with this; for example, see the [Mechsimulator website](https://mechsimulator.com/) which provides a browser-based interactive simulator for many mechanisms, including [Geneva, cam-follower, four-bar linkages, scotch yoke, slider-crank](https://mechsimulator.com/?q=mechanism) and [gear trains](https://mechsimulator.com/tools/gear-trains/).

{: .highlight }
> **Making Gifs**
> 
> Embedding videos in websites can sometimes feel a little clunky, and you'll need to ensure any videos in your Google Site have permissions set to allow public viewing. As an alternative, consider processing your videos into gifs and embedding those in your site instead. There are many free online tools for this; we recommend [Ezgif](https://ezgif.com/maker) which allows you to tweak frame rate and other features to dial in the gif settings. 