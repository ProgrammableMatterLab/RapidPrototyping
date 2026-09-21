---
layout: page
title: About
nav_order: 1
nav_exclude: false
description: >-
    Course policies and information.
---

# About
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

## Course Overview


Rapid prototyping and digital fabrication refer to the act of quickly fabricating a functional _physical_ device from a _digital_ model. They involve tools like 3D printers, electronics, and microcontroller programming to quickly physicalize a design idea. These techniques are used for protoyping iterations of commercial parts before full-scale production, but are just as often used by entrepreneurs, researchers, and hobbyists to create custom physical devices that are only required in small volumes. These are particularly critical skills for engineers, who, even if focusing on more theoretical work, can utilize rapid protoyping to build physical systems that perform specific tasks, test theories, or gather experimental data.

This hands-on studio course will introduce students to rapid prototyping through designing and fabricating electromechanical devices. Core topics include CAD, 3D printing, laser cutting, electronics, and microcontroller programming on the Arduino platform. The class will meet twice weekly, once for a lecture and once for a lab. Following a flipped classroom approach, weekly readings will introduce students to key design skills and should be completed before the lecture/lab. This is to allow the lecture to be spent resolving any questions that arose from readings, and to allow the limited lab time to be spent on physical fabrication. There will be weekly assignments and a final project, all involving design and fabrication. 

In-person participation is required for all lectures and labs, as these involve supervised physical fabrication tasks and trainings. No pre-requisites or prior experience in design or fabrication are required. Please see the [Syllabus]({{ '/syllabus/' | relative_url }}) page for more detailed information.




### What should I know to decide whether to take this class?
- **We will design, build and program custom physical devices**. This course is a broad coverage of skills used for the mechanical design, electronics, manufacturing, and programming of physical devices. In particular, much of the class will involve CAD, 3D printing, breadboarding electronics, and microcontroller programming using Arduino. The course aims to teach students with no experience in these topics how to prototype a custom physical device, to the complexity that is possible in 10 weeks. You’ll learn just enough in this class to 3D model and fabricate mechanical parts, instrument them with simple sensors and actuators, and program a microcontroller with basic functionality.
- **It will require independence and responsibility**. This is primarily a skills-based studio course, not a theory-based course. Learning skills require you to practice and learn concepts on your own, and there is not enough time to cover everything in lecture. You will be assigned weekly readings and tutorials so that you can learn and practice key design skills on your own; then come to lecture and lab with questions for the instructor to answer.  
- **You will need to attend every lecture and lab in person.** The class consists of weekly lectures and weekly labs that require in-person participation for physical building exercises and equipment trainings that cannot be rescheduled. 
- **We will cover breadth, not depth.** The class is not a substitute for a dedicated design/electronics/programming course, but will help you discover if you’d like to pursue focused classes on these topics. The motivation for this class is to show how these typically disjoint topics fit together, and to provide a space for students to learn the physical skills to design and build things.
- **This class is particularly for students with no prior design/building experience.** This course assumes no prior knowledge in any of these subjects, but it will require a lot of out-of-class time and effort. Students with prior experience are also welcome.


## Schedule (tentative)


<style>
.class-schedule {
  width: 100%;
  max-width: 100%;
  table-layout: fixed;
  font-size: 0.8rem;
}

.class-schedule th,
.class-schedule td {
  padding: 0.3rem 0.35rem;
  text-align: center;
  vertical-align: middle;
  overflow-wrap: anywhere;
  word-break: normal;
}

.class-schedule .design-fabrication {
  background-color: #dbeeff;
}

.class-schedule .electronics-programming {
  background-color: #dcf5df;
}

.class-schedule .final-project {
  background-color: #fff4cc;
}

.class-schedule .holiday-none {
  background-color: #f8d7da;
}
</style>

<table class="class-schedule">
  <thead>
    <tr>
      <th>Week</th>
      <th>Module</th>
      <th>Topic</th>
      <th>Lecture: Wed</th>
      <th>Lab: Fri</th>
      <th>Lab activity</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td class="design-fabrication">Design + Fabrication</td>
      <td>Intro to Prototyping</td>
      <td>Sep 30</td>
      <td>Oct 2</td>
      <td>Laser training + Mouse teardown</td>
    </tr>
    <tr>
      <td>2</td>
      <td class="design-fabrication">Design + Fabrication</td>
      <td>2D design + laser cutting</td>
      <td>Oct 7</td>
      <td>Oct 9</td>
      <td>Low fidelity mouse (laser-cut)</td>
    </tr>
    <tr>
      <td>3</td>
      <td class="design-fabrication">Design + Fabrication</td>
      <td>3D design + 3D printing</td>
      <td>Oct 14</td>
      <td>Oct 16</td>
      <td>High fidelity mouse (3DP)</td>
    </tr>
    <tr>
      <td>4</td>
      <td class="design-fabrication">Design + Fabrication</td>
      <td>Mechanisms + assembly</td>
      <td>Oct 21</td>
      <td>Oct 23</td>
      <td>Mechanisms + assembly</td>
    </tr>
    <tr>
      <td>5</td>
      <td class="electronics-programming">Electronics + Programming</td>
      <td>Electronics</td>
      <td>Oct 28</td>
      <td>Oct 30</td>
      <td>Electronics</td>
    </tr>
    <tr>
      <td>6</td>
      <td class="electronics-programming">Electronics + Programming</td>
      <td>Microcontroller programming</td>
      <td>Nov 4</td>
      <td>Nov 6</td>
      <td>Programming</td>
    </tr>
    <tr>
      <td>7</td>
      <td class="electronics-programming">Electronics + Programming</td>
      <td>Inputs + Outputs</td>
      <td class="holiday-none">UW Holiday</td>
      <td>Nov 13</td>
      <td>Inputs + Outputs</td>
    </tr>
    <tr>
      <td>8</td>
      <td class="electronics-programming">Electronics + Programming</td>
      <td>Project Integration</td>
      <td>Nov 18</td>
      <td>Nov 20</td>
      <td>Machine Assembly + Project brainstorm</td>
    </tr>
    <tr>
      <td>9</td>
      <td class="final-project">Final Project</td>
      <td>Initial design review</td>
      <td>Nov 25</td>
      <td class="holiday-none">UW Holiday</td>
      <td class="holiday-none">None</td>
    </tr>
    <tr>
      <td>10</td>
      <td class="final-project">Final Project</td>
      <td>Final design review</td>
      <td>Dec 2</td>
      <td>Dec 4</td>
      <td>Work on final projects</td>
    </tr>
    <tr>
      <td>11</td>
      <td class="final-project">Final Project</td>
      <td>Final Project Presentations</td>
      <td>Dec 9</td>
      <td>Dec 11</td>
      <td>Finish + present final projects</td>
    </tr>
  </tbody>
</table>

## Lectures

Weekly lectures (in GUG 204) will introduce the week's topic, create space for discussing the weekly readings, introduce the lab, and expose students to state of the art research in rapid prototyping. 

## Labs

Every week we will have a lab, involving hands-on manufacturing. Labs will be held in [The Mill Makerspace](https://hfs.uw.edu/experience/perks-recreation/the-mill/), located in [McCarty Hall](https://www.google.com/maps/place/McCarty+Innovation+%26+Learning+Lab+(The+MILL)/@47.6605206,-122.3051746,306m/data=!3m1!1e3!4m14!1m7!3m6!1s0x5490148ea8d9fc2d:0x67d212a0f804342!2sMcCarty+Hall+(MCC)!8m2!3d47.6607654!4d-122.304984!16s%2Fg%2F1pp2vlrnf!3m5!1s0x549015aaf40a4b19:0x889b35b583fd7570!8m2!3d47.660533!4d-122.3046792!16s%2Fg%2F11gmczmx3v?entry=ttu&g_ep=EgoyMDI2MDgyNi4wIKXMDSoASAFQAw%3D%3D). Some days will involve Mill-staffed trainings or group exercises, so it is critical to arrive on time. See [The Mill (labs)]({{ '/docs/resources/the-mill/' | relative_url }}) page for more information about the space, required trainings and personal attire.

## Assignments

We will issue an assignment every week. Assignments will consist of a design/fabrication **Task** and a **Reading**. The Task will center on the current week's topic, and the Reading will be on next week's topic. Readings are issued/due on Wednesdays; Tasks are issed/due Fridays. Only Tasks are graded.

For example, Week 2 centers on 2D design and laser cutting. The reading on laser cutting, assigned in Week 1, will be due on the Week 2 lecture. This is so that you can come prepared with questions, and are ready to complete the laser cutting lab that week. You will not be able to complete the Lab without having done the reading beforehand. For topical clarity, the Week 2 reading details will be listed on the Week 2 page under a _Readings & Preparation_ section, but you will be prompted to complete this in the Week 1 _Assignments_ section.

<figure style="text-align: center;">
  <img src="{{ '/assets/images/W0-assignment-flow.png' | relative_url }}"
       alt="Assignment schedule"
       style="display: block; max-width: 95%; height: auto; margin: 0 auto;">
  <figcaption>Figure 1: Cadence of weekly Assignments: Readings and Tasks.</figcaption>
</figure>


## Final project

The class will end with a final project. This will involve designing, fabricating, assembling, and programming a physical device using the skills learnt throughout the course.
