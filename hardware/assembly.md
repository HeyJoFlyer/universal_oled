# ESP32 Smart OLED Display – Assembly Instructions

These instructions cover the mechanical and electrical assembly of the ESP32 Smart OLED Display hardware. This project does not include firmware. You are expected to upload or develop your own software using the ESP32 platform of your choice.

## WIP

## Components Required

Components required can be found [here](./components.md) (list for digikey components.)

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

- Send the gerber `hardware/gerber.zip` to a PCB manufacturer (i used [PCBWay](https://www.pcbway.com)).
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

- Print the case file `case/Enclosure.3mf`. (Print both the back cover and the main case)
- Use PLA or ABS with standard print settings.
- Insert the assembled PCB into the case and glue it in place.
- Glue the touch sensor (optional) and USB-C connector.
- Close the housing with glue after you have confirmed that your board works and you have flashed the correct firmware.


---

## Custom Firmware

This hardware supports any firmware platform compatible with ESP32 and SSD1306 OLEDs:

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
- If you use the ESP32-C3-WROOM-02 module or similar you can connect GPIO 18 and GPIO 19 to the data lines of the Usb C connector for easy reflashing according to the [datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-c3-wroom-02_datasheet_en.pdf).

---

## Contact

For questions or contributions, open an issue on the GitHub repository.
