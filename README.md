#  ESP32 High-Temperature MQTT Monitoring Device (Up to 300 °C)

This project is an ESP32-based temperature monitoring device capable of reading temperatures **up to 300 °C** and publishing them to an **MQTT server**.  
It supports Wi-Fi configuration through **Access Point (AP) mode**, uses a **NeoPixel LED** for system status indication, includes a **backup battery** for uninterrupted operation, and features a **custom-designed enclosure and PCB** developed specifically for this device.

---

## Features

- **High-temperature sensing (0–300 °C)**
- **MQTT publishing** of real-time temperature data
- **Access Point mode** for Wi-Fi setup via built-in configuration page
- **Automatic reconnection** with stored Wi-Fi credentials
- **NeoPixel LED indicators** for AP mode, Wi-Fi/MQTT connection, and errors
- **Backup battery support**  
  Ensures the device continues running during power failures
- **Custom enclosure design**  
  I designed and manufactured the physical enclosure for durability using solidworks
- **Custom PCB design**  
  The circuit is fully integrated into a professionally designed PCB for reliability and compactness

---

## 🛠️ Hardware Requirements

- ESP32 Development Board  
- High-temperature thermistor / RTD sensor (up to 300 °C)  
- Single NeoPixel (WS2812B) LED  
- 5V main power supply  
- Backup battery (Li-ion/LiPo) + charging module  
- **Custom PCB (designed and made for this device)**  
- **3D-printed or fabricated enclosure**

---

##  Device Workflow

1. Power on the device (main power or backup battery)  
2. If no Wi-Fi credentials → ESP32 enters **AP Mode**  
3. User connects to AP and enters Wi-Fi details  
4. Device switches to **Station Mode**  
5. Temperature is measured and published to MQTT  
6. NeoPixel LED displays live status  

---

##  NeoPixel LED Status

| Color | Status |
|-------|---------|
| 🔵 Blue | AP Mode (Wi-Fi setup) |
| 🟢 Green | Successfully connected (Wi-Fi + MQTT) |
| 🔴 Red | Error / Not connected |

---

##  MQTT Information

- **Protocol:** MQTT  
- **Client Library:** PubSubClient  
- **Message Format:** JSON  
- **Compatible With:** EMQX, HiveMQ, Node-RED, Home Assistant, etc.

### Example MQTT Payload

```json
{
  "temperature": 247.3,
  "unit": "C"
}
)

```
![WhatsApp Image 2025-12-09 at 07 45 11_d745960a](https://github.com/user-attachments/assets/3f453054-3e58-4266-a026-815fe7384a29)

