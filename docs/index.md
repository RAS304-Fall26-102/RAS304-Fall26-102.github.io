---
title: Home
tags:
- tag1
- tag2
---
<center>
<font size="8">Modular Spider Leg<br>
<font size="5">Team 102<br>
<font size="5">Kaushik, Preston, Akshan, Bex<br>
**Submission: October 29, 2026**<br>
Fall 2026<br>
<font size="4">Arizona State University<br>
**RAS 304**<br>
Professor Thangavelu<br>
  

</center>

## Project Summary

Team 102 is designing a **modular robotic spider leg** for robotics hobbyists, students and makers who want to build walking robots without designing a leg from scratch. The leg is built from 3D-printed parts, standard fasteners and off-the-shelf electronics, so users can repair it, modify it and connect it to their own projects. It has three controlled joints: one driven by a servo motor and two by linear actuators. Four PIC18F57Q43 Curiosity Nano boards share the work in a hub-and-spoke layout. Preston's main Nano computes the leg kinematics from IR-remote commands and sends position commands over **UART** to three driver Nanos. Each driver controls one joint and reports back: Akshan's drives the servo, Bex's drives linear actuator A and reads a pressure sensor for ground contact, and Kaushik's drives linear actuator B and reads an IMU for jerk and impulse sensing. Every board has its **own power supply**; the 8-pin ribbon cables between boards carry only the UART link and a ground reference.

## Team Introduction

We are Team 102: Kaushik Gunasekaren, Preston Potts, Akshan Bhelkar and Bex Baker, students in RAS 304 (Embedded Systems) at Arizona State University. Each of us designs and documents one board of the leg, and together we define the shared requirements, block diagram and software.

| Section | What you'll find |
|---|---|
| [Team Organization](02-Team-Organization.md) | Team charter, mission statement and who is responsible for each board |
| [User Needs and Benchmarking](03-User-Needs-and%20Benchmarking.md) | Who the leg is for and how it compares with existing products |
| [Product Requirements](04-Product-Requirements.md) | The numbered requirements every board is designed against |
| [Design Ideation](05-design-ideation.md) | The concepts we generated and how the current design was chosen |
| [Team Block Diagram](06-team-block-diagram.md) | How the four boards connect and what each one does |
| [Software Proposal](07-Software%20Proposal.md) | The control flow and UART messages between the Nanos |


## Team Members' Datasheet Links

| **Team Member**        |**Ind Datasheet Links** |
| ---------------------- | -----------------------|
| Kaushik Gunasekaren    | [Kaushik's GitHub](https://kaushikgunasekaren.github.io/kgunase7_RAS304_F26/) |
| Preston Potts          | [Preston's GitHub](https://r0gue12.github.io/papotts_RAS304_Fall26/) |
| Akshan Bhelkar         | [Akshan's GitHub](https://akshan2.github.io/abhelkar_RAS304_F26/) |
| Bex Baker              | [Bex's GitHub](https://rab2254-art.github.io/rbaker54_RAS304_F26/) |
