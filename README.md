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

## Hardware

### Main Components

- 48 × LEDs
- 2 × 74HC595D Shift Registers
- 4 × 2N4402 PNP Transistors
- 4 × 1kΩ Resistors
- 16 × 10kΩ Resistors

---


## Bill of Materials (BOM)

| Qty | Component | Value | Example Link | Unit Cost (USD)* | Total |
|---:|-----------|-------|--------------|-----------------:|------:|
| 48 | LED | 3mm/5mm Red LED | https://www.lcsc.com/search?q=red%20led | $0.02 | $0.96 |
| 1 | Power Indicator LED | Green LED | https://www.lcsc.com/search?q=green%20led | $0.02 | $0.02 |
| 2 | Shift Register IC | 74HC595D | https://www.lcsc.com/search?q=74HC595D | $0.06 | $0.12 |
| 4 | PNP Transistor | 2N4402 | https://www.lcsc.com/search?q=2N4402 | $0.05 | $0.20 |
| 13 | Resistor | 10kΩ 0805 | https://www.lcsc.com/search?q=10k%200805 | $0.005 | $0.07 |
| 4 | Resistor | 1kΩ 0805 | https://www.lcsc.com/search?q=1k%200805 | $0.005 | $0.02 |
| 2 | Mounting Hole | M3 | — | — | — |

| | | | **Estimated Total Component Cost** | | **≈ $1.39 USD** |

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
