# Electric Vehicle

## Overview

This project implements a basic PID control system with encoder feedback for Arduino-powered differential-drive RC cars.

The system is designed to:
- Maintain a desired motor speed
- Help the vehicle drive in a straight line
- Perform 90-degree turns
- Use gyroscope data to improve heading control

Gyroscope measurements are processed using a Kalman filter to reduce sensor noise and provide more stable heading information.

## How It Works

### PID Motor Control

The project includes a `PID` class that uses encoder feedback to regulate motor speed. The controller continuously compares the motor's measured speed with the desired target speed and applies a correction.

A PID controller consists of three terms:

- **Proportional (P):** Responds to the current speed error.
- **Integral (I):** Accumulates past errors to reduce steady-state error.
- **Derivative (D):** Responds to how quickly the error is changing.

Together, these terms form a feedback loop that allows the motor to maintain a speed close to the desired target.

### Encoder Feedback

Encoders provide measurements of the motor or wheel movement. This feedback allows the controller to determine the actual motor speed and adjust the motor output accordingly.

### Gyroscope and Kalman Filter

The vehicle uses gyroscope measurements to estimate its heading. Because gyroscope data can contain noise, the measurements are processed through a Kalman filter.

The filtered heading information can then be used to correct the vehicle's direction while driving and to improve the accuracy of 90-degree turns.

### Example Chassis Utilized
<img width="826" height="398" alt="Screenshot 2026-09-04 053011" src="https://github.com/user-attachments/assets/93b86672-19ac-4d45-9dbe-ab4d495edb74" />
<img width="914" height="384" alt="Screenshot 2026-09-04 053227" src="https://github.com/user-attachments/assets/6021238a-4669-418b-94a1-b2e3f2186e69" />

### PID Tuning Tool

I wrote a script to analyze the output of the PID controller to measure and minimize oscillations. Repo: https://github.com/LolFeever12345/PIDData
