
# Team 102 — Robotic Spider Leg

## Project Overview

Team 102 is designing one functional leg for a six-legged robotic spider. The goal is to create a leg that can move through multiple joints, respond to movement commands, and provide information about its position and operating conditions. Our design uses multiple microcontrollers that communicate through UART. The main controller handles movement calculations, while the other controllers manage actuators, sensors, and other hardware. The system is planned to use linear actuators, a servo motor, limit switches, and sensors to support controlled movement and basic safety functions. The team is currently finalizing its hardware and software designs before moving into full implementation and testing.

## Project Objectives

The main objectives of this project are to:

- Design and build one robotic spider leg.
- Coordinate movement across three joints.
- Use UART for communication between microcontrollers.
- Control the assigned actuators and servo motor.
- Monitor limit switches and sensor information.
- Stop commanded movement when a fault or communication failure is detected.
- Document the hardware and software design.

## System Architecture

The project is divided into smaller subsystems.

### Main Controller

The main controller handles the kinematics calculations and sends movement commands to the other controllers.

### Driver Controllers

The driver controllers manage their assigned joint actuators and monitor the relevant limit switches.

### Servo and Display Controller

The servo/display controller handles its assigned servo motor and the planned diagnostic display.

The display specifications are still being finalized.

## Project Documentation

The team report contains the following sections:

1. Team Organization
2. User Needs and Benchmarking
3. Product Requirements
4. Design Ideation
5. Team Block Diagram
6. Software Proposal
7. Individual Datasheets

These pages document the decisions, requirements, and progress of the project.

## Individual Datasheets

Each team member maintains an individual datasheet describing their assigned subsystem.

| Subsystem | Responsibility |
|---|---|
| Main Controller | Kinematics and command distribution |
| Driver Nano 2 | Linear actuator control |
| Additional Controller | Assigned hardware and sensors |
| Servo/Display Controller | Servo motor and display |

Add the individual website links here once their final URLs are confirmed.

## Current Project Status

The team has established the general system architecture and selected UART as the communication method.

The block diagram and software proposal describe how the subsystems are intended to communicate.

The team is continuing to finalize component selections, electrical schematics, software implementation, and testing procedures.

## External Design Review

**Date:** October 29, 2026

The purpose of this review is to present the current design, explain the team's engineering decisions, and receive feedback before implementation.

The team will use this report to walk reviewers through the project.
