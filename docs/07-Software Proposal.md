

# Software Proposal

## Overview

The purpose of this software proposal is to explain how our team plans to control one leg of a six-legged robotic spider.

The design uses four PIC18F57Q43 Curiosity Nano microcontrollers. One Nano handles the main calculations and commands, while the other three control motors, actuators, and sensors.

The software is still in development. Component choices, pin assignments, and communication settings will be updated as the team completes the design.

## Table of Contents

1. [Software Architecture](#software-architecture)
2. [Software Flow](#software-flow)
3. [Communication Between Nanos](#communication-between-nanos)
4. [Safety and Error Handling](#safety-and-error-handling)
5. [Testing and Next Steps](#testing-and-next-steps)

---

## Software Architecture

The system uses one main controller and three driver controllers.

The main Nano calculates where the leg should move. The driver Nanos receive commands, control their assigned components, and return sensor information.

| Controller | Team Member | Responsibilities |
|---|---|---|
| Main Nano | Preston | Kinematics, IR remote, RGB LED, communication |
| Driver Nano 1 | Akshan | Servo motor and proposed display |
| Driver Nano 2 | Bex | Linear actuator A, pressure sensor, limit switches, status LED |
| Driver Nano 3 | Kaushik | Linear actuator B, IMU, limit switches, sensor feedback |

### Leg Control Block Diagram

![Leg Control Block Diagram](images/leg-control-block-diagram.png)

*Figure 1: Proposed control architecture showing the main Nano and three driver Nanos.*

The main Nano acts as the central controller. Each driver Nano is responsible for its assigned hardware.

The final motor drivers, wiring, and display are still being selected.

**Note:** UART is the current communication plan. Any older I2C/Serial labels in the diagram will need to be updated.

### Main Nano

The main Nano is responsible for:

- Reading commands from the IR remote
- Calculating the desired leg position
- Performing kinematics calculations
- Sending movement commands
- Receiving sensor feedback
- Updating the RGB status LED
- Detecting communication or system faults

### Driver Nano 1

Akshan's Nano is responsible for:

- Receiving servo position commands
- Controlling the servo motor
- Reporting servo status
- Operating the proposed diagnostic display

### Driver Nano 2

Bex's Nano is responsible for:

- Receiving actuator commands
- Controlling linear actuator A
- Reading the pressure sensor
- Checking assigned limit switches
- Updating the local status LED
- Sending feedback to the main Nano

### Driver Nano 3

Kaushik's Nano is responsible for:

- Receiving actuator commands
- Controlling linear actuator B
- Reading the IMU
- Checking assigned limit switches
- Sending sensor feedback to the main Nano

---

## Software Flow

The software will run continuously while the robotic leg is powered.

The main controller calculates movement and sends commands. The driver controllers carry out the commands while monitoring sensors and limits.

### Software Flow Diagram

![Software Flow Diagram](images/software-flow-diagram.png)

*Figure 2: Proposed software flow showing movement commands and sensor feedback.*

### Main Controller Process

1. Start the program.
2. Initialize communication and hardware.
3. Read input from the IR remote.
4. Determine the requested leg movement.
5. Calculate the joint positions using kinematics.
6. Send movement commands to the driver Nanos.
7. Receive feedback from the sensors.
8. Check for faults or limit conditions.
9. Update the RGB status LED.
10. Repeat the process.

### Driver Controller Process

1. Initialize the assigned hardware.
2. Wait for a valid command.
3. Check whether the requested movement is allowed.
4. Control the assigned motor or actuator.
5. Read the connected sensors.
6. Check the limit switches.
7. Send feedback to the main Nano.
8. Repeat until the system is stopped.

Each driver Nano can handle its assigned tasks independently after receiving a valid command.

---

## Communication Between Nanos

The team currently plans to use UART communication between the Nanos.

UART allows controllers to exchange commands and feedback through serial communication.

The exact communication channels, pin assignments, and message format have not been finalized.

### Proposed Communication Messages

| Message | Direction | Purpose |
|---|---|---|
| Position command | Main to driver | Requests movement |
| Speed command | Main to driver | Changes actuator or motor speed |
| Sensor feedback | Driver to main | Reports sensor readings |
| Limit warning | Driver to main | Reports a triggered limit switch |
| Motor status | Driver to main | Reports motor operation |
| Fault message | Either direction | Reports a problem |
| Stop command | Main to driver | Requests a safe stop |

### Proposed Message Structure

| Field | Description |
|---|---|
| Destination | Identifies the receiving Nano |
| Command | Identifies the requested action |
| Value | Contains the position, speed, or other data |
| Status | Reports completion or an error |

The final UART baud rate, wiring arrangement, and message structure will be determined during testing.

### Sensor Feedback

The driver Nanos will return information to the main controller.

Planned feedback includes:

- Joint or actuator position
- Pressure sensor readings
- IMU measurements
- Limit-switch status
- Motor or actuator status
- Error messages

This information will help the main controller determine whether the leg is operating correctly.

---

## Safety and Error Handling

Safety is an important part of the software because the robotic leg contains moving joints and actuators.

The software must prevent commands from moving the joints outside their allowed range.

### Limit Switches

The current plan includes two limit switches for each of the three joints.

The switches will help detect when a joint reaches its allowed movement limit.

When a limit switch is activated, the software should stop movement farther into that limit.

### Communication Loss

If communication between the main Nano and a driver Nano is lost, the affected actuator should stop safely.

The system should also report a communication fault.

### Invalid Commands

The software should reject movement commands that are outside the allowed operating range.

### Fault Responses

| Condition | Proposed Response |
|---|---|
| Joint limit reached | Stop movement farther into the limit |
| Communication lost | Stop the affected actuator |
| Invalid movement command | Reject the command |
| Sensor error | Report a fault |
| Startup | Keep motors stopped until initialization finishes |
| Emergency stop request | Stop commanded movement |

The exact fault handling will be tested once the hardware is connected.

---

## Testing and Next Steps

The team will test the individual controllers before combining them into the complete leg.

| Test | Expected Result |
|---|---|
| UART communication | Nanos exchange valid commands and feedback |
| Servo control | Servo responds to position commands |
| Linear actuator A | Actuator responds to movement commands |
| Linear actuator B | Actuator responds to movement commands |
| Pressure sensor | Nano receives pressure readings |
| IMU | Nano receives orientation data |
| Limit switches | Movement stops at the assigned limits |
| IR remote | Main Nano recognizes user commands |
| RGB LED | LED displays the assigned system status |
| Communication failure | Actuators stop safely |

### Items Still Being Finalized

- Servo motor model
- Linear actuator models
- Motor driver circuits
- Final UART connections
- Pin assignments
- Power distribution
- Diagnostic display
- Final software testing

The software proposal will continue to be updated as the team finalizes the hardware and begins programming.

## External Design Review — Software Design Rationale

The software is divided by hardware responsibility to match the four-controller block diagram. The main controller manages movement calculations and distributes commands, while the driver controllers translate those commands into local actuator or servo actions and return sensor and fault information. This organization avoids putting all peripheral handling into the main control loop and gives each team member a subsystem that can be tested independently.

The proposed sequence initializes communication and hardware first, checks relevant inputs, processes a command, applies the permitted output, and reports status. Checking limit switches before and during actuator commands is intended to prevent continued commanded motion into an active travel limit. Communication-loss handling is included because a driver must not continue an old movement command indefinitely when the main controller is no longer communicating.

### Relationship to product requirements

| Requirement | Proposed software behavior |
| --- | --- |
| Coordinate three-joint motion | Main controller computes and distributes joint commands |
| Control assigned motors | Driver controllers interpret and apply local commands |
| Communicate between boards | UART command and status messages |
| Monitor mechanical limits | Driver controllers read limit switches |
| Report operating conditions | Pressure, IMU, and status data returned to main controller |
| Handle faults | Stop commanded motion and report fault status |

### Implementation checks before testing

The team still needs to verify UART routing and message framing, define timeouts and recovery rules, configure the PIC peripherals, and test the stop response with actual actuator hardware. The diagrams above show the intended software flow rather than measured performance.
