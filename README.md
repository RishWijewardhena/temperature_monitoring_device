# ESP32 High-Temperature MQTT Monitoring Device (Up to 300 °C)

This project is an ESP32-based temperature monitoring device capable of reading temperatures **up to 300 °C** and publishing them to an **MQTT server**.  
It supports Wi-Fi configuration through **Access Point (AP) mode**, and a **NeoPixel LED** displays connection and system status.

---

##  Features

- **High-temperature sensing (0–300 °C)**
- **MQTT publishing** of temperature readings
- **Access Point mode** for Wi-Fi setup via a built-in web page
- **Automatic reconnection** with stored Wi-Fi credentials
- **NeoPixel LED indicators** for AP mode, connection success, and errors

---

## 🛠️ Hardware Requirements

- ESP32 Development Board  
- High-temperature thermistor / RTD sensor (0–300 °C)  
- Single NeoPixel (WS2812B) LED  
- 5 V Power Supply  

---

##  Device Workflow

1. Device powers on  
2. If Wi-Fi credentials are missing → ESP32 starts in **AP Mode**  
3. User connects to AP and enters Wi-Fi credentials through a config page  
4. ESP32 switches to **Station Mode** and connects to Wi-Fi  
5. Temperature values are measured and published to MQTT  
6. NeoPixel LED shows system status  

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
- **Format:** JSON payload
- **Compatible With:** EMQX, HiveMQ, Home Assistant, Node-RED, etc.

### Example MQTT Payload

```json
{
  "temperature": 247.3,
  "unit": "C"
}
