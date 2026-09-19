---
title: Product Requirements
---

## Project Objective

This project aims to create a robotic leg that can be easily understood and leveraged so that other robotic enthusiasts can adapt and utilize this leg in their own systems and creations. One of our goals is to create a leg that is easily understood and easy to use, tweak, and modify from the original design so that others can either buy our physical leg to avoid the building and wiring, or they can acquire the software, modify the design to their needs, and then use our original design in their own system, ambitions, work, or entertainment.

## Stakeholders

* **Target group:** Robotics enthusiasts of all ages looking to adapt pre-existing systems into larger projects and products.
* **Target purchaser:** Individuals, schools, or businesses looking to create or modify a walking or crawling robotics system. 
* **Customer service:** Prefers easy-to-repair, recyclable products, and easy-to-fix complaints.
* **Marketing & Sales division:** Looks for unique selling points to advertise and show off to entice potential and active consumers.
* **Retailers:** Prefer products that can withstand a wide range of storage conditions, including variations in temperature, vibration, humidity, and atmospheric pressure, and have strong, compact, theft and vandalism-proof packaging.

## Use Cases

### User Story #1 : Buzz Lightyear

**Goal:** Create a multi-legged prop for a live-action film scene.  

**Scenario:** Buzz Lightyear is a Prop Master on an upcomming horror film set. He needs to control eight spider legs, he just buys eight of them and uses a custom setup rather than a mobile phone app. Using the open API and Bluetooth control interface, Jordan bypasses the standard companion application and writes a custom script to sync the leg's movement with his choice of external components and body.  

### User Story #2 : Jhon Doe

**Goal:** Wants to build a custom quadruped or hexaped crawler without designing mechanical limbs from scratch.  

**Scenario:** Jhon Doe is a 22 year old working on a custom spider bot project. He buys four assembled physical legs so he can jump straight into quadruped locomotion. During a bench test, one of the links break becuase of his mistakes. Because the leg uses off the shelf fasteners, PLA/PETG 3D-printed parts, and non-proprietary mechanical components, Jhon uses his home 3D printer and standard Allen M-size bolts to swap out the damaged link in 20 minutes without needing specialized tools or replacing the whole unit.


## Aspects

The new product design will be based on that of the AirPods with improvements based on the following requirements. The **P1 - P10** is the "code" to indicate the priority of the requirement, from low to high. -->

## Design Aspects
   The **P1 - P10** is the "code" to indicate the priority of the requirement, from low to high.

 **Hardware/Product Design**<br>

   * 1.1 The Leg shall be constructed primarily from 3D-printed structural components to enable rapid iteration and low-cost design changes. (P10)<br>
   * 1.2 The Leg shall use standard metal fasteners (not adhesives or welds) for joint assembly, so components can be disassembled and replaced without specialized tools. (P9)<br>
   * 1.3 The Leg's structural components shall be printable in commonly available thermoplastics (e.g., PLA, PETG) to keep replacement parts accessible to hobbyists. (P8)<br>
   * 1.4 The Leg's housing and joints shall be designed for tool-based disassembly (screws/fasteners only) to support customer-service repairability. (P8)<br>
   * 1.5 The Leg's printed components shall use single-material construction where possible to support end-of-life recyclability. (P6)<br>

**Software/Functionality**

   * 2.1 The Leg's control software shall be written in Python to maximize accessibility for hobbyist and student developers. (P10)<br>

   * 2.2 The Leg shall use industry-standard communication protocols (UART and I2C) for sensor and actuator intercommunication, to ease integration with third-party components. (P9)<br>

   * 2.3 The Leg's software shall be modular, separating motion control, sensor input, and communication layers, so individual modules can be modified without rewriting the full stack. (P8)<br>

   * 2.4 The Leg's codebase shall include inline documentation and a setup guide sufficient for a first-time user to run a basic movement demo within one hour. (P7)<br>

**Interactivity**<br>

   * 3.1 The Leg shall support wireless control via Bluetooth from a companion smartphone application as the primary user interaction method. (P10)<br>
   * 3.2 The Leg's control interface shall expose an open API/command set so users can build alternative control schemes (e.g., gamepad, voice, autonomous scripts) beyond the phone app. (P8)<br>
   * 3.3 The companion app shall provide basic diagnostic feedback (connection status, battery level, joint position) to support ease of troubleshooting. (P7)<br>

**Customization**<br>

   * 4.1 The Leg's software and firmware shall be released under an open-source license to allow unrestricted modification by end users. (P10)<br>

   * 4.2 The Leg's hardware design files (CAD models, wiring diagrams) shall be published openly to support customization and replacement-part fabrication by end users. (P9)<br>

   * 4.3 The Leg shall ship with a fixed, standardized hardware configuration to keep manufacturing and initial support costs predictable, while allowing full post-purchase modification. (P7)<br>

   * 4.4 The Leg's design shall use commonly available off-the-shelf fasteners and connectors (not proprietary parts) to simplify sourcing of replacement or upgraded components. (P8)<br>

**Manufacturing**<br>

   * 5.1 The Leg's body shall be manufactured using 3D-printed parts to minimize tooling costs and allow rapid design revisions. (P10)<br>

   * 5.2 The Leg's electronic and mechanical subcomponents (motors, fasteners, bearings) shall be sourced as off-the-shelf parts to ensure long-term replaceability. (P9)<br>

   * 5.3 The Leg's packaging shall be designed to withstand variation in temperature, humidity, vibration, and atmospheric pressure encountered during standard retail shipping and storage. (P8)<br>

   * 5.4 The Leg's packaging shall be tamper-evident and resistant to theft and vandalism to meet retailer handling requirements. (P7)<br>

   * 5.5 The Leg's packaging materials shall be recyclable or reusable where feasible, in line with sustainability-focused customer service goals. (P5)<br>

**Safety**

   * 6.1 The Leg's actuators shall include current-limiting or stall-detection safeguards to prevent motor burnout or injury from pinch points during operation. (P10)<br>

   * 6.2 The Leg's exposed moving joints shall be shielded or guarded to reduce pinch-point risk during normal handling, particularly for younger hobbyist users. (P9)<br>

   * 6.3 The Leg's electronics shall operate within a battery/power system that includes over-voltage and over-current protection to prevent fire or component damage. (P9)<br>

   * 6.4 The Leg's default software behavior shall include a fail-safe stop state (e.g., loss of Bluetooth connection halts motion) to prevent uncontrolled movement. (P9)<br>

   * 6.5 The Leg's materials shall be non-toxic and free of sharp edges from the printing/manufacturing process, given the target audience includes younger enthusiasts. (P7)<br>



## Requirement Criteria Specifications

The following Requirement Criteria Specifications define how each product requirement will be verified. Each criterion provides a measurable or observable method for determining whether the final robotic leg meets the corresponding requirement. Verification will be completed through inspection, analysis, testing, or demonstration.

| Requirement | Requirement Criteria Specification | Verification Method |
| --- | --- | --- |
| **1.1** | At least 75% of the Leg's custom structural components, by part count, shall be manufactured using 3D printing. | Inspection |
| **1.2** | All structural joints shall use removable metal fasteners and shall be capable of disassembly using standard hand tools without cutting, welding, or destroying components. | Inspection / Demonstration |
| **1.3** | All custom 3D-printed structural components shall be successfully printable using commonly available PLA or PETG filament. | Inspection / Demonstration |
| **1.4** | A designated structural link shall be removable and reinstalled using standard hand tools in 20 minutes or less. | Demonstration |
| **1.5** | Each 3D-printed structural component shall use a single identified thermoplastic material where possible. | Inspection |
| **2.1** | The Leg's primary control software shall be written in Python and shall successfully execute a basic movement command. | Inspection / Demonstration |
| **2.2** | The Leg shall successfully transmit required sensor and actuator data using the implemented UART and I2C communication interfaces during 10 consecutive communication trials without communication failure. | Test |
| **2.3** | Motion control, sensor input, and communication functions shall exist as separately identifiable software modules that can be modified independently. | Inspection |
| **2.4** | A first-time user shall be able to follow the provided documentation and successfully run the basic movement demonstration within 60 minutes. | Demonstration |
| **3.1** | The Leg shall successfully connect to the companion smartphone application through Bluetooth and execute at least one movement command wirelessly. | Demonstration |
| **3.2** | The documented API or command set shall successfully accept a movement command from at least one control method other than the companion smartphone application. | Demonstration |
| **3.3** | The companion application shall display connection status, battery level, and joint-position information during operation. | Demonstration |
| **4.1** | The software and firmware repository shall contain an identified open-source license and provide access to the source files required for user modification. | Inspection |
| **4.2** | The published project documentation shall provide accessible CAD models and wiring diagrams required to reproduce or modify the Leg. | Inspection |
| **4.3** | The completed Leg shall use one documented standard hardware configuration while allowing components to be removed or replaced after assembly. | Inspection / Demonstration |
| **4.4** | Fasteners and connectors used in the Leg shall be commercially available, non-proprietary components identifiable by standard part specifications. | Inspection |
| **5.1** | All custom body components designated for additive manufacturing shall be successfully manufactured using 3D printing. | Inspection |
| **5.2** | Motors, fasteners, bearings, and other designated electronic and mechanical subcomponents shall have commercially available replacement parts or documented equivalents. | Inspection |
| **5.3** | The packaged Leg shall show no visible structural damage and shall remain functional following the team's defined environmental and shipping-condition tests. | Test |
| **5.4** | The final packaging shall contain a tamper-evident feature that provides visible evidence after the package has been opened or altered. | Inspection / Demonstration |
| **5.5** | Packaging materials shall be identified and documented as recyclable or reusable where feasible. | Inspection |
| **6.1** | When an actuator is intentionally stalled during a controlled test, the current-limiting or stall-detection safeguard shall activate and stop or limit actuator drive before the actuator exceeds its rated operating limits. | Test |
| **6.2** | All identified accessible pinch points shall include a physical shield or guard that prevents direct contact with the moving joint during normal handling. | Inspection |
| **6.3** | The Leg's power system shall include documented over-voltage and over-current protection appropriate for the rated voltage and current of the selected electronics. | Inspection / Analysis |
| **6.4** | Disconnecting the Bluetooth connection while the Leg is moving shall cause the system to enter its fail-safe state and stop commanded movement. | Test |
| **6.5** | All user-accessible manufactured surfaces shall be visually and physically inspected for sharp edges, and the selected structural materials shall have documentation identifying them as non-toxic for their intended use. | Inspection |

## Open Questions

* Can we move towards a recyclable and repairable product, for example, with ZIF connectors and glue-free assembly?
* Can we improve on failing or self-igniting batteries? -->

