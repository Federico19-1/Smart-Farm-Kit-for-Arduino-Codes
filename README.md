# 🌱 Keyestudio Smart Farm Kit — ESP32 IoT Workshop
<img width="250" height="250" alt="Smart_Farm_Interface" src="https://github.com/user-attachments/assets/b7959bad-3ef4-49ee-93a7-0aad686cea17" />

<img width="502" height="250" alt="images" src="https://github.com/user-attachments/assets/f3e0080e-0ff0-4373-9a13-584549a28ca7" />

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform: ESP32](https://img.shields.io/badge/Platform-ESP32-red.svg)](https://www.espressif.com/en/products/socs/esp32)
[![IDE: Arduino](https://img.shields.io/badge/IDE-Arduino%202.x-blue.svg)](https://www.arduino.cc/en/software)
[![ESP32 Package](https://img.shields.io/badge/ESP32%20Package-v2.0.6-green.svg)](https://github.com/espressif/arduino-esp32)

> **A complete, ready-to-run codebase for the Keyestudio Smart Farm Kit (KS0567).
> Transform your ESP32 into an automated farm management system that monitors the environment, controls actuators, and is accessible via a web browser or a dedicated mobile app.**

---

## 📖 Table of Contents

- [🌟 Introduction](#-introduction)
- [✨ Features](#-features)
- [🛠️ Hardware Overview](#️-hardware-overview)
  - [Board Specifications](#board-specifications)
  - [Included Modules](#included-modules)
  - [Pin Mapping](#pin-mapping)
- [🔩 Assembly Overview](#-assembly-overview)
- [🚀 Getting Started](#-getting-started)
  - [1. Prerequisites](#1-prerequisites)
  - [2. Set Up the Servo Before Assembly](#2-set-up-the-servo-before-assembly)
  - [3. Install & Configure Arduino IDE](#3-install--configure-arduino-ide)
  - [4. Add the Required Libraries](#4-add-the-required-libraries)
  - [5. Upload Your First Sketch](#5-upload-your-first-sketch)
- [📂 Project Structure](#-project-structure)
- [🧩 Projects](#-projects)
- [🌐 Web Control](#-web-control)
- [📱 App Control](#-app-control)
- [⚠️ Safety Notes](#️-safety-notes)
- [🤝 Contributing](#-contributing)
- [📜 License](#-license)

---

## 🌟 Introduction

Welcome to the **Keyestudio Smart Farm Kit** repository! This project provides a complete collection of Arduino sketches to bring your Keyestudio Smart Farm Kit (model **KS0567**) fully to life.

The kit is built around the powerful **KEYESTUDIO ESP32 PLUS Board**, which comes with integrated Wi-Fi and Bluetooth. It is your gateway to the world of the Internet of Things (IoT): you will combine physical sensors, actuators, and software to build a working intelligent farm system — one project at a time.

Whether you are a curious hobbyist, a student in a STEM program, or an educator looking for a hands-on kit, this repository guides you from assembling the physical parts all the way to controlling your farm remotely from a phone or browser.

> 📦 **Download all files** (code, libraries, driver): [https://fs.keyestudio.com/KS0567](https://fs.keyestudio.com/KS0567)

---

## ✨ Features

- 🌡️ **Environmental Monitoring** — Real-time tracking of temperature, humidity, soil moisture, light intensity, rain, and water level.
- 💧 **Automated Irrigation** — The soil moisture sensor and water level sensor work together to trigger a water pump automatically when the soil is dry and enough water is available.
- 🐓 **Smart Feeding System** — An ultrasonic sensor detects an animal's presence and automatically opens a servo-controlled feeding cabin door.
- 🌦️ **Rain Detection** — A steam sensor detects rainfall and can trigger alerts or protective actions.
- 🔐 **Security Alarm** — A PIR motion sensor triggers a buzzer and an LED to act as an intruder alarm.
- ☀️ **Solar Power Awareness** — An included solar panel demonstrates renewable energy concepts; no code required.
- 🌡️ **Temperature Control** — A DHT11 sensor monitors temperature and automatically turns on a fan when it gets too hot.
- 🖥️ **On-Device Display** — An LCD 1602 screen shows real-time sensor readings directly on the farm.
- 🌐 **Web Interface** — Monitor sensor data and control all actuators from any browser on the same Wi-Fi network.
- 📱 **Mobile App** — A dedicated iOS and Android app ("IOT Farm") gives you full control from your phone.

---

## 🛠️ Hardware Overview

### Board Specifications

The brain of the kit is the **KEYESTUDIO ESP32 PLUS Board**, based on the **ESP32-WROOM-32** module.

| Parameter | Value |
|---|---|
| Microcontroller | ESP32-WROOM-32 |
| Operating Voltage | 3.3V – 5V |
| Maximum Current Output | 1.2A |
| Maximum Power Output | 10W |
| Working Temperature | -10°C to 50°C |
| Dimensions | 69 × 54 × 14.5 mm |
| Weight | 25.5g |
| Wi-Fi | 2.4 GHz (802.11 b/g/n) |
| Bluetooth | 4.2 (BR/EDR + BLE) |

### Included Modules

| Category | Component |
|---|---|
| **Sensors** | DHT11 (Temperature & Humidity), Soil Humidity Sensor, Water Level Sensor, Photoresistor, Steam Sensor (Rain), Ultrasonic Sensor (HC-SR04), PIR Motion Sensor |
| **Actuators** | SG90 9G Servo, 130 DC Motor with Fan, Water Pump, Passive Buzzer, LED Module |
| **Display** | LCD 1602 (I2C) |
| **Power** | Relay Module, Solar Panel |
| **Input** | Button Module |

### Pin Mapping

Here is the complete wiring reference for all modules:

| # | Module | Connector | ESP32 Pin(s) |
|---|---|---|---|
| 1 | Fan (130 DC Motor) | 4-pin divided | io18 (IN−), io19 (IN+) |
| 2 | PIR Motion Sensor | 3-pin 15cm | io23 |
| 3 | Button | 3-pin 15cm | io5 |
| 4 | Ultrasonic Sensor | 4-pin divided | io12 (TRIG), io13 (ECHO) |
| 5 | LCD 1602 | 4-pin I2C | I2C (SDA/SCL) |
| 6 | DHT11 (Temp & Humidity) | 3-pin 20cm | io17 |
| 7 | Steam Sensor (Rain) | 3-pin 15cm | io35 |
| 8 | Photoresistor (Light) | 3-pin 15cm | io34 |
| 9 | Servo (SG90) | 3-pin | io26 |
| 10 | Passive Buzzer | 3-pin 20cm | io16 |
| 11 | LED Module | 3-pin 20cm | io27 |
| 12 | Water Level Sensor | 3-pin 25cm | io33 |
| 13 | Soil Humidity Sensor | 3-pin 20cm | io32 |
| 14 | Water Pump (via Relay) | 3-pin 20cm | io25 |

> **Wire color convention:** For all 3-pin modules, connect **Yellow → S (Signal)**, **Red → V (5V)**, **Black → G (GND)**.

---

## 🔩 Assembly Overview

The physical build is divided into **19 steps**. Follow them in order — some steps depend on what was done before.

| Step | Description |
|---|---|
| 1 | Install the ESP32 Board and the Relay Module |
| 2 | Install the Battery Case holder and the Feeding Cabin; connect ESP32 and Relay |
| 3 | Install the substructure (base frame) of the house |
| 4 | Install the Feeding Cabin door with servo gear |
| 5 | Install the LCD display and the DHT11 sensor |
| 6 | Install the Ultrasonic Module |
| 7 | Install the PIR Motion Sensor and Button Module |
| 8 | Install the walls of the house |
| 9 | Install the roof |
| 10 | Install the house base and ground |
| 11 | Wire all the internal modules |
| 12 | Attach the house to the foundation |
| 13 | Install the plastic water sinks |
| 14 | Install the Soil Humidity Sensor and the Water Level Sensor |
| 15 | Install the fence and fix the water pump |
| 16 | Install the Buzzer and LED Module |
| 17 | Decorate the house |
| 18 | Install the Solar Panel |
| 19 | Install the Battery Case (insert 6 × AA batteries — **not included**) |

> 💡 **Before Step 4**, you must set the servo angle to **180°** by running the `window_servo` sketch (see [Getting Started](#-getting-started) below). This is critical — the door will not work correctly if you skip it.

> 🪛 **Step 4 tip:** When installing the servo door, tighten the fixing screw firmly to keep the servo stable. A loose screw can cause the door to get stuck. Also, tear the protective film off the acrylic door panel to reduce friction.

---

## 🚀 Getting Started

### 1. Prerequisites

**Hardware:**
- Keyestudio Smart Farm Kit (KS0567), with all modules, wires, and wood/acrylic parts.
- **6 × AA batteries** (for powering the motors and water pump — not included in the kit).
- A USB cable (Type-A to Micro-B) to connect the ESP32 board to your computer.
- A **2.4 GHz Wi-Fi** network (a mobile hotspot works too) for projects 11 and 12.
- A phone or tablet on the same Wi-Fi, to test the web interface and the app.

**Software:**
- **Arduino IDE 2.x** → [Download here](https://www.arduino.cc/en/software)
- **ESP32 Board Package v2.0.6** (see instructions below)
- **CH340 USB Driver** (usually installed automatically; manual install provided in the tutorial package)

---

### 2. Set Up the Servo Before Assembly

> ⚠️ This step must be done **before** you physically attach the servo to the feeding cabin door. Once the servo is mounted, you cannot easily re-run this.

1. Connect the servo to **io26** of the ESP32 board (Yellow → io26, Red → V, Black → G).
2. Connect the ESP32 board to your computer via USB.
3. Open the `window_servo` sketch from the tutorial package in Arduino IDE.
4. Select `ESP32 Dev Module` as the board and the correct COM port.
5. Upload the code. The servo will rotate to **180°** (the correct starting position for the door).

---

### 3. Install & Configure Arduino IDE

**Install the ESP32 Board Package:**

1. Open Arduino IDE and go to **File → Preferences**.
2. In the "Additional boards manager URLs" field, paste this URL:
   ```
   https://espressif.github.io/arduino-esp32/package_esp32_index.json
   ```
3. Click **OK**, then open the **Boards Manager** (left sidebar).
4. Search for `esp32` and install **"esp32 by Espressif Systems" — version `2.0.6`**.

> ⚠️ **You must use version 2.0.6.** Other versions may be incompatible with the provided library files.

**Select your board and port:**

1. Go to **Tools → Board → esp32** and choose **ESP32 Dev Module**.
2. Go to **Tools → Port** and select the COM port shown in your Device Manager (e.g., `COM8`).

---

### 4. Add the Required Libraries

All library files are included in the tutorial package, downloadable from [https://fs.keyestudio.com/KS0567](https://fs.keyestudio.com/KS0567).

To install a library from a `.zip` file:
1. Go to **Sketch → Include Library → Add .ZIP Library...**.
2. Navigate to the `.zip` file and open it.
3. Restart Arduino IDE if needed.

The key libraries you will need are:

| Library | Used For |
|---|---|
| `ESP32_Servo` | Controlling the SG90 servo (feeding cabin door) |
| `LiquidCrystal_I2C` | Driving the LCD 1602 display |
| `DHT sensor library` | Reading temperature and humidity from the DHT11 |
| `WiFi.h` | Wi-Fi connectivity (built into the ESP32 package) |
| `WebServer.h` | Hosting the web control page (built in) |

---

### 5. Upload Your First Sketch

Once everything is installed, you are ready to go! Let's start with something simple:

1. Open `1.1Blink` from the `Codes` folder.
2. Make sure the board is set to `ESP32 Dev Module` and the right COM port is selected.
3. Click **Upload** (the arrow button).
4. Watch the LED on the farm blink once per second. ✅

You are now set up and ready to work through all the projects.

---

## 📂 Project Structure

```
Smart-Farm-Kit-for-Arduino-Codes/
│
├── Codes/
│   ├── 1.1Blink/
│   ├── 1.2PWM/
│   ├── 1.3Button/
│   ├── 1.4Self-Locking_Button/
│   ├── 1.5Lighting-System/
│   ├── 2.1Photocell-sensor/
│   ├── 2.2Light-Control-System/
│   ├── 3.1PIR-Motion-Sensor/
│   ├── 3.2Passive-Buzzer/
│   ├── 3.3Buzzer-Tone/
│   ├── 3.4Buzzer-Music/
│   ├── 3.5Alarm-System/
│   ├── 4.1Steam-Sensor/
│   ├── 4.2Rainwater-Detection-System/
│   ├── 6.1Servo/
│   ├── 6.2Ultrasonic-Sensor/
│   ├── 6.3Intelligent-Feeding-System/
│   ├── 7.1DHT11/
│   ├── 7.2LCD1602/
│   ├── 7.3Motor/
│   ├── 7.4Temperature-Control-System/
│   ├── 8.1Soil-Humidity-Sensor/
│   ├── 8.2Soil-Humidity-Testing-System/
│   ├── 9.1Water-Level-Sensor/
│   ├── 9.2Water-Level-Testing-System/
│   ├── 10.1Water-Pump/
│   ├── 10.2Auto-irrigation/
│   ├── 11.0Connect-the-ESP32-to-the-Network/
│   ├── 11.1WiFi-HTML-HELLOWORLD/
│   ├── 11.2WiFi-HTML-Smart-Farm/
│   └── 12.1APP-Smart-Farm/
│
├── Libraries/           ← All .zip library files
├── Driver/              ← CH340 USB driver
└── README.md
```

> **Note:** Arduino stores only one sketch at a time on the board. Uploading a new sketch replaces the previous one. This is perfectly normal — work through the projects step by step!

---

## 🧩 Projects

The projects are organized from simple to complex. Each one builds on the previous ones, so working through them in order is recommended.

---

### 4.1 — Lighting System

Learn how to control the LED and read the button.

| Sketch | What it does |
|---|---|
| `1.1Blink` | LED blinks once per second (your "Hello World") |
| `1.2PWM` | LED fades in and out using PWM (Pulse Width Modulation) |
| `1.3Button` | Reads the button state and prints it on the Serial Monitor |
| `1.4Self-Locking_Button` | Makes a momentary button behave like a toggle switch |
| `1.5Lighting-System` | Press the button to turn the LED on; press again to turn it off |

---

### 4.2 — Light Control System

Use the photoresistor to detect ambient light levels.

| Sketch | What it does |
|---|---|
| `2.1Photocell-sensor` | Reads and prints the light value on the Serial Monitor |
| `2.2Light-Control-System` | LED turns on automatically when it gets dark (value < 800) |

---

### 4.3 — Alarm System

Detect motion with the PIR sensor and trigger an alarm.

| Sketch | What it does |
|---|---|
| `3.1PIR-Motion-Sensor` | Prints "Someone is here" or "No one" on the Serial Monitor |
| `3.2Passive-Buzzer` | Generates continuous sound from the buzzer |
| `3.3Buzzer-Tone` | Uses the `tone()` function to play a specific frequency |
| `3.4Buzzer-Music` | The buzzer plays a melody |
| `3.5Alarm-System` | PIR detects motion → buzzer sounds + LED blinks as an alarm |

---

### 4.4 — Rain Detection System

The steam sensor detects water on its surface (simulating rain).

| Sketch | What it does |
|---|---|
| `4.1Steam-Sensor` | Reads and prints the rain sensor value (0–4095) |
| `4.2Rainwater-Detection-System` | The more rain detected, the louder the buzzer sounds |

---

### 4.5 — Solar Power System

No code needed for this one! This project explores solar energy. When the solar panel receives light, the small LED turns on automatically. The brighter the light, the brighter the LED — it works with both sunlight and indoor lighting.

---

### 4.6 — Smart Feeding System

Automatically feed animals when they approach the feeding cabin.

| Sketch | What it does |
|---|---|
| `6.1Servo` | Opens and closes the feeding cabin door (servo 80°→180°) |
| `6.2Ultrasonic-Sensor` | Measures the distance to the nearest object (range: 3–8 cm) |
| `6.3Intelligent-Feeding-System` | When an animal is detected close to the cabin, the door opens automatically |

> ⚠️ Do not put your fingers near the cabin door while the servo is running!

---

### 4.7 — Temperature Control System

Monitor temperature and humidity, display values on the LCD, and control the fan.

| Sketch | What it does |
|---|---|
| `7.1DHT11` | Reads temperature and humidity and prints them on the Serial Monitor |
| `7.2LCD1602` | Displays text on the LCD screen |
| `7.3Motor` | Fan rotates left and right alternately every 2 seconds |
| `7.4Temperature-Control-System` | When temperature ≥ 29°C, the fan turns on automatically |

> ⚡ The fan motor is a high-power device. Always use batteries (not just USB) when running the fan.

---

### 4.8 — Soil Humidity Monitoring System

Check how dry or wet the soil is.

| Sketch | What it does |
|---|---|
| `8.1Soil-Humidity-Sensor` | Reads and prints the soil humidity value (0–4095) |
| `8.2Soil-Humidity-Testing-System` | LCD displays the value; buzzer alarms if soil is too dry (value < 200) |

---

### 4.9 — Water Level Monitoring System

Monitor the water level in the tank.

| Sketch | What it does |
|---|---|
| `9.1Water-Level-Sensor` | Reads and prints the water level value (0–4095) |
| `9.2Water-Level-Testing-System` | LCD displays the value; buzzer alarms if the level is too low (value < 200) |

---

### 4.10 — Auto-Irrigation System

The full automatic irrigation loop: sensors trigger the pump when needed.

| Sketch | What it does |
|---|---|
| `10.1Water-Pump` | Turns on the pump once when you send "a" from the Serial Monitor |
| `10.2Auto-irrigation` | LCD shows soil humidity and water level in real time. If soil is too dry (< 500) and water is available (> 1000), irrigation starts automatically. If water is too low (< 500), the pump stops and the buzzer alarms. |

> ⚠️ Be careful not to overflow the water tanks! Water on the electronics can cause short circuits or damage. Younger users should work with a parent or adult.

---

### 4.11 — Web-Controlled Smart Farm

Control the whole farm from any browser on your local network.

| Sketch | What it does |
|---|---|
| `11.0Connect-the-ESP32-to-the-Network` | Connects the board to Wi-Fi and prints its IP address |
| `11.1WiFi-HTML-HELLOWORLD` | Hosts a simple web page that says "Hello, World!" |
| `11.2WiFi-HTML-Smart-Farm` | Full web dashboard: shows all sensor values and lets you control the LED, fan, feeding cabin, and water pump |

**How to use it:**

1. Open the sketch and replace `your_SSID` and `your_PASSWORD` with your Wi-Fi credentials.
2. Upload the code. Open the Serial Monitor to see the IP address.
3. Connect your phone or computer to the **same Wi-Fi** network.
4. Type the IP address into any browser. That's your farm dashboard!

> ⚠️ You must use a **2.4 GHz** Wi-Fi network. The ESP32 does not support 5 GHz.

---

### 4.12 — App-Controlled Smart Farm

Control the farm from the **"IOT Farm"** mobile app.

| Sketch | What it does |
|---|---|
| `12.1APP-Smart-Farm` | Runs the full smart farm and connects it to the mobile app |

> **Important:** `BuzzerMusic.h` and `12.1APP-Smart-Farm.ino` must be in the same folder. Do not move them apart.

---

## 🌐 Web Control

After uploading `11.2WiFi-HTML-Smart-Farm`, open the IP address in your browser. You will see:

- **Sensor readings** at the top: temperature, humidity, soil moisture, light, water level, and rain.
- **Control buttons** below: toggle the LED, start/stop the fan, open/close the feeding cabin, activate the water pump.

All values update automatically. Any phone, tablet, or computer connected to the same Wi-Fi can access the page at the same time.

---

## 📱 App Control

The **"IOT Farm"** app is available for both Android and iOS.

- **Android:** Search for `IOT Farm` on [Google Play](https://play.google.com)
- **iOS:** Search for `IOT Farm` on the [App Store](https://apps.apple.com)

**How to connect:**

1. Make sure the ESP32 is running the `12.1APP-Smart-Farm` sketch.
2. Connect your phone to the **same 2.4 GHz Wi-Fi** as the ESP32.
3. Open the app and enter the ESP32's IP address in the top-right corner.

**What the app shows and controls:**

| Display | What it shows |
|---|---|
| 🌡️ Temperature | Real-time temperature from DHT11 |
| 💧 Humidity | Real-time air humidity |
| 🌱 Soil humidity | Real-time soil moisture |
| ☀️ Light | Sunlight / ambient brightness |
| 🪣 Water level | Water level in the tank |
| 🌧️ Rain | Analog rainfall value |

| Control | What it does |
|---|---|
| 💡 LED | Turn the farm light on or off |
| 🚰 Water Pump | Trigger manual irrigation |
| 🌀 Fan | Turn the temperature fan on or off |
| 🚪 Servo | Open or close the feeding cabin door |
| 🎵 Buzzer | Play a music tune |

---

## ⚠️ Safety Notes

Please read these before getting started, especially if younger users are involved.

- 💧 **Water and electronics don't mix.** Only the detection area of the water sensors should touch water. Never let water spill on other modules, wires, or the board. Spilling water on electronics can cause short circuits, heat damage, or — in extreme cases with wet batteries — even explosion.
- 🔋 **Use batteries for motor projects.** The fan and water pump need more power than a USB connection can provide. Always connect the 6 × AA battery pack when running projects 7.3, 7.4, 10.x, 11.x, and 12.x.
- 🤚 **Keep fingers away from the servo door.** The feeding cabin servo is strong enough to cause a pinch injury. Never put your fingers into the cabin while it is powered on.
- 🌡️ **If the servo gets hot and the door does not move**, turn off the power immediately. Check that the acrylic door makes proper contact with the gear and that no screws are binding the servo shell.
- 👨‍👩‍👧 **Younger users** should always work with a parent or adult present, especially for projects involving water.

---

## 🤝 Contributing

Contributions are welcome! If you want to improve the code, add a new project, or fix a bug:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/my-improvement`
3. Make your changes and commit them: `git commit -m "Add: description of change"`
4. Push to your fork: `git push origin feature/my-improvement`
5. Open a Pull Request describing what you changed and why.

If you find a bug or have a suggestion, feel free to [open an Issue](https://github.com/Federico19-1/Smart-Farm-Kit-for-Arduino-Codes/issues).

---

## 📜 License

This project is released under the **MIT License**.
See the [LICENSE](LICENSE) file for full details.

---

<div align="center">

Made with ❤️ — Happy building! 🌱

</div>
