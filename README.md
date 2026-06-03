# ESP32 Smart Parking Sensor System

## Overview

The ESP32 Smart Parking Sensor System is an embedded systems project designed to assist drivers during parking by detecting obstacles and providing real-time visual feedback. The system uses an ESP32 microcontroller, an IR obstacle sensor, and an OLED display to classify distances into safety zones and alert the user accordingly.

This project demonstrates the integration of analog sensing, digital inputs, OLED graphics, and embedded control logic within a single microcontroller platform.

---

## Features

* Real-time obstacle detection
* Three parking safety zones:

  * SAFE (>100 cm)
  * WARNING (51–100 cm)
  * DANGER (0–50 cm)
* OLED display interface
* Animated visual alerts
* Obstacle override using IR sensor
* Distance simulation using potentiometer
* Compact and low-cost implementation

---

## Components Used

| Component                     | Quantity |
| ----------------------------- | -------- |
| ESP32-WROOM-32                | 1        |
| SSD1306 OLED Display (128×64) | 1        |
| IR Obstacle Sensor            | 1        |
| 10kΩ Potentiometer            | 1        |
| Breadboard                    | 1        |
| Jumper Wires                  | Several  |
| USB Power Supply              | 1        |

---

## Hardware Connections

### OLED Display

| OLED Pin | ESP32 Pin |
| -------- | --------- |
| SDA      | GPIO 21   |
| SCL      | GPIO 22   |
| VCC      | 3.3V      |
| GND      | GND       |

### IR Sensor

| IR Pin | ESP32 Pin |
| ------ | --------- |
| OUT    | GPIO 13   |
| VCC    | 3.3V      |
| GND    | GND       |

### Potentiometer

| Potentiometer Pin | ESP32 Pin |
| ----------------- | --------- |
| Wiper             | GPIO 34   |
| VCC               | 3.3V      |
| GND               | GND       |

---

## System Operation

1. The potentiometer simulates the distance between a vehicle and an obstacle.
2. The ESP32 reads the analog value and converts it to a distance measurement between 0 cm and 200 cm.
3. The system determines the current safety zone.
4. The OLED display updates in real time showing:

   * Distance value
   * Safety zone
   * Progress bar
   * Visual warning indicators
5. If the IR sensor detects an obstacle, it overrides the potentiometer reading and immediately places the system in the DANGER zone.

---

## Safety Zones

### SAFE Zone (>100 cm)

* Vehicle is far from obstacles
* No warning animation displayed
* Normal operation

### WARNING Zone (51–100 cm)

* Driver should proceed with caution
* Slow visual alert animation

### DANGER Zone (0–50 cm)

* Critical proximity detected
* Fast warning animation
* Screen flashing effect

### IR Obstacle Detection

* Immediate DANGER state
* Distance forced to 10 cm
* "OBSTACLE!" warning displayed

---

## Software Logic

### readSensors()

Reads:

* Potentiometer value
* IR sensor state

### processZones()

Determines:

* Current safety zone
* Alert level
* Progress bar status

### updateDisplay()

Updates OLED graphics:

* Distance
* Zone indicator
* Progress bar
* Warning animations

---

## Future Improvements

* Replace potentiometer with HC-SR04 ultrasonic sensor
* Add audible buzzer alerts
* Bluetooth or Wi-Fi monitoring
* Mobile application integration
* RGB LED proximity indicator
* Data logging and analytics

---

## Applications

* Vehicle parking assistance
* Obstacle detection systems
* Embedded systems education
* IoT sensor demonstrations
* Smart vehicle prototypes

---

## Team Members

* Kipyegon Mark Rotich 
* Gillian Kiptoo 
* Ochieng Phillip 

Department of Electrical & Electronic Engineering

---

## License

This project is released for educational and research purposes.
