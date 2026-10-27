**Motor Control Subsystem**

**Overview**

This block diagram illustrates the Motor Control and Power Distribution subsystem used in the EGR 304 robotic platform. The subsystem is responsible for regulated power distribution, motor control, feedback monitoring, and communication between the control electronics and mechanical drive components.

The design utilizes a 12 VDC power source protected by a fuse and regulated to provide stable operating voltages for the control circuitry. A Curiosity Nano microcontroller generates the control signals required by the left and right motor driver circuits. These motor drivers provide the necessary current and voltage to operate the differential drive motors.

Encoder feedback from both motors is routed back to the microcontroller, allowing motor speed and position monitoring. Debug LEDs are included to provide visual indicators during testing, troubleshooting, and normal operation.

**Power Source**

• 12 V DC Barrel Jack Input
• Fuse Protection Circuit
• Voltage Regulation Circuit
• Decoupling Capacitor Network
• Common Ground Reference

**Controller**

• Curiosity Nano Microcontroller

**Actuators**

• Left Drive Motor
• Right Drive Motor

**Sensors**
• Motor Encoder Feedback Signals
• User Input Switch

**Indicators**

• Status LED
• Debug LEDs

**Team Interfaces**

• Connector interface for signal routing and communication between subsystem components and team-designed modules

**Block Diagram**
<img width="1584" height="1060" alt="image" src="https://github.com/user-attachments/assets/62188e82-06a0-43bd-a41d-1f82157c211e" />


**Functional Description**

Power enters the subsystem through a 12 VDC barrel jack and passes through a protective fuse before being distributed throughout the system. A voltage regulator conditions the incoming voltage and provides the required operating voltage for the control electronics.

The Curiosity Nano microcontroller processes control logic and outputs motor control signals to the left and right motor driver circuits. Each motor driver independently controls a DC motor, enabling differential drive operation and directional control.

Encoder feedback from each motor is returned to the microcontroller where it can be used to monitor motor performance and support future closed-loop control implementations. Status LEDs and debugging indicators provide visual confirmation of subsystem activity and assist in system validation.

This subsystem serves as the central interface between the power distribution network, control electronics, sensor feedback circuits, and mechanical drive components of the robotic platform.
