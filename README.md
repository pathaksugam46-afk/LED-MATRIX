# 12×4 LED Matrix PCB

A compact **12×4 LED Matrix PCB** designed in **EasyEDA** using **two 74HC595D shift register ICs** and **four 2N4402 transistors**. The board is designed for Arduino and only requires **5V, GND, SER, CLK, and LATCH** connections to operate.

This project was created to learn PCB design, LED matrix multiplexing, and shift register communication while building a clean and professional PCB.

---

## Features

- 12 × 4 LED Matrix (48 LEDs)
- 2 × 74HC595D Shift Register ICs
- 4 × 2N4402 PNP Transistors
- Arduino Compatible
- Uses only 3 control signals
- Compact and professional PCB layout
- Easy to solder and assemble
- Designed in EasyEDA

---

## Hardware

### Main Components

- 48 × LEDs
- 2 × 74HC595D Shift Registers
- 4 × 2N4402 PNP Transistors
- 4 × 1kΩ Resistors
- 16 × 10kΩ Resistors
- 1 × 5-Pin Header
- Custom PCB

---

## Pinout

| PCB Pin | Description |
|---------|-------------|
| 5V | Power Supply |
| GND | Ground |
| SER | Serial Data |
| CLK | Shift Clock |
| LATCH | Storage Clock |

### Example Arduino Connections

| Arduino | PCB |
|----------|-----|
| 5V | 5V |
| GND | GND |
| D11 | SER |
| D13 | CLK |
| D10 | LATCH |

---

## Example Code

```cpp
#define DATA_PIN   11
#define CLOCK_PIN  13
#define LATCH_PIN  10

void setup() {
  pinMode(DATA_PIN, OUTPUT);
  pinMode(CLOCK_PIN, OUTPUT);
  pinMode(LATCH_PIN, OUTPUT);
}

void loop() {
  digitalWrite(LATCH_PIN, LOW);

  shiftOut(DATA_PIN, CLOCK_PIN, MSBFIRST, 0xAA);
  shiftOut(DATA_PIN, CLOCK_PIN, MSBFIRST, 0x55);

  digitalWrite(LATCH_PIN, HIGH);

  delay(500);
}
```

---

## Tools Used

- EasyEDA
- Arduino IDE

---

## Assembly Tools

- Temperature-controlled soldering iron
- Solder wire
- Flux
- Tweezers
- Flush cutter
- Multimeter (optional)

---

## Repository Structure

```
LED-Matrix-PCB/
│
├── Source/
│   └── LED_Matrix.epro
│
├── Gerber/
│   ├── Gerber.zip
│   ├── BOM.csv
│   └── PickAndPlace.csv
│
├── Firmware/
│   └── LED_Matrix_Test.ino
│
├── Images/
│   ├── Schematic.png
│   ├── PCB.png
│   ├── PCB_3D.png
│   └── Render.png
│
├── LICENSE
└── README.md
```

---

## Images

### Schematic

![Schematic](Images/Schematic.png)

### PCB Layout

![PCB](Images/PCB.png)

### 3D View

![3D PCB](Images/PCB_3D.png)

---

## Applications

- Arduino Projects
- LED Display
- Electronics Learning
- PCB Design Practice
- Shift Register Experiments
- Embedded Systems

---

## License

This project is released under the **MIT License**.

---

## Author

**Sugam Pathak**

Robotics Designer • PCB Designer • Embedded Systems Enthusiast

Designed in **EasyEDA** as a learning project to explore PCB design, LED matrix multiplexing, and Arduino-based hardware development.
