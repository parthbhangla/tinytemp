# TinyTemp Thermometer  
Custom PCB thermometer built with an **ATtiny85 microcontroller**, **TMP36 temperature sensor**, and **SSD1306 OLED display**.  
Designed in **KiCad**, assembled with **soldering**. Firmware written in **C**.  

---

## Overview  
TinyTemp is a compact, low-power thermometer system designed to display real-time temperature readings in °C and °F.  
It provides alerts when the temperature exceeds a defined threshold ("TOO HOT"), and was engineered under strict  
design constraints (PCB area < 3 sq. in., battery-powered, cost <$15 in bulk).  

---

## Features  
- Real-time temperature measurement (°C / °F)  
- Threshold alert at 18 °C with “TOO HOT” OLED warning  
- Low-power design with >2 months battery life on 4×AA batteries  
- Compact PCB: 2.9 cm × 4.95 cm (<3 sq. in. requirement)  
- Firmware with **ADC sampling, averaging, and calibration**  

---

## Hardware Design  
- **Microcontroller:** ATtiny85  
- **Sensor:** TMP36 analog temperature sensor  
- **Display:** SSD1306 128×64 OLED  
- **Voltage Regulation:** 6V (AA batteries) → 3.3V linear regulator with decoupling capacitors  
- **PCB Design:** KiCad (schematic + layout), board size 2.23 in²  
- **Assembly:** Hand-soldered components, oscilloscope validation of sensor signal  

Schematic and PCB Layout are included in the `/images` folder.  

---

## Firmware  
Firmware written in **C** for the ATtiny85 using AVR toolchain.  

Key functionality:  
- Configures ADC to sample TMP36 sensor on PB4  
- Averages 25 samples for noise reduction  
- Converts analog voltage → temperature (°C and °F)  
- Displays values on SSD1306 OLED  
- Threshold alert: “TOO HOT” if temp ≥ 18 °C  

Code is located in `/code`.  

---

## Testing & Validation  
- Verified ±4 °C accuracy with oscilloscope + calibrated thermometer  
- Battery life estimated at ~2.5 months (3.3 mA current draw, 6000 mAh capacity)  
- All project requirements validated (see report in `/docs/TinyTempReport.pdf`)  

---

## Demo  

| Schematic (KiCad) | PCB Layout (KiCad) |
|-------------------|---------------------|
| <img width="400" alt="Schematic" src="https://github.com/user-attachments/assets/1358d0d7-7f8c-4f40-b0f4-a4d669c39685" /> | <img width="400" alt="PCB_Layout" src="https://github.com/user-attachments/assets/98ee0a00-5f21-4999-8d80-8a597f8dc55e" /> |

| Assembled Board (soldered) | OLED Display Output |
|----------------------------|----------------------|
| <img width="400" alt="Assembled" src="https://github.com/user-attachments/assets/f8a2ba34-9b91-4b55-984e-9a626b5be081" /> | <img width="300" alt="Display" src="https://github.com/user-attachments/assets/0efd99cb-592b-4999-8bfc-19911444a46a" /> |



## Skills Demonstrated

- **PCB design & layout (KiCad)**  
- **Firmware development in C** (ATtiny85, ADC, I²C OLED)  
- **Hardware prototyping** (soldering, debugging with oscilloscope)  
- **Requirements-driven engineering** (area, cost, power constraints)  

---

## License  
MIT License. Free to use and modify.  

---

