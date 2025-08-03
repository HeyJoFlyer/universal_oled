# ESP32 Smart OLED Display – Assembly Instructions

These instructions cover the mechanical and electrical assembly of the ESP32 Smart OLED Display hardware. This project does not include firmware. You are expected to upload or develop your own software using the ESP32 platform of your choice.

## Components Required

### Required
- 1 × ESP32 Dev Module (WROOM-32 recommended)
- 1 × 0.96" 128x64 OLED Display (I2C, SSD1306)
- 1 × Custom PCB (Gerbers provided)
- 1 × 3D Printed Case
- Wires, solder
- Any type of glue

### Optional
- 1 × Capacitive Touch Sensor Module (TTP223)
- JST XTH connector for better modularity


## Tools Required

- Soldering iron and solder
- Flush cutters
- 3D printer (or access to one)
- Multimeter (optional for verification)

---

## Step-by-Step Assembly

### 1. PCB Fabrication

- Send the files from `hardware/gerbers/` to a PCB manufacturer (i used [PCBWay](https://www.pcbway.com)).
- Choose 1mm or 1.2mm thickness
- For sustainability choose HASL Lead free or ENIG (ENIG is absolutely not needed)

### 2. Soldering Components

- Solder the ESP32 module to the PCB.
- Solder the OLED module headers.
- Solder optional headers for the touch sensor if you plan to use one.


### 3. Touch Sensor (Optional)

- If using a touch sensor (TTP223 or similar), mount it on cutout spot and wire it to the dedicated header or directly to the PCB.
- It connects to a single GPIO pin. Ensure your firmware reads this pin with pullup enabled.

### 4. 3D Printed Case

- Print the case file `case/smart_display_case.3mf`. (Print both the back cover and the main case)
- Use PLA or ABS with standard print settings.
- Insert the assembled PCB and OLED into the case.
- Secure with screws, hot glue, or pressure fit depending on design.

### 5. Power Options

- The board can be powered via the ESP32’s micro-USB port.
- If your use case requires mobility, a LiPo battery and charger module can be added and connected to the VIN/GND rails.

---

## Custom Firmware

This hardware supports any firmware platform compatible with ESP32 and SSD1306 OLEDs:
- Arduino with `Adafruit_SSD1306` and `Wire.h`
- PlatformIO
- ESP-IDF
- CircuitPython or MicroPython

Example features you could add:
- Display time, temperature, humidity
- Wi-Fi signal or IP address
- API-based data (weather, calendars)
- Touch-based toggle display modes

---

## Notes

- OLED default I2C address is usually `0x3C`.
- I2C pins are typically GPIO 21 (SDA) and GPIO 22 (SCL) on ESP32.
- If the touch sensor is not responsive, verify GPIO configuration in your firmware.

---

## Contact

For questions or contributions, open an issue on the GitHub repository.
