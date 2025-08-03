# Open ESP32 Smart OLED Display Hardware

### Free as in Freedom

## ATTENTION - This repo is WIP!

This repository provides the complete open-source hardware design for a compact, Wi-Fi-capable smart display using an ESP32 and a 128x64 I2C OLED module. The project includes a manufacturable PCB and a 3D-printable case. An optional capacitive touch sensor can be added to the case.

This project is ideal for developers who want to integrate a small display into smart home interfaces, information kiosks, sensor dashboards, or other embedded projects. Examples include uses with ESPHome for HomeAssistant or weather display.

## Hardware Overview

- ESP32-based design (supports Wi-Fi and Bluetooth)
- 128x64 I2C OLED (SSD1306 or similar)
- Optional touch sensor header (TTP223)
- Compact 3D-printable enclosure
- USB C power
- Designed for easy customization and integration
- Parts sourced from Digikey find list [here](./hardware/digikey.csv)
- Display, touch sensor and USB C port sourced from aliexpress
- PCB ordered from [PCBWay](https://www.pcbway.com)

### PCB Highlights

- Minimal footprint
- Breakout headers for touch input
- Unused GPIO exposed for easy expansion
- Designed using only free software (KiCad and FreeCAD)
- High quality PCB ordered from [PCBWay](https://www.pcbway.com)


## Requirements

- ESP32-WROOM Module (ESP-WROOM-C2)
- 128x64 OLED display with I2C interface
- TTP223 Capacitive Touch sensor module (optional)
- Soldering equipment
- 3D printer for case (optional but recommended)
- PCB

## Usage

This repository provides the physical design only. You are free to write or upload your own firmware using Arduino, PlatformIO, or ESP-IDF. I2C display and touch sensor libraries are widely supported.

For a full list of pin connections and assembly steps, see [hardware/assembly.md](./hardware/assembly.md).

## License

This project is licensed under the MIT License. You are free to use, modify, and distribute it as needed.

## Contributing

Issues and pull requests for improvements to the hardware design or enclosure are welcome.

### Notes
- I have used a cheap USB C breakout to which I added only a single 5.1 k resistor (which is technically is not within USB spec, but it works)
- The antenna of the WROOM module is not blocked by any traces on thee main pcb, however it could possibly interfere with the display. In practice the module works fine and no interference is noticed.
- In the future I will design another open smart display again using an ESP WROOM boards and an SPI LCD Screen.