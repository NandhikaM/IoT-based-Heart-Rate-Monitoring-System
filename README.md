# IoT-Based Heart Rate Monitoring System

## Overview

The **IoT-Based Heart Rate Monitoring System** utilizes the **MAX30100 Pulse Oximeter** sensor to measure heart rate and SpO2 (oxygen saturation) levels. The measured data is displayed on an **SSD1306 OLED screen** and transmitted via **WiFi** for real-time monitoring.

---

## Features

- **Accurate Heart Rate & SpO2 Measurement** using the MAX30100 sensor.
- **OLED Display** for real-time data visualization.
- **Graphical Beat Detection** with the Adafruit GFX library.
- **Serial Output Logging** for debugging and data tracking.

---

## Components Required

- **ESP32 Development Board**
- **MAX30100 Pulse Oximeter Sensor**
- **0.96" SSD1306 OLED Display** (I2C)
- **Jumper Wires**
- **Power Supply (3.3V/5V)**

---

## Libraries Used

Ensure the following libraries are installed in the **Arduino IDE**:

- `Wire.h` - I2C communication.
- `MAX30100_PulseOximeter.h` - Sensor data processing.
- `Adafruit_GFX.h` - OLED graphics rendering.
- `Adafruit_SSD1306.h` - OLED display control.
  
---

## Circuit Connections

| Component | ESP32 Pin |
|-----------|------------|
| MAX30100 SDA | GPIO 21 |
| MAX30100 SCL | GPIO 22 |
| OLED SDA | GPIO 21 |
| OLED SCL | GPIO 22 |
| MAX30100 VCC | 3.3V |
| MAX30100 GND | GND |

---

## Code Functionality

### 1. Initialization (`setup()`)

- Initializes the **Serial Monitor** for debugging.
- Sets up the **OLED Display** and prints "Pulse Oximeter".
- Configures the **MAX30100 sensor** and IR LED current.
- Registers the **onBeatDetected()** callback function.
- Connects ESP32 to **WiFi** for IoT functionality.

### 2. Real-Time Data Processing (`loop()`)

- Continuously updates **MAX30100 sensor readings**.
- Displays **BPM & SpO2** values on the OLED screen.
- Uses `drawLine()` for **graphical heartbeat visualization**.
- Transmits **real-time data to a cloud server or mobile app**.

### 3. Display Functions

- `display_data(int bpm, int spo2)`: Updates OLED with real-time values.
- `drawLine(int *x_pos)`: Creates a scrolling effect for heartbeat visualization.
- `heart_beat(int *x_pos)`: Renders the **heart pulse waveform** on OLED.

---

## How to Use

1. Connect the **MAX30100 sensor** and **OLED display** to the ESP32 as per the circuit diagram.
2. Upload the code to the ESP32 board using **Arduino IDE**.
3. Open the **Serial Monitor** to check the BPM and SpO2 values.
4. Observe **real-time updates** on the OLED display.

---







