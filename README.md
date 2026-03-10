# 🛡️ Smart Home IoT Security & Fire Alarm

An IoT-based smart home monitoring system built with the ESP8266 (NodeMCU). This project provides real-time local alerts and cloud-based tracking for both fire hazards and room intrusions.

## ✨ Features
* **Dual-Threat Detection:** Monitors for both fire (Flame Sensor) and motion/intruders (IR Sensor).
* **Smart Audio Alerts:** Uses custom logic to change the active buzzer's rhythm:
  * 🚨 **Fire:** Solid, continuous screaming tone.
  * ⚠️ **Intrusion:** Rapid, pulsing warning beep.
* **Local Dashboard:** Real-time system status displayed on an I2C OLED screen.
* **Cloud Logging:** Automatically pushes event data via Wi-Fi to a ThingSpeak cloud dashboard.
* **Mobile Monitoring:** Live graphs accessible globally via mobile apps (ThingView/ThingShow).

## 🧰 Hardware Components
* NodeMCU ESP8266 (Wi-Fi Microcontroller)
* IR Obstacle Avoidance Sensor (Active-Low)
* Flame Sensor (Active-Low)
* Active Buzzer Module (Active-Low)
* 0.96" SSD1306 OLED Display (I2C)
* Breadboard & Jumper Wires

## 🔌 Circuit Wiring Diagram
**Power Distribution (via Breadboard):**
* NodeMCU `3V` ➔ Breadboard `+` (Red Rail)
* NodeMCU `GND` ➔ Breadboard `-` (Blue/Black Rail)
* *All sensor VCC/GND pins connect to these rails.*

**Data Connections:**
* **OLED SDA** ➔ NodeMCU `D2`
* **OLED SCL** ➔ NodeMCU `D1`
* **Buzzer I/O** ➔ NodeMCU `D6`
* **Flame D0** ➔ NodeMCU `D5`
* **IR Sensor OUT** ➔ NodeMCU `D7`

## 🚀 Setup Instructions
1. Clone this repository and open the `.ino` file in the Arduino IDE.
2. Install the required libraries: `Adafruit GFX`, `Adafruit SSD1306`.
3. Create a free [ThingSpeak](https://thingspeak.com) account and create a new channel with **Field 1 (Fire)** and **Field 2 (Motion)** enabled.
4. Update the code with your specific credentials:
   ```cpp
   const char* ssid = "YOUR_WIFI_NAME";           
   const char* password = "YOUR_WIFI_PASSWORD";   
   String writeAPIKey = "YOUR_THINGSPEAK_API_KEY";
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a10f194a-1833-49d1-9580-53d31801c7af" />
<img width="1920" height="1080" alt="Screenshot (258)" src="https://github.com/user-attachments/assets/f7024f22-a6ba-4c9a-81be-9907b84c3c6d" />

