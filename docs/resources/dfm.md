---
layout: page
title: DfM
parent: Resources
nav_exclude: false
description: >-
    Design for Manufacturing
---

# About
{:.no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Design for Manufacturing

Design for manufacturability will be a constant topic throughout this course. Just because you can model something digitall in CAD doesn't mean you can build it physically; the manufacturing process will often dictate the design and leave behind tell-tale signs. On this page, we'll identify some key points relating to our **computer mouse** in particular. 

### Co-design of a part geometry, electronics, and manufacturing/assembly process

Building physical products don't just involve designing for their intended functionality; they must also account for their manufacturing and assembly. Consider a computer mouse. It has some mechanical function (it should fit in your hand, it should be light, etc) and some electronic function (register button clicks, connect to a PC, etc.) These mechanical and electronic features must be co-designed; at the very least, the electronics should fit within the mechanical enclosure. But both features must also be designed to to support manufacturing and assembly. Many of these features become visible when we disassemble a computer mouse in our teardown assignment. We'll notice geometric features like ribs, bosses, grooves, fasteners, openings, compliant features, and connectors, and reason about how these connect to requirements for structural stiffness, alignment, tolerance, assembly sequence, user interaction, and access to internal components.

#### Manufacturing Related Features
Below is a list of manufacturing-related features to look out for. The computer mice we'll look at are injection molded; they will be designed with _Draft angle_ in mind and leave behind a _Parting line_. The designs we make in this class, for laser cutting and 3D printing, won't need to account for draft angle but will have their own unique and related constraints, which we'll introduce when we discuss those processes. All the other features will be common to all these manufacturing workflows. 
1. **Draft angle**: slight taper added to vertical walls that helps an injection-molded molded part release from its mold. This constraint is specific to injection molding, and we'll learn other constraints specific to laser cutting and 3D printing later.
1. **Bosses and grooves**: raised features used to locate, support, or fasten parts (like the PCB).
1. **Parting line**: A seam or line left on an injection-molded plastic part where the two halves of the mold meet. 
1. **Wall thickness**: affects strength, weight, and molding quality. Too thick and we waste material/cost; too thin and wall may break/warp.
1. **Ribs**: thin reinforcing features that increase wall stiffness to avoid making a wall too thick.
1. **Tolerances**: allowable variation in dimensions needed for parts to fit and function.
1. **Snap fit**: a compliant feature that temporarily deforms and locks parts together.
1. **Fasteners**: hardware such as screws, bolts, nuts, or threaded inserts used to join parts with.
1. **Assembly access**: openings or separable parts that allow components (like the PCB) to be inserted, connected, or serviced. Notice the mouse needs to assembled from disjoint parts so the PCB can be inserted and assembled. 
1. **Part access**: Unlike a 1-time assembly access, these are openings that allow components (like the USB wire, mouse wheel, and sensor) to permanently connect to or interface with the outside world.  
1. **Features for user Input transfer**: Features designed specifically for user interaction and ergonomics. Our computer mouse is sized for an average adult hand. It also provides tactile feedback - a _click_ - to tell the user when a button press is registered (consider and check yourself: does the _click_ come from the injection-molded part _or_ from the electronic button?)  