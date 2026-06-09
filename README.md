# ESP32 Duino-Coin Miner with GC9A01 Round TFT Display

Monitor your Duino-Coin mining stats in real time using an ESP32 and a GC9A01 1.28-Inch Round LCD TFT Display. View hashrate, shares, and node directly from your device, with a tachometer ring that scales with kH/s.

## What You Need

- ESP32 development board (WROOM-32D or similar)
- GC9A01 1.28-Inch Round LCD TFT Display (240x240)
- Jumper wires

## Wiring

| TFT Pin | ESP32 GPIO |
|---------|------------|
| VCC     | 3.3V       |
| GND     | GND        |
| SCL     | GPIO 18    |
| SDA     | GPIO 23    |
| DC      | GPIO 05    |
| CS      | GPIO 15    |
| RST     | GPIO 04    |

## Required Libraries

Install the following via Arduino IDE → Sketch → Include Library → Manage Libraries:

- Adafruit GC9A01A
- Adafruit GFX
- TridentTD_EasyFreeRTOS32
- ArduinoJson

## Setup

1. Go to [duinocoin.com](https://duinocoin.com/) and create an account
2. Click Get Started and follow the instructions for the ESP32 board
3. Unzip the folder and open the main `.ino` in Arduino IDE
4. Replace the `DisplayHal.h` file with the one provided in this repo
5. Open `Settings.h` and fill in your details:

```cpp
char *DUCO_USER = "your_username";
char *MINER_KEY = "your_mining_key";
char *RIG_IDENTIFIER = "your_rig_name";
const char SSID[] = "your_wifi_name";
const char PASSWORD[] = "your_wifi_password";
```

6. Select your board and port in Arduino IDE and click Upload

## Display Features

- Large hashrate readout in the center
- Tachometer ring around the edge that scales green → yellow → orange → red with kH/s
- WiFi signal bars and ping
- Accepted/total shares and accept rate
- Node name, difficulty, share rate, uptime, and IP address

Adjust `MAX_KH` in `DisplayHal.h` to match your expected peak hashrate (default 200).

## Acknowledgements

Based on the official [Duino-Coin](https://github.com/revoxhere/duino-coin) ESP miner by the Duino-Coin Team & Community © MIT Licensed.

## License

MIT License — see [LICENSE](LICENSE) for details.
