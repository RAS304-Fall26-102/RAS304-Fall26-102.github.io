
---
title: Block Diagram, Process Diagram, and Message Structure
---

# Block Diagram, Process Diagram, and Message Structure

## Table of Contents

1. [Team Block Diagram](#team-block-diagram)
2. [Subsystem Responsibilities](#subsystem-responsibilities)
3. [Connection Layout](#connection-layout)
4. [Hardware and Sensors](#hardware-and-sensors)
5. [Process Diagram](#process-diagram)
6. [UART Communication](#uart-communication)
7. [Message Structure](#message-structure)
8. [Indicator Lights](#indicator-lights)
9. [Power Distribution](#power-distribution)
10. [Safety and Fault Handling](#safety-and-fault-handling)
11. [Design Discussion](#design-discussion)
12. [Items Still Being Finalized](#items-still-being-finalized)

---

## Team Block Diagram

Our team is designing one robotic leg that could eventually be used as part of a six-legged spider robot.

The leg is divided into four subsystems, with each teammate responsible for one PIC18F57Q43 Curiosity Nano microcontroller.

We are using a hub-and-spoke layout, meaning Preston's Nano acts as the main controller while the other three Nanos connect directly to it.

Preston's Nano will handle leg kinematics and movement coordination. The other Nanos will control their assigned motors, actuators, and sensors.

### Original Team 102 Block Diagram

![Team 102 Block Diagram](images/team-block-diagram.png)

**Figure 1:** Original Team 102 block diagram showing Preston's main controller connected to Akshan's servo motor, Bex's linear actuator and pressure sensor, and Kaushik's linear actuator and IMU.

[Download the editable draw.io file](images/team-block-diagram.drawio)

This diagram shows our original subsystem layout and the 8-pin ribbon cable connections between the four boards.

As the project develops, we will update the electrical connections and software communication to match our final hardware choices.

[Back to Table of Contents](#table-of-contents)

---

## Subsystem Responsibilities

Each teammate is responsible for developing and testing the software and hardware for their assigned subsystem.

| Teammate | Controller | Responsibilities |
|---|---|---|
| Preston Potts | Main Processor Nano | Leg kinematics, IR remote input, movement coordination, UART communication, and global status |
| Akshan Bhelkar | Driver Nano 1 | Servo motor control, joint limit monitoring, and proposed diagnostic display |
| Bex Baker | Driver Nano 2 | Linear actuator A, pressure sensor, joint limit switches, and joint status |
| Kaushik Gunasekaren | Driver Nano 3 | Linear actuator B, IMU, joint limit switches, and joint status |

### Main Processor Nano - Preston

Preston's Nano will be responsible for coordinating the overall movement of the robotic leg.

It will:

- Receive commands from an IR remote.
- Calculate the required joint positions.
- Send movement commands to the other Nanos.
- Receive feedback from the joint controllers.
- Monitor the overall system status.
- Send stop commands when a fault is detected.

### Driver Nano 1 - Akshan

Akshan's Nano will control the servo motor.

It will:

- Receive servo position commands.
- Generate the servo control signal.
- Monitor the joint's limit switches.
- Send status information to Preston's Nano.
- Support the proposed diagnostic display.

The display model and programming details are still TBD.

### Driver Nano 2 - Bex

Bex's Nano will control Linear Actuator A and read the pressure sensor.

It will:

- Receive movement commands.
- Control the linear actuator through a motor driver.
- Read pressure sensor information.
- Monitor two limit switches.
- Send feedback to Preston's Nano.
- Control the joint status indicator.

### Driver Nano 3 - Kaushik

Kaushik's Nano will control Linear Actuator B and read the IMU.

It will:

- Receive movement commands.
- Control the linear actuator through a motor driver.
- Read IMU measurements.
- Monitor two limit switches.
- Send feedback to Preston's Nano.
- Control the joint status indicator.

[Back to Table of Contents](#table-of-contents)

---

## Connection Layout

Our team plans to connect the four Nanos using 8-pin ribbon cables.

Each spoke Nano connects directly to Preston's main controller.

### Hub Connections

| Hub Connector | Connected Nano | Purpose |
|---|---|---|
| Connector 1 | Akshan | Servo commands and feedback |
| Connector 2 | Bex | Linear actuator A commands and pressure feedback |
| Connector 3 | Kaushik | Linear actuator B commands and IMU feedback |

The original class-standard connector layout uses:

- Pins 1-5 for digital signals.
- Pins 6-7 for analog signals.
- Pin 8 for ground.

### Proposed Ribbon Cable Pin Assignments

| Pin | Type | Akshan | Bex | Kaushik |
|:---:|---|---|---|---|
| 1 | Digital | UART TX | UART TX | UART TX |
| 2 | Digital | UART RX | UART RX | UART RX |
| 3 | Digital | Reserved | Reserved | Reserved |
| 4 | Digital | Reserved | Reserved | Reserved |
| 5 | Digital | Reserved | Reserved | Reserved |
| 6 | Analog | Reserved | Reserved | Reserved |
| 7 | Analog | Reserved | Reserved | Reserved |
| 8 | Ground | Common ground | Common ground | Common ground |

**Note:** These are proposed signal assignments, not finalized wiring. The TX and RX directions must be verified for both ends of each cable.

The exact microcontroller pin assignments will be finalized when the electrical schematics are completed.

[Back to Table of Contents](#table-of-contents)

---

## Hardware and Sensors

Our robotic leg will use three motorized joints controlled by the four Nanos.

### Planned Hardware

| Component | Assigned Nano | Purpose |
|---|---|---|
| IR receiver | Preston | Receive commands from a TV remote |
| RGB/status LED | Preston | Display overall system status |
| Servo motor | Akshan | Control one joint |
| Diagnostic display | Akshan | Display system information |
| Linear actuator A | Bex | Control one joint |
| Pressure sensor | Bex | Detect pressure or contact |
| Linear actuator B | Kaushik | Control one joint |
| IMU | Kaushik | Measure motion and orientation |
| Limit switches | Joint controllers | Detect joint travel limits |
| White LED | Joint controllers | Display joint status |

### Limit Switches

Our current plan includes two limit switches for each joint.

Since the leg has three joints, we plan to use six limit switches total.

The switches will help prevent the joints from moving beyond their allowed mechanical range.

### Pressure Sensor

The pressure sensor will be connected to Bex's Nano.

It will help detect contact or pressure at the robotic leg.

The final sensor location and pressure thresholds have not been determined.

### IMU

The IMU will be connected to Kaushik's Nano.

It will provide information about the leg's movement and orientation.

The exact IMU model and communication interface are still TBD.

[Back to Table of Contents](#table-of-contents)

---

## Process Diagram

The software for the robotic leg will be divided among the four Nanos.

The main controller will calculate the movement commands, while the other three controllers will operate their assigned hardware.

The complete software flow diagram is included on our Software Proposal page.

### Main Controller Process

1. Initialize the Nano.
2. Initialize communication.
3. Initialize the IR receiver and indicator lights.
4. Wait for a user command.
5. Read the IR remote input.
6. Calculate the required joint positions.
7. Send commands to the three driver Nanos.
8. Receive sensor and joint feedback.
9. Check for faults or stop commands.
10. Update the global status indicator.
11. Repeat the process.

### Joint Controller Process

1. Initialize the Nano.
2. Initialize communication.
3. Initialize the assigned actuator and sensors.
4. Wait for a movement command.
5. Check the command and joint limits.
6. Control the assigned motor or actuator.
7. Read sensor information.
8. Monitor for faults.
9. Send feedback to the main Nano.
10. Repeat the process.

Each driver Nano will operate independently while communicating with the main controller.

[Back to Table of Contents](#table-of-contents)

---

## UART Communication

Our current communication plan is to use UART between the four Nanos.

Preston's main Nano will communicate with each of the three driver Nanos through a separate connection.

### Communication Layout

| Connection | Commands | Feedback |
|---|---|---|
| Preston to Akshan | Servo target position | Servo status and limit information |
| Preston to Bex | Linear actuator A command | Pressure sensor and limit information |
| Preston to Kaushik | Linear actuator B command | IMU and limit information |

Each UART connection requires:

- TX (transmit)
- RX (receive)
- Common ground

The TX signal from one Nano connects to the RX signal on the other Nano.

The final UART channels, pin assignments, baud rate, and communication settings still need to be verified.

[Back to Table of Contents](#table-of-contents)

---

## Message Structure

The Nanos will need a consistent message format so they can send and receive commands correctly.

The following message structure is our current proposal.

### Command Message

| Field | Purpose |
|---|---|
| Start | Identifies the beginning of a message |
| Destination | Identifies the receiving Nano |
| Command | Identifies the requested action |
| Target Position | Contains the requested joint position |
| Sequence Number | Identifies the command |
| Error Check | Helps detect communication errors |

### Feedback Message

| Field | Purpose |
|---|---|
| Start | Identifies the beginning of a message |
| Source | Identifies the sending Nano |
| Joint Status | Reports the joint's operating state |
| Sensor Data | Contains pressure or IMU information |
| Limit Status | Reports limit switch activity |
| Fault Status | Reports detected errors |
| Error Check | Helps detect communication errors |

### Proposed Command Types

| Command | Description |
|---|---|
| MOVE | Move a joint toward a requested position |
| STOP | Stop commanded joint movement |
| STATUS | Request current controller status |
| HOME | Start an approved joint homing procedure |
| RESET | Clear an eligible fault after safety checks |

### Proposed Feedback Types

| Feedback | Description |
|---|---|
| READY | Controller is initialized |
| MOVING | Joint is moving |
| POSITION | Reports position information |
| SENSOR | Reports sensor measurements |
| LIMIT | A joint limit is active |
| FAULT | A fault has been detected |
| STOPPED | Joint movement has stopped |

These message types are proposals. The exact encoding, field sizes, and error-checking method still need to be finalized.

[Back to Table of Contents](#table-of-contents)

---

## Indicator Lights

Our team plans to use different colored LEDs to indicate the status of the robotic leg.

| LED Color | Purpose |
|---|---|
| Yellow | Power indicator |
| Green | Board power indicator |
| Blue | Global status indicator |
| White | Joint status indicator |

### Yellow LED

The yellow LED indicates that power is present.

### Green LED

The green LED indicates that the board is receiving power.

### Blue LED

The blue LED will indicate the overall status of the robotic leg.

### White LED

The white LED will indicate the status of an individual joint.

The exact behavior of the blue and white LEDs will be determined during software development.

[Back to Table of Contents](#table-of-contents)

---

## Power Distribution

Our team would prefer to use an external 12V DC power supply rather than relying on a computer USB connection.

However, the final power supply has not been selected.

Some early schematics show a 9V power source as a placeholder. This is not the confirmed power source for the final design.

### Proposed Power Arrangement

1. An external DC supply provides power to the robotic leg.
2. Power distribution circuitry supplies the individual subsystems.
3. Voltage regulators provide the correct voltage for the Nanos and sensors.
4. Motor drivers receive the voltage required by the selected actuators.
5. The controllers share a common ground reference.

The final supply voltage, current requirements, voltage regulators, and protection components will be determined after the actuator models are selected.

**Power Supply Status: TBD**

[Back to Table of Contents](#table-of-contents)

---

## Safety and Fault Handling

Our team plans to include several safety features in the robotic leg.

### Joint Limit Protection

Each joint controller will monitor its two limit switches.

If a limit switch is activated, the controller will prevent further movement in the restricted direction.

### Communication Loss

If a Nano stops receiving valid commands for longer than the selected timeout, it should enter a safe state.

The affected joint should stop commanded movement until communication is restored and the controller is ready.

### Invalid Commands

Each controller should check incoming commands before moving its actuator.

Commands outside the allowed range should be rejected or limited.

### Fault Reporting

The joint controllers should send fault information to Preston's Nano.

Possible faults include:

- Communication loss
- Joint limit reached
- Invalid movement command
- Sensor failure
- Motor stall or overload
- Position feedback failure

The exact response to each fault will depend on the selected hardware.

[Back to Table of Contents](#table-of-contents)

---

## Design Discussion

### Minimizing Interconnections

Using a hub-and-spoke layout allows each Nano to communicate directly with Preston's main controller.

UART communication can reduce the number of individual control and sensor signals that need to travel between boards.

Each driver Nano will process its own sensor readings and control its assigned actuator.

### Why Hub and Spoke?

The robotic leg has three joints that need to work together.

Preston's Nano will calculate the required movement for all three joints and send commands to the driver Nanos.

This allows the main controller to focus on movement coordination while the other Nanos handle their local hardware.

### Independent Joint Control

The three driver Nanos will be able to operate independently.

Each Nano can receive commands, move its assigned actuator, monitor sensors, and return feedback without waiting for another joint to finish unless synchronization is required.

### Risk of Losing a Controller

Preston's Nano is the central controller, making it an important part of the system.

If the main controller fails, coordinated movement cannot continue.

If one driver Nano fails, the affected joint will no longer be controlled correctly.

The team should make sure the system enters a safe state when communication or controller failures occur.

Keeping the software modular and documented will also make it easier to replace a controller if needed.

[Back to Table of Contents](#table-of-contents)

---

## Items Still Being Finalized

| Item | Current Status |
|---|---|
| Main controller | PIC18F57Q43 Curiosity Nano |
| Communication protocol | UART – current plan |
| Ribbon cable layout | 8-pin connectors |
| UART pin assignments | TBD |
| UART message format | Proposed |
| Servo model | TBD |
| Linear actuator models | TBD |
| Motor drivers | TBD |
| Pressure sensor model | TBD |
| IMU model | TBD |
| Diagnostic display | TBD |
| Limit switches | Two per joint planned |
| Power source | TBD – 12V DC preferred |
| Voltage regulators | TBD |
| LED status behavior | Partially defined |
| Fault timeouts | TBD |
| Joint position feedback | TBD |

These details will be updated as our team finalizes the electrical schematics and software.

[Back to Table of Contents](#table-of-contents)
