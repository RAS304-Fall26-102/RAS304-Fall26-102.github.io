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

<!-- ## Use Cases  EXAMPLE

### User Story #1: Jenna

Jenna is a 33-year-old executive who regularly visits a bar for lunch to blow off some steam. The bar is often loud with people, but it is paramount that she can hold business conversations over the phone there. Then again, she does not want to miss out on the atmosphere and be able to hear the waiters as well. Her new Apple wireless earphones allow her to switch instantly between a mode where she can fully focus on the phone conversation and a mode where the phone call and environmental sound are seamlessly combined. They also allow her to rapidly adjust the volume on the earbuds themselves without having to take out her phone.

Jenna occasionally visits the bar in the evenings. She is a big fan of the L.A. Lakers, and whenever they play, she streams the live footage through her phone. Her new earbuds allow her to easily switch to hearing everything around her and streaming the match commentary without having to ever take the earbuds out.  She sometimes gets compliments on how stylish the earbuds look on her, and she wouldn’t want to miss out on hearing those either.

### User Story #2

...

## Aspects

The new product design will be based on that of the AirPods with improvements based on the following requirements. The **P1 - P10** is the "code" to indicate the priority of the requirement, from low to high. -->

## Design Aspects

   1. **Hardware/Product Design**
   * 1.1 The Leg shall be constructed primarily from 3D-printed structural components to enable rapid iteration and low-cost design changes. (P10)
   * 1.2 The Leg shall use standard metal fasteners (not adhesives or welds) for joint assembly, so components can be disassembled and replaced without specialized tools. (P9)
   * 1.3 The Leg's structural components shall be printable in commonly available thermoplastics (e.g., PLA, PETG) to keep replacement parts accessible to hobbyists. (P8)
   * 1.4 The Leg's housing and joints shall be designed for tool-based disassembly (screws/fasteners only) to support customer-service repairability. (P8)
   * 1.5 The Leg's printed components shall use single-material construction where possible to support end-of-life recyclability. (P6)

2. **Software/Functionality**
   * 2.1 The Leg's control software shall be written in Python to maximize accessibility for hobbyist and student developers. (P10)
   * 2.2 The Leg shall use industry-standard communication protocols (UART and I2C) for sensor and actuator intercommunication, to ease integration with third-party components. (P9)
   * 2.3 The Leg's software shall be modular, separating motion control, sensor input, and communication layers, so individual modules can be modified without rewriting the full stack. (P8)
   * 2.4 The Leg's codebase shall include inline documentation and a setup guide sufficient for a first-time user to run a basic movement demo within one hour. (P7)

3. **Interactivity**
   * 3.1 The Leg shall support wireless control via Bluetooth from a companion smartphone application as the primary user interaction method. (P10)
   * 3.2 The Leg's control interface shall expose an open API/command set so users can build alternative control schemes (e.g., gamepad, voice, autonomous scripts) beyond the phone app. (P8)
   * 3.3 The companion app shall provide basic diagnostic feedback (connection status, battery level, joint position) to support ease of troubleshooting. (P7)

4. **Customization**
   * 4.1 The Leg's software and firmware shall be released under an open-source license to allow unrestricted modification by end users. (P10)
   * 4.2 The Leg's hardware design files (CAD models, wiring diagrams) shall be published openly to support customization and replacement-part fabrication by end users. (P9)
   * 4.3 The Leg shall ship with a fixed, standardized hardware configuration to keep manufacturing and initial support costs predictable, while allowing full post-purchase modification. (P7)
   * 4.4 The Leg's design shall use commonly available off-the-shelf fasteners and connectors (not proprietary parts) to simplify sourcing of replacement or upgraded components. (P8)

5. **Manufacturing**
   * 5.1 The Leg's body shall be manufactured using 3D-printed parts to minimize tooling costs and allow rapid design revisions. (P10)
   * 5.2 The Leg's electronic and mechanical subcomponents (motors, fasteners, bearings) shall be sourced as off-the-shelf parts to ensure long-term replaceability. (P9)
   * 5.3 The Leg's packaging shall be designed to withstand variation in temperature, humidity, vibration, and atmospheric pressure encountered during standard retail shipping and storage. (P8)
   * 5.4 The Leg's packaging shall be tamper-evident and resistant to theft and vandalism to meet retailer handling requirements. (P7)
   * 5.5 The Leg's packaging materials shall be recyclable or reusable where feasible, in line with sustainability-focused customer service goals. (P5)

6. **Safety**
   * 6.1 The Leg's actuators shall include current-limiting or stall-detection safeguards to prevent motor burnout or injury from pinch points during operation. (P10)
   * 6.2 The Leg's exposed moving joints shall be shielded or guarded to reduce pinch-point risk during normal handling, particularly for younger hobbyist users. (P9)
   * 6.3 The Leg's electronics shall operate within a battery/power system that includes over-voltage and over-current protection to prevent fire or component damage. (P9)
   * 6.4 The Leg's default software behavior shall include a fail-safe stop state (e.g., loss of Bluetooth connection halts motion) to prevent uncontrolled movement. (P9)
   * 6.5 The Leg's materials shall be non-toxic and free of sharp edges from the printing/manufacturing process, given the target audience includes younger enthusiasts. (P7)


<!-- ## Requirement Criteria Specifications EXAMPLE

* 1.1.1 - Regulate system power from 9 volts to 5 volts
* 1.1.2 - Provide over-amperage project to not exceed 1.5 amps.

## Open Questions

* Can we move towards a recyclable and repairable product, for example, with ZIF connectors and glue-free assembly?
* Can we improve on failing or self-igniting batteries? -->

