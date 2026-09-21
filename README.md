# 12×4 LED Matrix PCB

A simple 12×4 LED Matrix PCB designed in EasyEDA. This board is controlled using two 74HC595 shift register ICs, which reduce the number of Arduino I/O pins needed to drive the LEDs. The PCB is designed with a clean and compact layout for easy assembly and reliable performance.

This project can be used for learning multiplexing, shift registers, LED control, and basic PCB design.

---

## Features

- 12×4 LED matrix (48 LEDs)
- Uses 2 × 74HC595 shift register ICs
- Works with Arduino boards
- Only three Arduino control pins required
- Compact and professional PCB layout
- Easy to solder and assemble
- Designed in EasyEDA

---

## Arduino Connections

| PCB Pin | Arduino Pin |
|---------|-------------|
| 5V | 5V |
| GND | GND |
| DATA (SER) | Any Digital Pin |
| CLOCK (SRCLK) | Any Digital Pin |
| LATCH (RCLK) | Any Digital Pin |

Example:

```cpp
DATA  -> D11
CLOCK -> D13
LATCH -> D10
```

---

## Components

- 48 × LEDs
- 2 × 74HC595 Shift Register IC
- Current limiting resistors
- Pin Header
- Decoupling capacitors
- PCB

---

## Software

The board can be programmed using the Arduino IDE. Since it uses the 74HC595 shift register, you can control the LEDs with the `shiftOut()` function or any compatible library.

---

## Designed With

- EasyEDA
- Arduino IDE

---

## Project Images

Add your PCB images here.

```
Images/
├── Schematic.png
├── PCB.png
├── PCB_3D.png
└── Finished_Board.png
```

---

## Author

**Sugam Pathak**

This PCB was designed as a personal learning project to improve my PCB design skills and create a clean, professional LED Matrix board that can be easily used with Arduino.
