##ESP32 High-Temperature MQTT Monitor (Up to 300 °C)

A compact ESP32-based temperature monitoring device capable of measuring up to 300 °C and publishing real-time readings to an MQTT server. The device supports smart Wi-Fi configuration through Access Point mode, and a NeoPixel LED indicates system and connection status.

#⚡ Features

High-temperature monitoring (0–300 °C)
Suitable for industrial or high-heat environments.

MQTT data publishing
Sends temperature readings to a configured MQTT broker at regular intervals.

Smart Wi-Fi setup (AP Mode)
If no credentials are stored, the ESP32 becomes an Access Point.
Users can enter Wi-Fi credentials through a built-in configuration webpage.

Automatic reconnect + credential storage
Wi-Fi details are saved in non-volatile memory.

NeoPixel LED status indicator

🔵 AP Mode (Wi-Fi setup)

🟢 Connected (Wi-Fi + MQTT OK)

🔴 Error / Not connected

#🛠️ Hardware Requirements

ESP32 Development Board

High-temperature thermistor / RTD sensor (0–300 °C)

NeoPixel (WS2812B) single LED

Power supply (5V)

📡 Workflow

Power on device

ESP32 starts in AP Mode if no Wi-Fi saved

User connects to AP → enters Wi-Fi details

Device connects to Wi-Fi

Temperature data is continuously published to MQTT

NeoPixel LED shows current status
