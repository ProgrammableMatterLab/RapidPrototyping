---
title: Week 8
nav_order: 10
nav_exclude: false
description: >-
    Week 8 activities
---

# Week 8 - Project integration & Machine Building
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

This week has no external readings. You should just ensure you carefully read the Final Project page to inform your project ideation, and the Machine Building page so you come to lab prepared.

## Lecture

Over the past week, you've worked with new electronic components and started brainstorming Final Project ideas for your Conceptual Design Review. In this lecture, we will:
1. Share initial Final Prototype ideas
1. Discuss Machine Design, introducing the 2D plotter to be assembled in lab
1. Use the 2D plotter to showcase final project documentation examples

We presented the [Machine Building]({{ '/docs/resources/machine-building/' | relative_url }}) page directly; there are no separate slides. 

[//]: # *Project Integration; CAD assembly with electronics (either imported CAD or simple proxy), con ops for use, block diagrams, schematics, also useful tools like heat set inserts, electrical tape insulation....Machine Overview as Example and Lab overview*{: .text-red-300 }

[//]: # In lecture, show existing assignments and comment on ETL Survey
[//]: # In lecture, ask people to share early ideas. *Idea discussion in class to share ideas, discuss time & technical feasability, BOM required, risk mitigation (see next week), how to build.*{: .text-red-300 }




## Hardware & Software

This week's lab will involve assembling ad operating our custom 2D plotting machine. All the parts and software will be provided for you, and can be found on the [Machine Building]({{ '/docs/resources/machine-building/' | relative_url }}) page.

### Hardware

Please **ensure you bring with you all kits and components** you've taken home from previous weeks:
1. Elgeoo / Arduino Uno microcontroller
1. All electronics and kits that have been disbursed to students, as well as those that remain in the Mill.
1. Your laptop

This week we'll also provide a Machine Building kit with pre-printed parts and additional components: 
1. See the [Machine Building]({{ '/docs/resources/machine-building/' | relative_url }}) page for a list of new parts used in the lab.


### Software

1. Arduino IDE
1. [Image Converter page]({{ '/assets/files/machine-build/Image_to_Gcode_tool/index.html' | relative_url }})




## Lab

This lab will have the following activities:

1. Machine Building exercise. See the _Assembly Instructions_ section of the [Machine Building]({{ '/docs/resources/machine-building/' | relative_url }}) page for detailed instructions of what to do in the lab.
1. Staff meeting to review your published CoDR and select a Final Project.


#### What to do in the lab

1. We will disburse kits with the additional components required to complete the machine building exercise. Working in groups, assemble your machine and demonstrate operating it in both of its modes (image upload and joystick). Reference the _Assembly Instructions_ section of the [Machine Building]({{ '/docs/resources/machine-building/' | relative_url }}) page for detailed instructions on how to assemble the machine and operate it.  
1. During the machine building exercise, the staff will call on one group at a time to discuss your CoDR with you and help select a final project.
1. Reserve a few minutes with your final project group to review the PDR assignment below and coordinate on next steps.


## Assignments

**Important**: Note the assignment deadline below. Please review the [Final Project]({{ '/final-project/' | relative_url }}) page more detailed information about the final project upcoming _deadlines_.
1. **Preliminary Design Review (PDR)**: Preliminary Design Review of your selected project proposal
1. **Presentation**: A presentation to the class covering your PDR

<figure style="text-align: center;">
  <img src="{{ '/assets/images/W8-PDR.png' | relative_url }}"
       alt="device"
       style="display: block; max-width: 99%; height: auto; margin: 0 auto;">
  <figcaption>Figure 1: Specification & Critical Part Prototyping.</figcaption>
</figure>


#### Deadlines

- **Issued**: Friday November 20, 1pm (Week 8 lab)
- **Due**: Wednesday November 25, 9am (before Week 9 lecture). 

Note that you will present your Design Review **during Wednesday lecture** before we break for Thanksgiving break.

#### Deliverables

There are 2 deliverables:
- Publish your PDR to your Group Project Website
- A 6-8 minute presentation of your PDR to give to the class during lecture

To submit your PDR, document it under a "PDR" heading on your Group's Google Site, then publish it. Your presentation will use the published PDR and does not require separate submission. 


### Preliminary Design Review (PDR) 

The Preliminary Design Review is the first technical design review for any system. Its purpose is to affirm that the design will be able to meet the requirements; therefore, it focuses on full definition of the design. It has two goals:
- Analyze whether the chosen architecture can meet the requirements
- Focus on a proof-of-concept of the highest risk component(s).

See below for the sections required in your PDR. You can also see the [Machine Building]({{ '/docs/resources/machine-building/' | relative_url }}) page for examples of many deliverables.

#### Updated CoDR with Rationale 

The PDR documentation is the first page on your group website that focuses exclusively on your selected project, so your CoDR for your selected project should be copied here (Project Description, Project Design Sketch & System Requirements, BoM, and Risk Assessment).
- Update its sections with any revisions since generating and discussing the CoDR with staff. If the CoDR is unchanged, you can copy it directly 
- Clearly summarize any updates made from the original CoDR submission
- Briefly summarize the rationale for selecting it, based on both your CoDR evaluation/comparison and discussion with staff


#### Performance Requirements 

While the system level "functional" requirements detail what the device should do at a high level, the performance requirements should give some more detail on _how well_ it should do. See the [Machine Building]({{ '/docs/resources/machine-building/' | relative_url }}) page for an example. 

Aim to specify both the requirement and a test you can do to validate it: 
- Specify each performance metric; quantitatively if possible
- Specify an experiment or test you can execute to determine whether you satisfied it 


#### System Block Diagram 

The system block diagram should graphically depict the overall _architecture_ of your project: key parts or functions should be represented by _blocks_ and these should be connected by arrows showing how they _relate_ to each other. In many cases, arrows should be color-coded by (1) information/signals, (2) electrical power, and (3) mechanical movement. See the [Machine Building]({{ '/docs/resources/machine-building/' | relative_url }}) page for an example.


#### Gantt Chart & Responsibilities

Gantt Chart with key milestones for design/fabrication, electronics, code, and testing. It should span the 3 weeks  between the PDR being issued and the Presentation Day. It should include entries that are specific to your project (e.g. "fabricate rack-and-pinion mechanism" not only "design and fabrication").

Identify which group member will be the lead key aspects of the project, or how the responsibilities will be shared. You can list this separately from the Gantt Chart or annotate this directly on it.

Your Gantt chart will summarize at a high level what your action items are for the remaining week. Underneath, briefly detail any specifics about your next steps; why you think some things will take longer than others; uncertainties about your plan; what the next highest-priority tasks are.

#### Critical feature prototype

In your CoDR, you identified the key risks in your project: the most important part of your project that you are most uncertain about successfully implementing, and whose failure is most likely to jeapordize the project definition. 

_Your chief goal for this assignment is to prototype this part as well as possible_. The degree of your success will help you determine whether you should proceed with the proposed project, downscope and revert to a fall-back option, or even upscope. 

##### What to focus on for your critical feature prototype

The work you should do depends strongly on the risk you've identified:
- If it's a highly complicated mechanism, you may wish to focus the whole teams' efforts on rapidly prototyping that mechanism physically using laser cutting, and actuate it manually without electronics. If its geometry requires it to be 3D printed, you might choose to focus only on modeling it in CAD, applying constraints, and animating it, without any fabrication. 
- If it's a complicated bit of code or untested algorithm, you may want to focus exclusively on that, using just Arduino and the serial monitor to debug, without building any electronics unless also required.  
- Your risk may be spread across both code, electronics, and mechanical design. The key take-away is that you should focus your group's efforts on prototyping the critical part(s) of your project, to as high fidelity as possible, to help you determine as early as possible whether to re-scope. 

##### What to document for the critical feature prototype in your PDR

You will have a _Critical feature prototype_ section in your PDR. There you should report:
- What part you chose to work on, and why.
- Appropriate documentation, whether its CAD, physical assemblies, code and pseudocode, breadboarded electronics and schematics, etc. Include high quality documentation, including videos to support photos and screenshots wherever possible.
- Discuss your success, and share your recommended scoping outcome and why. Did the prototype work? Alternatively, did you confidently prove to yourselves that it _will_ work? Is it inconclusive given the limited time; or is it unlikely to succeed? State clearly the outcome and whether you are proceeding with the project definition, or what you are downscoping/upscoping to.


[//]: # EXCLUDED BECAUSE 5 DAY DEADLINE DUE TO THANKSGIVING BREAK
[//]: # #### Preliminary designs or low fidelity prototypes

[//]: # Other Work Update: 
[//]: # - Sketches & CAD;
[//]: # - Low-Fidelity Prototypes; 
[//]: # - Electronics schematics and breaboarded circuits; estimates of maximum current draw. 
[//]: # - Arduino PseudoCode 
[//]: # - Updated BoM



### Presentation 

Your PDR will contain both your (updated) CoDR and the new work defined above. This means it should be a self-contained document that will allow you to present your project to the class, from the initial sketch and project description to the critical prototype. 

Prepare a **6-8 minute presentation of your PDR** to give to the class during lecture. We discourage you from presenting slides; instead we encourage you to polish your published PDR on your website and narrate us through that.

