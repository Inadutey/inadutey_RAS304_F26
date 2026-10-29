---
title: Motor Drive Schematic
---

## Overview


This schematic illustrates the electrical design of the Motor Driver Subsystem for the Open Field robotic platform. This subsystem uses a Curiosity Nano microcontroller and H-bridge motor driver to control two DC gear motors. The purpose of this subsystem is to provide controlled motor operation for robot navigation and movement throughout the field.

**Circuit Design, Microcontroller and Motor Control**

our Nano acts as the primary controller for the subsystem. GPIO outputs from the microcontroller are connected to the motor driver, allowing the controller to command motor direction and movement. The microcontroller processes software-generated control signals and sends them to the H-bridge, which supplies the necessary power to operate both DC motors.

The isolates the low-power control circuitry from the higher-current motor circuitry, enabling reliable and efficient motor control.

**Power Supply**

The subsystem receives power through a DC barrel jack input. A fuse is included to protect the circuit from excessive current conditions, while a voltage regulator converts the input voltage into a regulated 5 V supply for the Curiosity Nano and other low-voltage components.

The Motor driver and DC motors are powered from the motor supply rail, ensuring sufficient current is available for motor operation while maintaining stable logic-level power for the controller.

**User Input**

A pushbutton provides a manual input to the microcontroller for testing and system interaction. The pushbutton is connected with supporting components to ensure reliable signal detection and reduce the effects of electrical noise.

A status LED with a current-limiting resistor provides visual feedback, allowing users to verify subsystem operation and assist during debugging and testing.

**Electrical Connections**

This schematic includes a ribbon connector for communication with other project subsystems and external hardware. Additional connections are provided for motor outputs, power input, and control signals between the Curiosity Nano and the motor driver. These interfaces allow the Motor  Subsystem to integrate into the overall system.

**Product Requirements**

This subsystem satisfies the needed product requirements by providing precise control of the robot's drive motors. The Curiosity Nano calculates movement commands and sends control signals to the DRV8833 motor driver, which regulates motor direction and operation. Together, these components enable the robot to move, navigate, and respond to control inputs while maintaining safe and reliable operation.




**Figure ##:**<img width="1106" height="824" alt="image" src="https://github.com/user-attachments/assets/8a95fef7-38a6-49d6-ad28-4af1019896a4" />




## Resources

The schematic as a PDF download is available [*here*](ExampleSchematic.pdf), and the Zip folder of the project [*here*](dummyZip.zip).
