---
title: Product Requirements
---

## Table of Contents

1. [Project Objective](#project-objective)
2. [Stakeholders](#stakeholders)
3. [Use Cases](#use-cases)
   - [User Story 1: Buzz Lightyear](#user-story-1-buzz-lightyear)
   - [User Story 2: John Doe](#user-story-2-john-doe)
4. [Design Aspects](#design-aspects)
   - [Hardware/Product Design](#hardwareproduct-design)
   - [Software/Functionality](#softwarefunctionality)
   - [Interactivity](#interactivity)
   - [Customization](#customization)
   - [Manufacturing](#manufacturing)
   - [Safety](#safety)
5. [Requirement Criteria Specifications](#requirement-criteria-specifications)
6. [Open Questions](#open-questions)

---

## Project Objective

This project aims to create a robotic leg that can be easily understood and leveraged so that other robotic enthusiasts can adapt and utilize this leg in their own systems and creations.

One of our goals is to create a leg that is easy to use, tweak, and modify from the original design. Users could purchase the physical leg to avoid building and wiring it themselves, or access the software and design files to modify the leg for their own projects.

[Back to Table of Contents](#table-of-contents)

---

## Stakeholders

- **Target Group:** Robotics enthusiasts of all ages looking to adapt existing systems into larger projects and products.
- **Target Purchaser:** Individuals, schools, or businesses looking to create or modify walking or crawling robotic systems.
- **Customer Service:** Prefers easy-to-repair, recyclable products and straightforward solutions to customer complaints.
- **Marketing & Sales Division:** Looks for unique selling points that can attract potential customers.
- **Retailers:** Prefer products that can withstand different storage conditions, including changes in temperature, vibration, humidity, and atmospheric pressure, with strong and compact packaging.

[Back to Table of Contents](#table-of-contents)

---

## Use Cases

### User Story 1: Buzz Lightyear

**Goal:** Create a multi-legged prop for a live-action film scene.

**Scenario:**

Buzz Lightyear is a prop master working on an upcoming horror film. He needs to control eight spider legs, so he purchases eight robotic legs and uses a custom setup rather than a mobile phone application.

Using the open API and Bluetooth control interface, Buzz bypasses the standard companion application and writes a custom script to synchronize the legs with the other components of the prop.

### User Story 2: John Doe

**Goal:** Build a custom quadruped or hexapod crawler without designing mechanical limbs from scratch.

**Scenario:**

John Doe is a 22-year-old working on a custom spider robot project. He purchases four assembled robotic legs so he can begin working on quadruped movement.

During testing, one of the structural links breaks. Because the leg uses off-the-shelf fasteners, PLA/PETG 3D-printed parts, and non-proprietary mechanical components, John can print a replacement part and install it using standard tools.

[Back to Table of Contents](#table-of-contents)

---

## Design Aspects

The product requirements use a priority scale from **P1 (lowest priority)** to **P10 (highest priority)**.

### Hardware/Product Design

- **1.1** The leg shall be constructed primarily from 3D-printed structural components to enable rapid iteration and low-cost design changes. (P10)
- **1.2** The leg shall use standard metal fasteners instead of adhesives or welds for joint assembly, allowing components to be disassembled and replaced without specialized tools. (P9)
- **1.3** The leg's structural components shall be printable using commonly available thermoplastics, such as PLA and PETG. (P8)
- **1.4** The leg's housing and joints shall be designed for disassembly using standard tools and removable fasteners. (P8)
- **1.5** The leg's printed components shall use single-material construction where possible to support recyclability. (P6)

### Software/Functionality

- **2.1** The leg's control software shall be written in Python to maximize accessibility for hobbyist and student developers. (P10)
- **2.2** The leg shall use industry-standard communication protocols, using UART for communication between the leg's controllers. (P9)
- **2.3** The leg's software shall be modular, separating motion control, sensor input, and communication functions. (P8)
- **2.4** The codebase shall include documentation and a setup guide allowing a first-time user to run a basic movement demonstration within one hour. (P7)

### Interactivity

- **3.1** The leg shall support wireless control through Bluetooth using a companion smartphone application as its primary user interaction method. (P10)
- **3.2** The control interface shall provide an open API or command set so users can create alternative control methods, such as gamepads, voice commands, or autonomous scripts. (P8)
- **3.3** The companion application shall provide diagnostic information, including connection status, battery level, and joint position. (P7)

### Customization

- **4.1** The leg's software and firmware shall be released under an open-source license to allow user modification. (P10)
- **4.2** The hardware design files, including CAD models and wiring diagrams, shall be publicly available. (P9)
- **4.3** The leg shall use a standardized hardware configuration while allowing users to modify components after purchase. (P7)
- **4.4** The design shall use commonly available off-the-shelf fasteners and connectors to simplify replacement and upgrades. (P8)

### Manufacturing

- **5.1** The leg's body shall be manufactured using 3D-printed components to reduce tooling costs and allow design revisions. (P10)
- **5.2** Electronic and mechanical components, including motors, fasteners, and bearings, shall be sourced as off-the-shelf parts. (P9)
- **5.3** Packaging shall withstand changes in temperature, humidity, vibration, and atmospheric pressure during normal shipping and storage. (P8)
- **5.4** Packaging shall be tamper-evident and resistant to theft and vandalism. (P7)
- **5.5** Packaging materials shall be recyclable or reusable where possible. (P5)

### Safety

- **6.1** The leg's actuators shall include current-limiting or stall-detection safeguards to prevent motor damage and reduce injury risks. (P10)
- **6.2** Exposed moving joints shall include guards or shields to reduce pinch-point risks. (P9)
- **6.3** The electrical system shall include over-voltage and over-current protection. (P9)
- **6.4** The software shall include a fail-safe stop state to prevent uncontrolled movement if communication is lost. (P9)
- **6.5** The leg's materials shall be non-toxic and free of sharp edges. (P7)

[Back to Table of Contents](#table-of-contents)

---

## Requirement Criteria Specifications

The following criteria describe how the team will verify that each product requirement has been met.

Verification methods include inspection, analysis, testing, and demonstration.

| Requirement | Requirement Criteria Specification | Verification Method |
|---|---|---|
| **1.1** | At least 75% of custom structural components, by part count, shall be 3D printed. | Inspection |
| **1.2** | Structural joints shall use removable metal fasteners and be disassembled using standard hand tools. | Inspection / Demonstration |
| **1.3** | Custom structural components shall be printable using PLA or PETG filament. | Inspection / Demonstration |
| **1.4** | A designated structural link shall be removable and reinstalled within 20 minutes. | Demonstration |
| **1.5** | Printed structural components shall use a single identified thermoplastic material where possible. | Inspection |
| **2.1** | The primary control software shall be written in Python and execute a basic movement command. | Inspection / Demonstration |
| **2.2** | UART communication between the controllers shall successfully transmit sensor and actuator data during 10 consecutive trials. | Test |
| **2.3** | Motion control, sensor input, and communication functions shall exist as separate software modules. | Inspection |
| **2.4** | A first-time user shall complete a basic movement demonstration within 60 minutes using the documentation. | Demonstration |
| **3.1** | The leg shall connect to a companion smartphone application through Bluetooth and execute a movement command. | Demonstration |
| **3.2** | The documented API or command set shall accept movement commands from an alternative control method. | Demonstration |
| **3.3** | The companion application shall display connection status, battery level, and joint-position information. | Demonstration |
| **4.1** | The software repository shall contain an open-source license and accessible source files. | Inspection |
| **4.2** | CAD models and wiring diagrams shall be available in the published documentation. | Inspection |
| **4.3** | The completed leg shall use a documented standard hardware configuration while allowing component replacement. | Inspection / Demonstration |
| **4.4** | Fasteners and connectors shall be commercially available and non-proprietary. | Inspection |
| **5.1** | Custom body components designated for additive manufacturing shall be 3D printed. | Inspection |
| **5.2** | Electronic and mechanical components shall have commercially available replacements or documented equivalents. | Inspection |
| **5.3** | The packaged leg shall remain functional and show no structural damage following defined shipping-condition tests. | Test |
| **5.4** | Packaging shall include a tamper-evident feature. | Inspection / Demonstration |
| **5.5** | Packaging materials shall be identified as recyclable or reusable where feasible. | Inspection |
| **6.1** | Current-limiting or stall-detection safeguards shall activate during controlled testing before an actuator exceeds its rated limits. | Test |
| **6.2** | Accessible pinch points shall include physical guards or shields. | Inspection |
| **6.3** | The power system shall include appropriate over-voltage and over-current protection. | Inspection / Analysis |
| **6.4** | Disconnecting Bluetooth during movement shall trigger the fail-safe state and stop commanded movement. | Test |
| **6.5** | Manufactured surfaces shall be inspected for sharp edges, and materials shall be documented as non-toxic for their intended use. | Inspection |

[Back to Table of Contents](#table-of-contents)

---

## Open Questions

- Can we make the product more recyclable and repairable through the use of ZIF connectors and glue-free assembly?
- How can we reduce the risk of battery or power-supply failures?
- Should the software and communication requirements be updated to match the team's current PIC Nano, UART, and IR remote design?
- What power source will be selected for the final prototype?
- Which actuators and motor drivers will be used?

[Back to Table of Contents](#table-of-contents)

