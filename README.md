# Gyroscope-Based Gesture Recognition System for Throttle Valve Control

A gesture-controlled actuation system that uses a gyroscope sensor to detect hand orientation and translate it into real-time servo motor control — simulating throttle valve positioning. Built as an individual project to explore embedded sensor integration, Bluetooth/CAN bus communication, and real-time actuator control.

## What it does

- Reads angular motion from a **GY-521 (MPU-6050)** gyroscope sensor to track hand gestures in real time.
- Maps tilt angle directly to **servo motor rotation**, simulating throttle valve positioning based on hand movement.
- Communicates over **Bluetooth** for wireless control of LED and push-button states.
- Integrates **CAN bus** protocol for data exchange with external devices — the same communication standard used in automotive and industrial control systems.
- Includes overflow/limit detection to keep the system operating safely within range.

## Hardware & Tools

- Arduino Uno
- GY-521 (MPU-6050) gyroscope/accelerometer sensor
- Servo motor
- Active buzzer + LED (status/alert indicators)
- CAN bus module
- Bluetooth module
- Arduino IDE (C++)

## How it works

1. The MPU-6050 continuously streams orientation data to the Arduino over I2C.
2. The Arduino processes this data and maps the tilt angle to a target servo position.
3. The servo moves in real time to reflect the gesture, simulating throttle valve response.
4. In parallel, the system listens for Bluetooth commands (LED/button control) and exchanges status data over the CAN bus.
5. A buzzer/LED provide simple feedback if the system detects an out-of-range condition.

## Why this project

Most gesture-control demos stop at "move the servo." This one goes further by layering in the communication protocols that real automotive and industrial systems actually use — CAN bus for inter-device data exchange, with Bluetooth for local wireless control — so the gesture input isn't just a toy, it's wired into a realistic control architecture.

## Files

- `Task_3.ino` — main Arduino firmware
- `Microcontrollers report.pdf` — full technical write-up (design rationale, testing, performance analysis)

## Status

Built and tested on physical hardware. Individual project.
