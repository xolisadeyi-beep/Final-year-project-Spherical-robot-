# Spherical Robot

Final year project for the Bachelor of Technology in Electrical Engineering, Nelson Mandela University (2026).

**Author:** Xolisa Deyi

## Overview

This project is a spherical robot that balances itself using PID control. It can be controlled wirelessly and monitored in real time while it carries out its task. The robot has a built-in safety function that protects its internal mechanism from damage.

## Demo videos

- [Spherical Robot (with shell)](Spherical%20Robot.mp4)
- [Spherical Robot (without shell, showing the internal mechanism)](Spherical%20Robot%20without%20shell.mp4)

## Key features

### Wireless control and monitoring
The robot is controlled wirelessly through an MQTT application. The same application is used to monitor the status of the system while the robot is operating.

### PID balance control
The PID controller runs on the ESP32. It works as follows:
1. The MPU6050 sensor measures the tilt angle of the robot.
2. The controller compares the tilt angle with the desired angle, which is 0° (upright), to calculate the error.
3. The controller generates a PWM signal that drives the wheel to compensate for the error and return the robot to the upright position.

### Distance control
An optical sensor continuously measures the distance travelled while the robot is moving. When the set distance is reached, the robot stops momentarily and waits for a new command.

### Safety function
The safe operating range is a tilt angle of **0° to 60°**.
- **Inside the safe range:** the PID controller keeps compensating to hold the robot upright.
- **Outside the safe range:** the system locks the motion instead of increasing the speed to the maximum while trying to recover. This prevents high forces that could damage the internal mechanism.

## Hardware

| Component | Purpose |
|-----------|---------|
| ESP32 | Runs the PID control and the wireless communication |
| MPU6050 | Measures the tilt angle |
| Optical sensor | Measures the distance travelled |
| [Motor and wheel] | [Drive the robot and correct the tilt] |
| [Battery] | [Powers the system] |

## Software and tools

- PID control algorithm on the ESP32
- MQTT for wireless control and status monitoring
- [Programming language or IDE, for example Arduino IDE or C++]

## Results

- [A measured result, such as the time to recover from a tilt, the distance accuracy or the run time]
- [What worked well]
- [Limitations and what you would improve]

## Skills demonstrated

Embedded systems, PID control, sensor integration, wireless communication (MQTT), safety design and system testing.

## Contact

Xolisa Deyi · xolisadeyi@gmail.com
