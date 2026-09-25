---
title: Ideation and Concept Generation
---

# Ideation and Concept Generation

## Overview

The purpose of this design ideation phase was to explore a wide range of possible features for a modular robotic leg intended for a six-legged walking robot.

Rather than selecting one design immediately, the team generated approximately 100 individual product features covering joint architecture, actuation, sensing, structural design, foot interaction, modularity, and control. These ideas were then grouped and ranked before being combined into three distinct product concepts.

---

# Initial Brainstorm

The brainstorm focused on generating individual features that could later be combined into complete robotic-leg designs.

## Joint Architecture and Kinematics

1. Three-degree-of-freedom leg with hip yaw, hip pitch, and knee pitch
2. Two-degree-of-freedom leg for simpler control
3. Offset hip joint to increase lateral workspace
4. Four-bar linkage to control foot motion
5. Parallel-link knee mechanism for improved load support
6. Mechanical linkage that keeps the foot approximately level
7. Adjustable upper-leg link length
8. Adjustable lower-leg link length
9. Interchangeable link geometry for different stride lengths
10. Mechanical joint stops to prevent over-rotation
11. Adjustable joint-angle limits
12. Foldable leg configuration for compact storage
13. Joint geometry designed to maximize useful workspace
14. Joint spacing designed to reduce self-collision
15. Leg geometry designed around a repeatable walking arc

## Rotary and Linear Actuation

16. High-torque digital servo at the hip
17. High-torque digital servo at the knee
18. Compact servo at the distal joint
19. Brushless motor with planetary gearbox
20. Geared DC motor with encoder feedback
21. Stepper motor for precise joint positioning
22. Worm-drive actuator for high holding torque
23. Belt-reduction transmission
24. Cable-driven joint
25. Electric linear actuator
26. Electric linear actuator driving a four-bar linkage
27. Electric linear actuator with built-in position feedback
28. Lead-screw actuator
29. Pneumatic linear actuator
30. Double-acting pneumatic cylinder
31. Pneumatic cylinder with adjustable flow control
32. Hydraulic linear actuator
33. Hydraulic cylinder with pressure sensing
34. Spring-assisted actuator
35. Series-elastic actuator

## Actuator Mounting and Force Transmission

36. Quick-release actuator mounting bracket
37. Modular actuator cartridge
38. Clevis-mounted linear actuator
39. Rocker linkage
40. Bell-crank mechanism
41. Adjustable actuator attachment point
42. Pushrod linkage
43. Dual-actuator joint
44. Counterbalance spring at the hip
45. Mechanical leverage system to reduce actuator force requirements

## Position and Motion Feedback

46. Absolute magnetic encoder at the hip
47. Absolute magnetic encoder at the knee
48. Incremental encoder with startup homing
49. Potentiometer-based joint-angle sensing
50. Hall-effect joint-angle sensing
51. Linear potentiometer for actuator extension
52. Encoder mounted directly on the joint output shaft
53. Joint velocity calculated from encoder data
54. IMU mounted on the upper leg
55. IMU mounted near the foot
56. Home-position sensor
57. End-of-travel sensor
58. Slip detection using commanded and measured position
59. Backlash estimation using position feedback
60. Sensor fusion between encoder and IMU data

## Foot and Ground Contact

61. Force-sensitive resistor in the foot
62. Load cell for measuring ground reaction force
63. Multiple force sensors across the foot
64. Contact switch for ground detection
65. Compliant rubber foot pad
66. Replaceable high-friction foot insert
67. Rounded foot for uneven surfaces
68. Wide foot for soft terrain
69. Narrow foot for hard indoor surfaces
70. Articulated foot
71. Spring-loaded foot
72. Damped foot mechanism
73. Interchangeable foot designs
74. Toe-style obstacle-climbing tip
75. Foot geometry designed to reduce slipping

## Gecko Gripper and End-Effector Concepts

76. Gecko-inspired adhesive foot
77. Gecko gripper end effector
78. Interchangeable gecko foot module
79. Passive gecko adhesive pad
80. Actively engaged gecko gripper
81. Directional gecko adhesive surface
82. Compliant gecko foot mount
83. Gecko pad with integrated force sensing
84. Hybrid rubber and gecko adhesive foot
85. Replaceable end-effector interface

## Structural Design

86. Lightweight aluminum upper-leg link
87. Lightweight aluminum lower-leg link
88. Carbon-fiber link with printed fittings
89. Reinforced 3D-printed nylon link
90. Fiber-reinforced polymer structure
91. Hollow structural members
92. Ribbed printed geometry
93. Topology-optimized leg link
94. Removable side plates
95. Heat-set threaded inserts

## Wiring, Safety, and Control

96. Internal cable routing through the leg
97. Strain relief near moving joints
98. Motor-current sensing for stall detection
99. Automatic startup calibration
100. Closed-loop position control with an emergency fault state

---

## Initial Brainstorm Snapshot

![Initial Brainstorm](images/initial-brainstorm.png)

---

# Grouping and Ranking

After the initial brainstorm, the ideas were grouped according to their primary function. This allowed the team to compare related features and identify which ideas could be combined into complete product concepts.

The features were ranked based on their importance to the operation, control, safety, modularity, and adaptability of the robotic leg.

## Highest Priority — Core Features

| Rank | Feature |
|---:|---|
| 1 | Three-degree-of-freedom leg with hip yaw, hip pitch, and knee pitch |
| 2 | High-torque digital servo at the hip |
| 3 | High-torque digital servo at the knee |
| 4 | Absolute magnetic encoder at the hip |
| 5 | Absolute magnetic encoder at the knee |
| 6 | Closed-loop position control with emergency fault state |
| 7 | Mechanical joint stops |
| 8 | Load cell for measuring ground reaction force |
| 9 | Interchangeable foot designs |
| 10 | Modular actuator cartridge |
| 11 | Joint geometry designed to maximize useful workspace |
| 12 | Motor-current sensing for stall detection |
| 13 | Reinforced 3D-printed nylon structure |
| 14 | Automatic startup calibration |
| 15 | Adjustable actuator attachment point |

## Very Strong Features

| Rank | Feature |
|---:|---|
| 16 | Electric linear actuator |
| 17 | Electric linear actuator with position feedback |
| 18 | Electric linear actuator driving a four-bar linkage |
| 19 | Four-bar linkage |
| 20 | Adjustable joint-angle limits |
| 21 | Encoder mounted directly on the joint output shaft |
| 22 | Home-position sensor |
| 23 | Quick-release actuator mounting bracket |
| 24 | Low-friction joint support |
| 25 | Adjustable upper-leg link length |
| 26 | Adjustable lower-leg link length |
| 27 | Compliant rubber foot pad |
| 28 | Strain relief near moving joints |
| 29 | Internal cable routing |
| 30 | Spring-assisted actuator |

## Alternative Actuation Concepts

| Rank | Feature |
|---:|---|
| 31 | Pneumatic linear actuator |
| 32 | Double-acting pneumatic cylinder |
| 33 | Pneumatic cylinder with adjustable flow control |
| 34 | Hydraulic linear actuator |
| 35 | Hydraulic cylinder with pressure sensing |
| 36 | Geared DC motor with encoder feedback |
| 37 | Brushless motor with planetary gearbox |
| 38 | Worm-drive actuator |
| 39 | Lead-screw actuator |
| 40 | Series-elastic actuator |

## Sensor and Feedback Features

| Rank | Feature |
|---:|---|
| 41 | Hall-effect joint-angle sensing |
| 42 | Linear potentiometer for actuator extension |
| 43 | Potentiometer-based joint-angle sensing |
| 44 | Upper-leg IMU |
| 45 | Foot-mounted IMU |
| 46 | Force-sensitive resistor |
| 47 | Multiple force sensors across the foot |
| 48 | End-of-travel sensor |
| 49 | Slip detection |
| 50 | Encoder and IMU sensor fusion |
| 51 | Joint velocity calculation |
| 52 | Backlash estimation |
| 53 | Contact switch |
| 54 | Incremental encoder with homing |

## Gecko Gripper and End-Effector Features

| Rank | Feature |
|---:|---|
| 55 | Interchangeable gecko foot module |
| 56 | Gecko gripper end effector |
| 57 | Gecko-inspired adhesive foot |
| 58 | Compliant gecko foot mount |
| 59 | Gecko pad with integrated force sensing |
| 60 | Replaceable end-effector interface |
| 61 | Hybrid rubber and gecko adhesive foot |
| 62 | Actively engaged gecko gripper |
| 63 | Directional gecko adhesive surface |
| 64 | Passive gecko adhesive pad |

## Mechanical Structure and Transmission

| Rank | Feature |
|---:|---|
| 65 | Rocker linkage |
| 66 | Bell-crank mechanism |
| 67 | Pushrod linkage |
| 68 | Mechanical leverage system |
| 69 | Counterbalance spring |
| 70 | Parallel-link knee mechanism |
| 71 | Lightweight aluminum upper-leg link |
| 72 | Lightweight aluminum lower-leg link |
| 73 | Hollow structural members |
| 74 | Ribbed printed structure |
| 75 | Heat-set threaded inserts |
| 76 | Removable side plates |
| 77 | Interchangeable link geometry |
| 78 | Structural guards |
| 79 | Topology-optimized leg link |
| 80 | Carbon-fiber link with printed fittings |

## Specialized Features

| Rank | Feature |
|---:|---|
| 81 | Articulated foot |
| 82 | Spring-loaded foot |
| 83 | Damped foot mechanism |
| 84 | High-friction foot insert |
| 85 | Wide foot for soft terrain |
| 86 | Rounded foot for uneven terrain |
| 87 | Toe-style obstacle-climbing tip |
| 88 | Anti-slip foot geometry |
| 89 | Narrow foot for hard surfaces |
| 90 | Compact distal servo |

## Experimental / Lower Priority Features

| Rank | Feature |
|---:|---|
| 91 | Cable-driven joint |
| 92 | Belt-reduction transmission |
| 93 | Dual-actuator joint |
| 94 | Two-degree-of-freedom leg |
| 95 | Foldable leg configuration |
| 96 | Offset hip joint |
| 97 | Foot-leveling linkage |
| 98 | Fiber-reinforced polymer structure |
| 99 | Joint spacing optimized for self-collision |
| 100 | Leg geometry optimized around a predetermined walking arc |

---

## Ranked Brainstorm Snapshot

![Ranked Brainstorm](images/ranked-brainstorm.png)

---

# Product Concepts

The highest-ranked and most compatible features were combined into three different robotic-leg concepts.

## Concept 1 — Rotary Servo-Actuated Leg

The first concept uses rotary electric actuators directly at the main leg joints.

### Main Features

- Three-degree-of-freedom architecture
- High-torque hip and knee servos
- Absolute magnetic encoders
- Closed-loop position control
- Mechanical joint stops
- Ground-force sensing
- Interchangeable foot
- Modular structural components

![Rotary Servo Concept](images/concept-1.png)

---

## Concept 2 — Electric Linear-Actuator Leg

The second concept uses electric linear actuators connected to mechanical linkages to create joint movement.

### Main Features

- Electric linear actuators
- Four-bar or rocker linkage
- Adjustable actuator attachment points
- Position feedback
- Mechanical joint limits
- Ground-force sensing
- Modular actuator mounting
- Protected wiring

![Linear Actuator Concept](images/concept-2.png)

---

## Concept 3 — Linear-Actuated Leg with Gecko End Effector

The third concept combines linear-actuator movement with a modular end-effector system.

### Main Features

- Linear actuator-based movement
- Mechanical linkage
- Position feedback
- Replaceable end-effector interface
- Gecko-inspired gripper
- Compliant foot mounting
- Force sensing
- Interchangeable standard foot

![Gecko End Effector Concept](images/concept-3.png)

---

# Concept Comparison

| Feature | Concept 1 | Concept 2 | Concept 3 |
|---|:---:|:---:|:---:|
| Rotary actuation | ✓ |  |  |
| Linear actuation |  | ✓ | ✓ |
| Position feedback | ✓ | ✓ | ✓ |
| Mechanical joint limits | ✓ | ✓ | ✓ |
| Ground sensing | ✓ | ✓ | ✓ |
| Modular foot | ✓ | ✓ | ✓ |
| Gecko end effector |  |  | ✓ |

---

# Selected Features Moving Forward

Several features were identified as useful across multiple concepts:

- Three-degree-of-freedom movement
- Position feedback
- Closed-loop control
- Mechanical joint limits
- Ground-contact sensing
- Modular actuator mounting
- Replaceable foot or end-effector interface
- Lightweight structural components
- Protected wiring
- Startup calibration

These features will continue to be considered as the team evaluates the three concepts and moves toward a final leg design.

---

# Brainstorming Process

A separate page documents how the brainstorming session was conducted, including team participation, meeting format, resources, grouping, and ranking.

[View the Brainstorming Process](brainstorming-process.md)

---

# Design Ideation Video

[Watch the Design Ideation Video](PASTE-VIDEO-LINK-HERE)
