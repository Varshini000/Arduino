# Arduino
# 🩺 MAX30100 Pulse Oximeter Webserver using NodeMCU ESP8266

This project demonstrates how to build a **Pulse Oximeter Web Server** using the **NodeMCU ESP8266** and **MAX30100 Pulse Oximeter Sensor**.  
It measures **Heart Rate (BPM)** and **Oxygen Saturation (SpO₂)** levels and displays them on a **webpage hosted by the ESP8266**.  
You can view live readings from any smartphone or PC connected to the same WiFi network.

---

## 📘 Table of Contents
- [Overview](#overview)
- [Components Required](#components-required)
- [Circuit Diagram](#circuit-diagram)
- [Library Installation](#library-installation)
- [Code Explanation](#code-explanation)
- [How to Upload the Code](#how-to-upload-the-code)
- [Web Dashboard Preview](#web-dashboard-preview)
- [Troubleshooting](#troubleshooting)
- [Author](#author)
- [License](#license)

---

## 🧠 Overview
The **MAX30100** sensor combines two LEDs (red and IR) and a photodetector to measure pulse rate and SpO₂ levels.  
The **ESP8266** reads data from the MAX30100 using I²C communication and hosts a **local web server** to display real-time sensor readings.

**Features:**
- Real-time monitoring of BPM and SpO₂.
- Local Wi-Fi webserver viewable on any browser.
- AJAX-based live data updates without refreshing.
- Simple and compact IoT biomedical application.

---

## 🧩 Components Required

| S.N | Component Name | Description | Quantity |
|-----|----------------|-------------|-----------|
| 1 | NodeMCU ESP8266 | WiFi Development Board | 1 |
| 2 | MAX30100 Sensor | Heart Rate & SpO₂ Sensor | 1 |
| 3 | Breadboard | Mini Breadboard | 1 |
| 4 | Jumper Wires | Male-to-Female | 5 |

---

## 🔌 Circuit Diagram

| MAX30100 Pin | NodeMCU Pin |
|---------------|-------------|
| VCC | 3.3V |
| GND | GND |
| SCL | D1 (GPIO5) |
| SDA | D2 (GPIO4) |
| INT | D0 (GPIO16) |

---

## ⚙️ Library Installation

Before uploading the code, install the following libraries in **Arduino IDE** or **VS Code (Arduino Extension):**

1. **MAX30100_PulseOximeter** by *Connor Huffine*  
   *(Library Manager → Search “MAX30100”)*
2. **ESP8266WebServer** by *ESP8266 Community*

Also ensure you have installed the **ESP8266 board support** in Arduino IDE:  
- File → Preferences → Additional Board URL:  


---

## 💻 Code Explanation

- Connects NodeMCU to your WiFi network using SSID & Password.
- Initializes the MAX30100 sensor.
- Starts a local web server at `http://<your-local-IP>/`
- Sends real-time BPM and SpO₂ readings using **AJAX** for live updates.

Replace WiFi credentials in code:
```cpp
const char* ssid = "Your_WiFi_Name";
const char* password = "Your_WiFi_Password";
