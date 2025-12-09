#  ESP32 High-Temperature MQTT Monitoring Device (Up to 300 °C)

This project is an ESP32-based temperature monitoring device capable of reading temperatures **up to 300 °C** and publishing them to an **MQTT server**.  
It supports Wi-Fi configuration through **Access Point (AP) mode**, uses a **NeoPixel LED** for status indication, and includes a **backup battery** to ensure continuous operation during power loss.

---

##  Features

- **High-temperature sensing (0–300 °C)**
- **MQTT publishing** of real-time temperature readings
- **Access Point mode** for Wi-Fi setup through a built-in configuration page
- **Automatic reconnection** using stored Wi-Fi credentials
- **NeoPixel LED indicators** for AP mode, MQTT status, and errors
- **Backup battery support**  
  Ensures the ESP32 continues running and sending data even if the main power source is disconnected.

---

## 🛠️ Hardware Requirements

- ESP32 Development Board  
- High-temperature thermistor / RTD sensor (0–300 °C)  
- Single NeoPixel (WS2812B) LED  
- 5 V main power supply  
- **Backup battery (Li-ion or LiPo) with charging module**  

---

##  Device Workflow

1. Device powers on (main supply or backup battery)  
2. If Wi-Fi credentials are missing → ESP32 starts in **AP Mode**  
3. User connects to AP and enters Wi-Fi credentials  
4. ESP32 switches to **Station Mode**  
5. Temperature data is measured and published to MQTT  
6. NeoPixel LED indicates the current status  

---

##  NeoPixel LED Status

| Color | Status |
|-------|---------|
| 🔵 Blue | AP Mode (Wi-Fi setup) |
| 🟢 Green | Connected (Wi-Fi + MQTT OK) |
| 🔴 Red | Error / Not connected |

---

##  MQTT Information

- **Protocol:** MQTT (PubSubClient)
- **Data Format:** JSON
- **Compatible Platforms:** EMQX, HiveMQ, Node-RED, Home Assistant, etc.

### Example MQTT Payload

```json
{
  "temperature": 247.3,
  "unit": "C"
}
![WhatsApp Image 2025-12-09 at 07 45 11_d745960a](https://github.com/user-attachments/assets/52b3262e-134a-417e-b8de-76dd1e1f6854)
