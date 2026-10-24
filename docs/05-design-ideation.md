---
title: Ideation and Concept Generation
hide:
  - toc
---

# Ideation and Concept Generation

The goal of this project is to design and build one functional robotic leg for a six-legged walking robot. During ideation, the team explored different ways to move the leg, detect its position, interact with the ground, and protect its components.

We considered rotary motors, electric linear actuators, pneumatic and hydraulic systems, sensors, different foot designs, and modular parts before narrowing our ideas into three possible concepts.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Initial Brainstorm](#initial-brainstorm)
3. [Grouping and Ranking](#grouping-and-ranking)
4. [Design Concepts](#design-concepts)
5. [Concept Comparison](#concept-comparison)
6. [Selected Features](#selected-features)
7. [Brainstorming Process](#brainstorming-process)

---

## Project Overview

Our design focuses on a single robotic leg that can eventually become part of a six-legged robot.

| Design Area | Goal |
|---|---|
| Movement | Control the leg through three joints |
| Actuation | Compare rotary and linear actuators |
| Sensors | Detect joint movement and ground contact |
| Structure | Create a lightweight and durable design |
| Safety | Prevent movement beyond joint limits |
| Modularity | Allow components to be replaced |
| Control | Coordinate movement using microcontrollers |

---

## Initial Brainstorm

The team explored 100 possible design features. The ideas were divided into categories to make them easier to compare.

### Joint Architecture and Kinematics

| # | Feature |
|---|---|
| 1 | Three-degree-of-freedom leg |
| 2 | Two-degree-of-freedom leg |
| 3 | Offset hip joint |
| 4 | Four-bar linkage |
| 5 | Parallel-link knee mechanism |
| 6 | Foot-leveling linkage |
| 7 | Adjustable upper-leg link |
| 8 | Adjustable lower-leg link |
| 9 | Interchangeable link geometry |
| 10 | Mechanical joint stops |
| 11 | Adjustable joint-angle limits |
| 12 | Foldable leg configuration |
| 13 | Workspace-optimized joint geometry |
| 14 | Self-collision optimized spacing |
| 15 | Repeatable walking-arc geometry |

### Rotary and Linear Actuation

| # | Feature |
|---|---|
| 16 | High-torque hip servo |
| 17 | High-torque knee servo |
| 18 | Compact distal servo |
| 19 | Brushless motor with planetary gearbox |
| 20 | Geared DC motor with encoder |
| 21 | Stepper motor |
| 22 | Worm-drive actuator |
| 23 | Belt-reduction transmission |
| 24 | Cable-driven joint |
| 25 | Electric linear actuator |
| 26 | Linear actuator with four-bar linkage |
| 27 | Linear actuator with position feedback |
| 28 | Lead-screw actuator |
| 29 | Pneumatic linear actuator |
| 30 | Double-acting pneumatic cylinder |
| 31 | Pneumatic actuator with flow control |
| 32 | Hydraulic linear actuator |
| 33 | Hydraulic actuator with pressure sensing |
| 34 | Spring-assisted actuator |
| 35 | Series-elastic actuator |

### Actuator Mounting and Force Transmission

| # | Feature |
|---|---|
| 36 | Quick-release actuator bracket |
| 37 | Modular actuator cartridge |
| 38 | Clevis-mounted linear actuator |
| 39 | Rocker linkage |
| 40 | Bell-crank mechanism |
| 41 | Adjustable actuator attachment point |
| 42 | Pushrod linkage |
| 43 | Dual-actuator joint |
| 44 | Hip counterbalance spring |
| 45 | Mechanical leverage system |

### Position and Motion Feedback

| # | Feature |
|---|---|
| 46 | Absolute magnetic hip encoder |
| 47 | Absolute magnetic knee encoder |
| 48 | Incremental encoder with homing |
| 49 | Potentiometer joint sensing |
| 50 | Hall-effect joint sensing |
| 51 | Linear potentiometer |
| 52 | Joint-output encoder |
| 53 | Calculated joint velocity |
| 54 | Upper-leg IMU |
| 55 | Foot-mounted IMU |
| 56 | Home-position sensor |
| 57 | End-of-travel sensor |
| 58 | Slip detection |
| 59 | Backlash estimation |
| 60 | Encoder/IMU sensor fusion |

### Foot and Ground Contact

| # | Feature |
|---|---|
| 61 | Force-sensitive resistor |
| 62 | Load cell |
| 63 | Multiple foot force sensors |
| 64 | Contact switch |
| 65 | Compliant rubber foot |
| 66 | High-friction foot insert |
| 67 | Rounded foot |
| 68 | Wide foot |
| 69 | Narrow foot |
| 70 | Articulated foot |
| 71 | Spring-loaded foot |
| 72 | Damped foot |
| 73 | Interchangeable feet |
| 74 | Toe-style climbing tip |
| 75 | Anti-slip foot geometry |

### Gecko Gripper and End-Effector Concepts

| # | Feature |
|---|---|
| 76 | Gecko-inspired adhesive foot |
| 77 | Gecko gripper end effector |
| 78 | Interchangeable gecko module |
| 79 | Passive gecko adhesive pad |
| 80 | Active gecko gripper |
| 81 | Directional gecko surface |
| 82 | Compliant gecko mount |
| 83 | Gecko pad with force sensing |
| 84 | Hybrid rubber/gecko foot |
| 85 | Replaceable end-effector interface |

### Structural Design

| # | Feature |
|---|---|
| 86 | Aluminum upper-leg link |
| 87 | Aluminum lower-leg link |
| 88 | Carbon-fiber link with printed fittings |
| 89 | Reinforced 3D-printed nylon link |
| 90 | Fiber-reinforced polymer |
| 91 | Hollow structural members |
| 92 | Ribbed printed geometry |
| 93 | Topology-optimized link |
| 94 | Removable side plates |
| 95 | Heat-set threaded inserts |

### Wiring, Safety, and Control

| # | Feature |
|---|---|
| 96 | Internal cable routing |
| 97 | Strain relief |
| 98 | Limit-switch protection |
| 99 | Emergency motor stop |
| 100 | Microcontroller-based motion control |

---

## Grouping and Ranking

After brainstorming, the features were grouped by their purpose. The main categories were movement, actuation, sensing, structural design, safety, and ground interaction.

The team compared the ideas based on how well they could support the robotic leg.

| Priority | Feature | Reason |
|---|---|---|
| High | Three-degree-of-freedom architecture | Allows movement in multiple directions |
| High | Electric linear actuators | Provides controlled extension and retraction |
| High | Position feedback | Helps determine the leg's actual position |
| High | Limit switches | Protects joints from moving too far |
| High | Pressure sensing | Detects contact with the ground |
| High | Lightweight structure | Reduces the load on actuators |
| Medium | Modular actuator mounting | Makes repairs and changes easier |
| Medium | Interchangeable feet | Allows different ground-contact designs |
| Medium | IMU | Provides orientation and motion feedback |
| Experimental | Gecko gripper | Adds specialized gripping capability |
| Experimental | Pneumatic actuation | Requires additional air-control equipment |
| Experimental | Hydraulic actuation | Requires additional fluid-control equipment |

These priorities describe the proposed design direction and should be updated with the team's final scoring results.

---

## Design Concepts

Three design concepts were developed from the brainstormed features.

### Concept 1: Rotary Servo-Actuated Leg

This concept uses rotary servo motors to move the joints.

| Feature | Description |
|---|---|
| Architecture | Three-degree-of-freedom leg |
| Actuation | Rotary servo motors |
| Feedback | Joint-position sensors |
| Safety | Mechanical joint stops |
| Foot | Interchangeable foot |
| Structure | Lightweight modular links |

**Advantages:** Direct joint control and relatively simple motion commands.

**Challenges:** Motor torque and joint loading must be considered.

![Rotary Servo Concept](../images/Concept1_Leg-1.png)

### Concept 2: Electric Linear-Actuator Leg

This concept uses electric linear actuators connected to mechanical linkages.

| Feature | Description |
|---|---|
| Architecture | Three-degree-of-freedom leg |
| Actuation | Electric linear actuators |
| Transmission | Mechanical linkage |
| Feedback | Position sensing |
| Safety | Limit switches and mechanical stops |
| Foot | Contact-sensing foot |

**Advantages:** Controlled extension and retraction with adjustable linkage geometry.

**Challenges:** Actuator mounting and joint geometry require careful design.

![Linear Actuator Concept](../images/Concept2_Leg-1.png)

### Concept 3: Linear-Actuated Leg with Gecko End Effector

This concept combines electric linear actuators with a replaceable gecko-inspired foot or gripper.

| Feature | Description |
|---|---|
| Actuation | Electric linear actuators |
| Transmission | Mechanical linkage |
| Feedback | Position sensing |
| End Effector | Gecko-inspired gripper |
| Modularity | Replaceable foot interface |
| Ground Detection | Force or pressure sensing |

**Advantages:** Adds specialized ground interaction while keeping a modular design.

**Challenges:** Gecko-style gripping introduces additional complexity.

![Gecko End Effector Concept](../images/Concept3_Leg-1.png)

---

## Concept Comparison

| Feature | Concept 1 | Concept 2 | Concept 3 |
|---|:---:|:---:|:---:|
| Three-degree-of-freedom design | Yes | Yes | Yes |
| Rotary servos | Yes | No | No |
| Linear actuators | No | Yes | Yes |
| Position feedback | Yes | Yes | Yes |
| Joint protection | Yes | Yes | Yes |
| Ground-contact sensing | Yes | Yes | Yes |
| Modular foot | Yes | Yes | Yes |
| Mechanical linkage | No | Yes | Yes |
| Gecko-inspired end effector | No | No | Yes |

---

## Selected Features

The current software and hardware proposal combines features from the different concepts.

| Area | Proposed Direction |
|---|---|
| Joint movement | Three controlled joints |
| Actuation | One servo and two linear actuators |
| Main control | PIC18F57Q43 Curiosity Nano |
| Communication | UART between Nanos |
| Ground detection | Pressure sensor |
| Orientation | IMU |
| Joint protection | Two limit switches per joint |
| User input | IR remote |
| Status | RGB and local LEDs |

These features are still being developed. Final component models and electrical connections will be documented as the project progresses.

---

## Brainstorming Process

The team began by generating individual ideas instead of choosing a complete design immediately. The brainstorming focused on ways to improve movement, stability, sensing, safety, and modularity.

Ideas were organized into categories so similar features could be compared. Features that supported the main requirements of the robotic leg were given higher priority. More complex ideas, including hydraulic systems and gecko-inspired gripping, were retained as alternatives.

The team then combined compatible features into three concepts: a rotary servo design, a linear-actuator design, and a linear-actuator design with a gecko-inspired end effector.

This process allowed the team to compare multiple approaches before developing the current hardware and software architecture.

**Team documentation to complete:** Add the actual brainstorming participants, meeting method, meeting date, tools used, and final ranking scores before submission.
