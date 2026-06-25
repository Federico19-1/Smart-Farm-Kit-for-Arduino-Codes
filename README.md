# 🌱 Keyestudio Smart Farm Kit - ESP32 IoT Workshop

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform: ESP32](https://img.shields.io/badge/Platform-ESP32-red.svg)](https://www.espressif.com/en/products/socs/esp32)
[![IDE: Arduino](https://img.shields.io/badge/IDE-Arduino-blue.svg)](https://www.arduino.cc/en/software)

> **A complete, ready-to-run codebase for the Keyestudio Smart Farm Kit. Transform your ESP32 into an automated farm management system that monitors the environment, controls actuators, and is accessible via a web interface or a dedicated mobile app.**

---

## 📖 Table of Contents

- [🌟 Introduction](#-introduction)
- [✨ Features](#-features)
- [🛠️ Hardware Overview](#️-hardware-overview)
- [🚀 Getting Started](#-getting-started)
    - [1. Prerequisites](#1-prerequisites)
    - [2. Installation & Configuration](#2-installation--configuration)
    - [3. Upload Your First Sketch](#3-upload-your-first-sketch)
- [📂 Project Structure](#-project-structure)
- [🧩 Included Projects & Modules](#-included-projects--modules)
- [🌐 Web & App Control](#-web--app-control)
- [🤝 Contributing](#-contributing)
- [📜 License](#-license)

---

## 🌟 Introduction

Welcome to the **Keyestudio Smart Farm Kit** repository! This project provides a comprehensive collection of Arduino sketches designed to unlock the full potential of your Keyestudio Smart Farm Kit[reference:0]. Based on the powerful ESP32 platform, this kit is your gateway to the Internet of Things (IoT), blending hardware, sensors, and software to create an intelligent, automated farm system[reference:1].

Whether you are a hobbyist, a student in a STEM program, or an educator, this repository will guide you through building a functional smart farm, from assembling the physical components to controlling them via a web browser or a custom mobile app[reference:2].

## ✨ Features

This project transforms a collection of components into a cohesive smart farming solution:

*   **🌡️ Environmental Monitoring:** Real-time tracking of temperature, humidity, soil moisture, light intensity, and water levels[reference:3].
*   **💧 Automated Irrigation:** A soil moisture sensor triggers a water pump to automatically water your plants when the soil gets too dry.
*   **🐓 Smart Feeding System:** An ultrasonic sensor detects an animal's presence and automatically opens a servo-controlled feeding cabin[reference:4].
*   **🌦️ Rain Detection:** A steam sensor detects rain, which can be used to trigger alerts or protective actions.
*   **🔐 Alarm System:** A Passive Infrared (PIR) motion sensor can trigger a buzzer and an LED to act as a security alarm.
*   **🌐 Remote Control:** Monitor sensor data and control actuators (LED, fan, water pump, servo) from anywhere using a built-in web server or a dedicated mobile app[reference:5].
*   **🖥️ On-Device Display:** An LCD 1602 screen provides real-time, local feedback on sensor readings.

## 🛠️ Hardware Overview

This kit is built around the **KEYESTUDIO ESP32 PLUS Board**[reference:6], a powerful development board with integrated Wi-Fi and Bluetooth. Key hardware components include[reference:7]:

*   **Microcontroller:** ESP32-WROOM-32
*   **Operating Voltage:** 3.3V - 5V
*   **Current Output:** 1.2A (Maximum)
*   **Connectivity:** 2.4GHz Wi-Fi & Bluetooth 4.2[reference:8]

### **Included Modules:**

*   **Sensors:** DHT11 (Temperature & Humidity), Soil Humidity Sensor, Water Level Sensor, Photoresistor (Light), Steam Sensor (Rain), Ultrasonic Sensor (Distance), PIR Motion Sensor.
*   **Actuators:** SG90 9G Servo, DC Motor with Fan, Water Pump, Passive Buzzer, LED Module.
*   **Display:** LCD 1602 Module (I2C).
*   **Other:** Relay Module, Button Module.

## 🚀 Getting Started

Follow these steps to get your Smart Farm up and running.

### 1. Prerequisites

Before you begin, ensure you have the following:

*   **Hardware:**
    *   Keyestudio Smart Farm Kit (including all modules, wires, and acrylic/wooden parts).
    *   6x AA Batteries (for powering motors and pumps).
    *   A USB Cable (type-A to micro-B) to connect the ESP32 board to your computer.
*   **Software:**
    *   **Arduino IDE:** Version 2.0 or later [Download here](https://www.arduino.cc/en/software).
    *   **ESP32 Board Package:** Version `2.0.6` installed via the Arduino Boards Manager. **(Using the correct version is critical for compatibility).**

### 2. Installation & Configuration

1.  **Clone this Repository:**
    ```bash
    git clone https://github.com/your-username/keyestudio-smart-farm.git

