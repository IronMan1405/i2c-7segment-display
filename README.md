# I2C 7-Segment Display Module
![Platform](https://img.shields.io/badge/Platform-Arduino%20%7C%20RaspberryPi-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![KiCad](https://img.shields.io/badge/KiCad-8.0-orange)
![Status](https://img.shields.io/badge/Status-Active-success)

A compact **4-digit, I²C-based 7-segment display module** designed around the **HT16K33 LED driver IC**.  
This project combines open-source **hardware**, **firmware**, and **documentation** to create a fully standalone, programmable numeric display for Arduino, ESP, and Raspberry Pi systems.

---

## 🚀 Overview

The project implements a simple and efficient I²C-driven display interface using the **HT16K33**, capable of controlling up to 16×8 LEDs (suitable for four 7-segment displays plus dots).  

It is designed for:
- DIY and educational electronics projects  
- Embedded system displays  
- Robotics or smart-device dashboards

---

## 🧩 Features

- 🧠 **I²C-based interface** (2-wire communication)
- 🔢 **4-digit common-cathode 7-segment display**
- 💡 Optional **decimal points and colon/dot segments**
- ⚙️ Compatible with **Arduino**, **ESP8266/ESP32**, and **Raspberry Pi**
- 🖥️ Fully open-source **KiCad hardware design**
- 🔌 Designed for easy **PCB manufacturing (Gerber included)**

---

## 📁 Repository Structure

- [`docs/photos/`](docs/photos/) – Images and assembly documentation
- [`firmware/`](firmware/)
    - [`arduino/`](firmware/arduino/) – Arduino source code
    - [`raspberrypi/`](firmware/raspberrypi/) – Python or C code for Raspberry Pi
- [`hardware/`](hardware/)
    - [`datasheets/`](hardware/datasheets/) - Reference datasheets of HT16K33, 7-segment display
    - [`gerber/`](/hardware/gerber/) – PCB fabrication-ready Gerber files
    - [`i2c-7segment-display/`](hardware/i2c-7segment-display/) – KiCad schematic & PCB files
    - [`library/`](hardware/library/)
        - [`symbols/`](hardware/library/symbols/) – Custom HT16K33 symbol for KiCad
- [`.gitignore`](.gitignore) – Ignored build/temp files
- [`LICENSE`](LICENSE) - License file
- [`README.md`](README.md) – This file 

---

## ⚙️ Hardware Details

- **Controller IC:** HT16K33 (20-pin SOP)
- **Display Type:** 4× Common Cathode 7-Segment (e.g., Cromatek D168K)
- **Supply Voltage:** 5V (typical)
- **Communication Protocol:** I²C  
  - **SDA →** Data  
  - **SCL →** Clock  
- **Default I²C Address:** `0x70` (configurable via address pins)
- **Resistors:** Individual current-limiting resistors per LED segment
- **PCB Design Software:** KiCad 8.0

---

## 🔌 Connections (Typical Setup)

| HT16K33 Pin | Function | Description |
|--------------|-----------|-------------|
| VCC | Power | +5V supply |
| GND | Ground | Common ground |
| SDA | I²C Data | Connect to MCU SDA |
| SCL | I²C Clock | Connect to MCU SCL |
| ROW/COM0–7 | Segment anode control lines |
| COL0–15 | Digit cathode control lines |

---

## 🧠 Firmware Overview

### Arduino
Located in `/firmware/arduino/`
- Example sketches for testing digits, scrolling numbers, and dots.
- Wire library used for I²C communication.

### Raspberry Pi
Located in `/firmware/raspberrypi/`
- Python scripts using `smbus` or `adafruit-ht16k33` library.
- Simple display test examples included.

---

## 📘 Datasheets

| Component | File |
|------------|------|
| **Cromatek D168K 7-segment** | `/hardware/datasheets/Cromatek D168K.pdf` |
| **HT16K33 LED Driver** | `/hardware/datasheets/ht16k33v110.pdf` |

---

## 🛠️ Getting Started

### 1. Hardware
- Open `/hardware/i2c-7segment-display/i2c-7segment-display.kicad_pro` in **KiCad 9**.
- To add the custom HT16K33 symbol:
  - `Preferences → Manage Symbol Libraries → Add`
  - Select: `hardware/library/symbols/ht16k33.kicad_sym`

### 2. Firmware
- For Arduino: upload from `/firmware/arduino/`
- For Raspberry Pi: run test script from `/firmware/raspberrypi/`

---

## 📸 Documentation

All photos, wiring diagrams, and assembly references are in:
/docs/photos


---

## 📜 License

This project is licensed under the **MIT License** — see [LICENSE](./LICENSE) for details.  
You’re free to use, modify, and distribute it with attribution.

---

## 💡 Future Work

- [ ] Add 3D model for HT16K33  
- [ ] Add PCB assembly photos and demo video  
- [ ] Develop Arduino library for dynamic animations  

---

## ✨ Author

**Dakshesh Nankani**  
Electronics & Robotics Enthusiast | Open Source Developer  

email: [daksheshnankani1405@gmail.com]  

[LinkedIn](https://linkedin.com/in/dakshesh-nankani-319643377)
---

> “Simplicity is the ultimate sophistication.” — Leonardo da Vinci
