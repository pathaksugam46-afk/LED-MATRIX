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

---

## Why I Built This

I built this 12×4 LED Matrix PCB to learn how LED matrix displays work and to improve my PCB design skills. Instead of using a ready-made module, I wanted to design the circuit from scratch using 74HC595 shift registers and transistors. This project helped me understand LED multiplexing, shift register communication, schematic design, PCB layout, and component placement.

During the project, I:
- Designed the complete schematic in EasyEDA.
- Connected all 48 LEDs into a 12×4 matrix.
- Used two 74HC595D shift registers to reduce the number of Arduino I/O pins.
- Added four 2N4402 PNP transistors for row control.
- Designed and routed the PCB from scratch.
- Improved the PCB by moving the ICs and some resistors to the back side to save space and create a cleaner layout.
- Added a power indicator LED, decoupling capacitors, and mounting holes.
- Fixed DRC errors, optimized routing, and prepared the board for manufacturing.

This project gave me practical experience in PCB design, circuit organization, and hardware debugging while creating a reusable LED matrix module for future Arduino projects.

## Hardware

### Main Components

- 48 × LEDs
- 2 × 74HC595D Shift Registers
- 4 × 2N4402 PNP Transistors
- 4 × 1kΩ Resistors
- 16 × 10kΩ Resistors

---


## Bill of Materials (BOM)

| Qty | Component | Designators | Package | Unit Price (USD)* | Total |
|---:|-----------|-------------|---------|------------------:|------:|
| 48 | Red LED | LED2–LED49 | 0402 | $0.03 | $1.44 |
| 1 | Green Power LED | LED50 | 0603 | $0.03 | $0.03 |
| 2 | 74HC595D Shift Register IC | U1, U2 | SOIC-16 | $0.02 | $0.04 |
| 4 | 2N4402 PNP Transistor | Q1–Q4 | TO-92 | $0.06 | $0.24 |
| 13 | 10kΩ Resistor | R1–R5, R10–R16, R18 | 0805 | $0.001 | $0.01 |
| 4 | 1kΩ Resistor | R6–R9 | 0805 | $0.001 | $0.00 |
| 1 | 2-Pin Header | H1 | 1.27mm TH | $0.01 | $0.01 |
| 1 | 3-Pin Header | H2 | 1.27mm TH | $0.01 | $0.01 |

| | | | **Estimated Total Component Cost** | | **≈ $1.78 USD** |
## Pinout
<img width="597" height="438" alt="Screenshot 2026-09-24 123341" src="https://github.com/user-attachments/assets/2a03b7f0-6582-43ed-8f5d-eb06bfd5dd70" />


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



## Images

### Schematic

<img width="886" height="512" alt="Schematic" src="https://github.com/user-attachments/assets/a8f30dd3-6f0a-46d6-b860-554d4b586e43" />

---

### PCB Layout

#### Front

<img width="983" height="447" alt="PCB Front" src="https://github.com/user-attachments/assets/2a3ba879-41bf-410d-82c5-8fe156413696" />

#### Back

<img width="1127" height="761" alt="Screenshot 2026-09-24 123706" src="https://github.com/user-attachments/assets/1590d386-3799-4ccf-99d1-51e8f6214fa2" />

---

### 3D View

#### Front

<img width="1230" height="715" alt="3D Front" src="https://github.com/user-attachments/assets/0c3b79a0-f5f3-4ba8-8b01-ac5c6a871782" />

#### Back

<img width="1126" height="732" alt="3D Back" src="https://github.com/user-attachments/assets/ed304096-d4c4-465f-9250-e10aa148dd2e" />
---

## Applications

- Arduino Projects
- LED Display
- Electronics Learning


## Author

**Sugam Pathak**

Robotics Designer • PCB Designer

Designed in **EasyEDA** as a learning project to explore PCB design, LED matrix multiplexing, and Arduino-based hardware development.
MADE FOR HACK CLUB
