# Owl AFC-TC Expansion Board

![Owl AFC-TC Board Render](./images/Owl%20AFC-TC_top.png)

The **Owl AFC-TC** is an open-source expansion board for advanced multi-toolhead 3D printers running Klipper firmware. It is designed to support high-performance, modular printing systems with automatic filament changers and CAN-connected toolheads.

This board was inspired by the [AFC-Lite project by xbst](https://github.com/xbst/AFC-Lite) and builds upon its foundation with a broader feature set, more I/O, and support for complex toolchanger configurations. It is also compatible with the [AFC Klipper Add-On](https://github.com/ArmoredTurtle/AFC-Klipper-Add-On), allowing seamless integration into Klipper-controlled systems.

The Owl AFC-TC board is built to control up to **4 toolheads** and **4 independent filament changers**, each capable of handling **2 spools**, for a total of 8 spools in a fully automated, multi-material 3D printer.

## Feature Highlights

- **Powerful MCU**  
  Utilizes a high-performance 32-bit ARM Cortex-M7 STM32H723ZET6 microcontroller running at 550 MHz

- **Powerful 5V rail**
  On-board 5V buck converter allowing up to 12A output

- **Stepper and DC Motor Support**  
  - 8× TMC2209 stepper driver headers (24V) in UART mode for additional extruder steppers
  - 8× DRV8837 DC motor drivers (5V) for rewind motors

- **Sensor Inputs**  
  The board features 32 dedicated endstop-style inputs, each with external pull-up resistors and an individual indicator LED for real-time debugging. These inputs are purpose-built for AFC system integration and can be used as follows:

  - 8× AFC Buffer Sensors (4 units × 2 signals: `advance_pin` + `trailing_pin`)  
  - 16× AFC Stepper Sensors (8 units × 2 signals: `prep` + `load`)  
  - 4× AFC Hub Sensors (`switch_pin` for 4 hubs)  
  - 4× AFC Bypass Sensors (`bypass` signal for 4 units)

- **PWM Outputs**  
  - 3× PWM-controlled outputs (3A each), can be used for fans or heaters
    - Two with selectable voltage (5V or 24V)  
    - One fixed to 24V

- **Temperature Sensing**  
  - 2× Thermistor inputs with optional PT1000 support, selectable via jumper.

- **RGB & Neopixel Outputs**  
  - 4× Buffered RGB/Neopixel connections

- **Connectivity Options**  
  - USB connection
  - CANbus support (also functions as a U2C interface for Klipper)  
  - 4× main CANbus headers for toolhead connections  
  - 2× additional CANbus expansion headers  
  - Onboard selectable termination resistor for proper CAN line termination


## Specifications

| **Parameter**                         | **Details**                                                                 |
|-------------------------------------|------------------------------------------------------------------------------|
| **MCU**                             | ARM Cortex-M7 STM32H723ZET6 @ 550MHz                                        |
| **Input Voltage**                   | 24VDC 30A max                                                               |
| **5V Regulator**                    | TPS51385 Buck Converter – 5V @ 12A total (shared by logic, Neopixels, DC motors, etc.) |
| **Stepper Driver Support**          | 8× External TMC2209 (24V) in UART mode                                     |
| **DC Motor Driver Support**         | 8× Onboard DRV8837 (5V)                                            |
| **PWM Outputs**                     | 3× PWM (3A max each); two with selectable 5V or 24V, one fixed 24V         |
| **Always-On Fan Outputs**           | 2× Fixed 24V                                                               |                    |
| **Neopixel / RGB Outputs**          | 4× RGB headers (5A max per channel; total 5V output limited to 12A)        |
| **Thermistor Interfaces**           | 2× NTC with optional PT1000 support via jumper                             |
| **I2C Interfaces**                  | 2× I2C headers for external sensors (e.g., temp/humidity)                  |
| **CANbus Interfaces**               | 4× Primary CAN headers for toolheads, 2 × Additional expansion headers      |
| **CAN Termination**                 | Onboard jumper-selectable 120Ω resistor                                     |
| **USB Interface**                   | USB-C for Pi/PC communication and firmware updates                          |
| **CAN-to-USB Mode**                 | Can function as a Klipper U2C (USB-to-CAN) bridge                           |
| **GPIO Outputs**                    | 9 × Additional general-purpose outputs via header                           |
| **Endstop Inputs**                  | 32 × Inputs with pullups + indicator LEDs                                   |                   |
| **Firmware Update Methods**         | DFU via USB or Katapult via CAN                                             |
| **Board Dimensions**                | 168x89 mm                                                                   |


---

## License

This project is licensed under the  
**Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License**.  
You may use, modify, and share the design for non-commercial purposes with proper attribution and under the same license terms.

For more information, see:  
[https://creativecommons.org/licenses/by-nc-sa/4.0/](https://creativecommons.org/licenses/by-nc-sa/4.0/)
