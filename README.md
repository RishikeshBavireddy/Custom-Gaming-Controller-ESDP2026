# ESP32-Based BLE Gaming Controller

## Overview

This project presents the design and implementation of a custom Bluetooth Low Energy (BLE) gaming controller based on the ESP32 platform. The system integrates multiple user input mechanisms including joysticks, push buttons, directional pad (D-pad), and trigger switches, along with onboard power management and USB interfacing.

The project was developed as part of the **Electronic System Design Project Lab (Spring Semester 2026)** at IIT Hyderabad. It encompasses complete hardware design (schematic and PCB), embedded firmware development, and system-level testing.

---

## Objectives

- Design a fully functional BLE gaming controller using ESP32
- Develop a custom PCB integrating all controller subsystems
- Implement BLE HID communication for wireless gaming
- Integrate motion sensing using MPU6050
- Provide visual feedback using NeoPixel LEDs
- Validate hardware and firmware performance 

---


# System Architecture

The controller consists of five major subsystems:

## 1. Input Subsystem

Responsible for acquiring user inputs.

### Components

- Dual Analog Joysticks
- Trigger Buttons (LT, RT)
- Action Buttons (R1–R4)
- Directional Pad (D-pad)
- Joystick Push Buttons (LS, RS)

---

## 2. Motion Sensing Subsystem

### MPU6050 Gyroscope

Provides motion-based camera control and aiming assistance.

| Signal | ESP32 Pin |
|----------|----------|
| SDA | GPIO21 |
| SCL | GPIO22 |

The gyroscope is interfaced using the I2C protocol.

---

## 3. Processing Unit

### ESP32-WROOM-32

Responsible for:

- Input acquisition
- Signal processing
- Deadzone compensation
- Motion sensing
- LED control
- BLE communication

---

## 4. Communication Subsystem

### BLE HID Gamepad

The ESP32 operates as a Bluetooth HID gamepad and transmits:

- Button states
- D-pad states
- Joystick positions
- Motion control data

to gaming devices and computers.

---

## 5. Power Management

The controller is powered by a rechargeable Li-Ion battery and includes:

- TP4056 charging circuit
- DW01A battery protection IC
- FS8205A protection MOSFET
- MT3608 boost converter
- AMS1117-3.3 voltage regulator

---


## Hardware Design

### Schematic

The complete circuit schematic is shown below:

![Schematic](images/schematic.png)

---

### PCB Layout

#### Design (EasyEDA)
![PCB Layout](images/pcb.png)

#### Fabricated PCB (Before Assembly)
![PCB Bare](images/pcb_bare.jpg)

#### Assembled PCB
![PCB Assembled](images/pcb_assembled.jpeg)

---

## Key Components

| Component            | Description                          |
|---------------------|--------------------------------------|
| ESP32-WROOM-32      | Main microcontroller with BLE        |
| CH340C              | USB-to-Serial interface              |
| AMS1117-3.3         | Voltage regulator                    |
| TP4056              | Li-ion battery charger               |
| DW01A + FS8205A     | Battery protection circuitry         |
| MT3608              | DC-DC boost converter                |
| Analog Joysticks    | Dual-axis input devices              |
| Push Buttons        | User input switches                  |
| USB Type-C          | Power and programming interface      |

---

### 3. Gyroscope Integration

A gyroscope is planned for motion-based input.

**Current Status:**
- Not yet implemented  

**Future Plan:**
- Integrate via I2C interface  
- Update firmware for sensor fusion and motion tracking  

---

## Testing and Validation

| Module             | Status       |
|-------------------|-------------|
| Buttons           | Verified     |
| D-pad             | Verified     |
| Triggers          | Verified     |
| Joystick Buttons  | Verified     |
| Joystick Axes     | Verified     |
| BLE Connectivity  | Verified     |
| Drift Correction  | Pending      |
| Gyroscope         | Pending      |

---

## Firmware Overview

The firmware is responsible for:

- Reading analog and digital inputs  
- Processing joystick data  
- Handling BLE communication  
- Mapping inputs to gamepad controls  

---

## Repository Structure

## Course Information

This project was carried out as part of:

**Electronic System Design Project Lab**  
Spring Semester 2026  
Indian Institute of Technology Hyderabad  

---

## Team Members

- Rishikesh — EE24BTECH11204  
- Vighnesh — EE24BTECH11205  
- Kedar — EE24BTECH11030  
- Mahendar — EE24BTECH11213  
- Ashok — EE24BTECH11208  
- Madhukar — EE24BTECH11218  

