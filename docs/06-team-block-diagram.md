

# Block Diagram, Process Diagram, and Message Structure

This page explains the proposed hardware organization, software processes, and communication between the four PIC18F57Q43 Curiosity Nano microcontrollers used to control one robotic spider leg.

The team is responsible for designing and building one leg, which could eventually become part of a six-legged walking robot.

## Table of Contents

1. [Team Block Diagram](#team-block-diagram)
2. [Subsystem Responsibilities](#subsystem-responsibilities)
3. [Process Diagram](#process-diagram)
4. [Communication and Message Structure](#communication-and-message-structure)
5. [Sensors and Actuators](#sensors-and-actuators)
6. [Safety and Error Handling](#safety-and-error-handling)

---

## Team Block Diagram

The system uses four Curiosity Nano microcontrollers. One Nano handles the main calculations and coordinates the other three Nanos, which control individual motors, actuators, and sensors.

### Team 102 Block Diagram

![Original Team 102 Block Diagram](images/team-block-diagram.png)

*Figure 1: Team 102 block diagram showing the main controller (Preston) and three driver controllers (Akshan, Bex, Kaushik). Each link is an 8-pin ribbon cable carrying UART and a ground reference; every board has its own power supply.*

Block diagram source: [draw.io source (ZIP)](images/team-block-diagram-source.zip) · [draw.io file](images/team-block-diagram.drawio)

The main Nano acts as the central controller. The other Nanos receive movement commands and return sensor information.

Each driver Nano connects to its own connector on the main Nano with an 8-pin ribbon cable. The cables carry only the UART link (pin 1: commands to the driver, pin 2: feedback to the main Nano) and a ground reference on pin 8. No power is shared between boards: each board has its own supply.

### How the Block Diagram Was Structured

**Hub and spoke.** The kinematics have to coordinate every joint of the leg, so one central board (Preston's main Nano) computes them and sends commands out to the three joint boards. Each driver board has its own direct cable to the main Nano, so a fault on one cable doesn't cut off the other joints.

**One board per joint.** Each driver Nano owns one joint and the sensor that goes with it: Akshan the servo, Bex linear actuator A and the pressure sensor, and Kaushik linear actuator B and the IMU. This keeps motion control, sensing and communication separated, as Requirement 2.3 asks, and lets each teammate design, test and document a board independently.

**Minimal interconnections.** Each link needs at most two signal pins plus ground: UART receive for the command and UART transmit for feedback. Pins 3&ndash;7 stay free on every cable for future signals. Using UART on every link meets Requirement 2.2 (a standard communication protocol), and keeping power off the ribbon means a fault on one board's supply can't damage the others.

**Risk of losing a teammate.** If a driver board is lost, only that joint or sensor is affected, and the rest of the leg can still be commanded. The main Nano is the single point of failure: without it, no kinematics commands are generated. To reduce that risk, the kinematics code should be written so it can be moved onto another teammate's Nano if needed.

**How it meets the product requirements.** Separate boards with standard connectors support repair and modification (Requirements 4.3 and 4.4). The UART links meet Requirement 2.2. Each driver stops its actuator if UART commands stop arriving, which supports the fail-safe stop in Requirement 6.4.

---

## Subsystem Responsibilities

Each team member is responsible for a different portion of the robotic leg.

| Team Member | Controller | Responsibilities |
|---|---|---|
| Preston | Main Nano | Kinematics, IR remote, RGB LED, communication |
| Akshan | Driver Nano 1 | Servo motor and proposed display |
| Bex | Driver Nano 2 | Linear actuator A, pressure sensor, status LED |
| Kaushik | Driver Nano 3 | Linear actuator B with slide-pot position feedback and stall detection, LIS3DH IMU (jerk and impulse), UART feedback |

### Main Nano — Preston

The main controller is responsible for:

- Receiving commands from the IR remote
- Calculating the desired leg position
- Performing kinematics calculations
- Sending movement commands to the driver Nanos
- Receiving sensor feedback
- Monitoring system status
- Controlling the RGB status LED
- Handling communication faults

### Driver Nano 1 — Akshan

This controller is responsible for:

- Receiving servo position commands
- Controlling the servo motor
- Reporting motor status
- Operating the proposed diagnostic display

The final servo model and display are still being selected.

### Driver Nano 2 — Bex

This controller is responsible for:

- Receiving movement commands
- Controlling linear actuator A
- Reading the pressure sensor
- Controlling a local status LED
- Sending sensor information to the main Nano

### Driver Nano 3 — Kaushik

This controller is responsible for:

- Receiving linear actuator B position commands from the main Nano over UART
- Controlling linear actuator B (DFRobot FIT0577 N20 lead-screw motor) through a DRV8833 motor driver
- Reading a slide potentiometer for the actuator's position (closed-loop control)
- Monitoring motor current for stall detection (0.61 A current limit)
- Reading the LIS3DH IMU (accelerometer) and computing jerk and impulse
- Sending IMU data and actuator status to the main Nano over UART

Driver Nano 3 is powered by its own 9 V supply. Its only connection to the main Nano is the UART link (pins 1 and 2 of the ribbon cable) and a ground reference (pin 8). Full details are on [Kaushik's datasheet](https://kaushikgunasekaren.github.io/kgunase7_RAS304_F26/).

---

## Process Diagram

The proposed process begins when the system is powered on.

The main Nano initializes its hardware and communication, reads user input, calculates the required movement, and sends commands to the driver Nanos.

### Main Controller Process

1. Start the system.
2. Initialize the microcontroller.
3. Initialize communication with the driver Nanos.
4. Read commands from the IR remote.
5. Determine the desired leg position.
6. Calculate the required joint positions.
7. Send movement commands to the driver Nanos.
8. Receive sensor feedback.
9. Check for faults and movement limits.
10. Update the RGB status LED.
11. Repeat the process.

### Driver Controller Process

1. Initialize the assigned hardware.
2. Wait for a command from the main Nano.
3. Check the command against movement limits.
4. Control the assigned motor or actuator.
5. Read the connected sensors.
6. Check the joint position against its allowed range.
7. Send feedback to the main Nano.
8. Repeat until the system is stopped.

The driver Nanos are intended to operate independently after receiving valid commands, without waiting unnecessarily for the other drivers.

---

## Communication and Message Structure

The team currently plans to use UART communication between the Nanos.

UART allows the microcontrollers to send movement commands and return sensor information using serial communication.

Each link uses UART on ribbon pins 1 and 2 with a ground reference on pin 8. The baud rate has not been finalized.

### Communication Overview

| Sender | Receiver | Information |
|---|---|---|
| Main Nano | Driver Nano 1 | Servo position commands |
| Main Nano | Driver Nano 2 | Linear actuator A commands |
| Main Nano | Driver Nano 3 | Linear actuator B commands |
| Driver Nano 1 | Main Nano | Servo status |
| Driver Nano 2 | Main Nano | Pressure and actuator feedback |
| Driver Nano 3 | Main Nano | IMU and actuator feedback |

### Proposed Message Structure

The software will need a consistent message format so each Nano can identify commands and sensor readings.

| Field | Purpose |
|---|---|
| Destination | Identifies the receiving controller |
| Command | Identifies the requested action |
| Value | Contains position, speed, or sensor data |
| Status | Indicates normal operation or a fault |

### Proposed Commands

| Command | Description |
|---|---|
| MOVE | Request movement to a position |
| SPEED | Change the requested movement speed |
| STOP | Stop commanded movement |
| STATUS | Request controller status |
| SENSOR | Send or request sensor information |
| ERROR | Report a detected fault |

These command names are proposed examples. The final message format will be determined during programming and testing.

### Ribbon Cable Connections

Each driver Nano connects to the main Nano with an 8-pin ribbon cable using the class-standard pinout.

The connector pinout is:

| Pin | Use |
|---|---|
| 1 | UART: command from the main Nano to the driver Nano |
| 2 | UART: feedback from the driver Nano to the main Nano |
| 3&ndash;5 | Digital, not used |
| 6&ndash;7 | Analog, not used |
| 8 | Ground reference (no power is carried on the ribbon) |

Each board has its own power supply, so the ribbon carries only the UART link and the shared ground reference that UART needs.

---

## Sensors and Actuators

The robotic leg will use multiple components to control movement and monitor its position.

### Actuators

| Component | Purpose | Controller |
|---|---|---|
| Servo motor | Controls one joint | Akshan |
| Linear actuator A | Controls one joint | Bex |
| Linear actuator B | Controls one joint | Kaushik |

The final actuator models and motor drivers have not been selected.

### Sensors

| Component | Purpose |
|---|---|
| IR sensor | Receives commands from a remote |
| Pressure sensor | Detects contact or applied pressure |
| IMU | Measures orientation and movement |
| Actuator position sensors | Measure joint position for closed-loop control and range limits |

### Status Indicators

The system will use LEDs to provide visual information about its operation.

| Indicator | Proposed Purpose |
|---|---|
| RGB LED | Displays overall system status |
| Local status LEDs | Display individual controller or joint status |

The final LED colors and meanings will be assigned during programming.

---

## Safety and Error Handling

Safety is important because the robotic leg contains moving joints and actuators.

The software must prevent commands from causing movement beyond the allowed joint range.

### Joint Position Limits

The leg does not use limit switches. Each driver Nano knows its joint's position from its own feedback (servo position or the linear actuator's position sensor), and the software keeps every joint inside its allowed range.

Driver Nano 3's motor driver also limits motor current and detects a stall, so its joint is stopped before the motor overheats if it reaches a hard stop or jams.

If a command would move a joint past its allowed range, the driver Nano rejects it and stops at the limit.

### Communication Loss

If a driver Nano loses communication with the main Nano, the affected actuator should stop safely.

The controller should report the communication fault when communication becomes available again.

### Invalid Movement Commands

The software should reject commands that request movement outside the allowed range.

### Fault Response Table

| Condition | Proposed Response |
|---|---|
| Joint position limit reached | Stop movement farther into the limit |
| Motor stall or over-current | Stop the motor and report a fault |
| Communication lost | Stop the affected actuator |
| Invalid command | Reject the command |
| Sensor error | Report a fault |
| Startup | Keep motors stopped until initialization finishes |
| Stop command | Stop commanded movement |

---

## Development Status

The block diagram and communication structure represent the team's current proposed design.

The following items still need to be finalized:

- Servo and linear actuator models
- Motor driver circuits
- UART pin assignments and baud rate
- Ribbon cable pinout
- Power distribution
- Diagnostic display
- Final sensor connections
- Communication message format
- Safety testing

The diagrams and tables will be updated as the team completes the hardware and software design.
