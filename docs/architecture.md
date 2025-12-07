Here is a clean, professional **English version of `architecture.md`** that you can copy directly into your GitHub project.

Feel free to paste your Tinkercad wiring image where indicated.


#  **Robot Architecture Overview**

This document describes the physical and logical architecture of the Spider Robot project, including mechanical structure, servo placement, wiring layout, and the overall system design.


##  **1. General Robot Structure**

The robot is a six-legged (hexapod) platform.  
Each leg is controlled by a set of servo motors that allow the robot to lift, lower, and move its legs forward and backward.

**Main components:**

* **Chassis / Body frame** (3D-printed or pre-built)
* **12× SG90 servo motors** (2 per leg)
* **PCA9685 PWM controller** (16-channel)
* **Arduino Uno/Mega**
* **External 5V power supply** for servos
* **Breadboard or power distribution module**
* **Connecting cables**

The PCA9685 is used because the Arduino cannot directly generate 12 stable PWM signals for multiple servos.


##  **2. Mechanical Leg Structure**

Each leg consists of two main joints:

1. **Hip Servo (Horizontal movement)**  
   Rotates the leg left/right and is attached to the main body.

2. **Knee Servo (Vertical movement)**  
   Lifts and lowers the leg.

This configuration allows the robot to perform basic gaits such as:

* Tripod gait
* Ripple gait
* Wave gait

This two-servo-per-leg system is simple, lightweight, and power-efficient.


##  **3. Electronics and Wiring Overview**

All 12 servos receive PWM control signals from the PCA9685, while power is supplied separately to prevent overload on the Arduino.

**Connections:**

* **PCA9685 → Arduino**

  * SDA → A4
  * SCL → A5
  * VCC → 5V
  * GND → GND

* **Servos → PCA9685**

  * Signal pins: channels 0–11
  * Power: 5V and GND from external power source

* **Power Source Requirements:**

  * 5V
  * 2A–5A depending on servo load  
    **Do NOT use a 9V battery (“block battery”) — it cannot supply required current.**


##  **4. Wiring Diagram**

<img width="1900" height="863" alt="Снимок экрана 2025-12-07 163326" src="https://github.com/user-attachments/assets/60975166-427b-497f-804a-5aaaa8cb89d0" />

