---
title: Mimi's Appendix Breakdown- Main Page
---

The diagram below illustrates our team's Motor Driver Subsystem. Its purpose is to demonstrate how the Curiosity Nano processes position data by calculating the difference between the X and Y coordinates. Based on this calculated error value, the controller determines whether movement should begin. If the error exceeds the defined threshold, the motors are activated and the movement loop is executed. Once the error is less than or equal to the threshold, motor operation stops. The design also includes a safety condition that immediately disables both motors if the error exceeds a predefined maximum limit.

<img width="420" height="440" alt="image" src="https://github.com/user-attachments/assets/1a84d727-cedb-409c-9b1f-fbc92bd1d22a" />
