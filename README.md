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



## Images

### Schematic

<img width="886" height="512" alt="Screenshot 2026-09-20 222319" src="https://github.com/user-attachments/assets/a8f30dd3-6f0a-46d6-b860-554d4b586e43" />


### PCB Layout

<img width="1010" height="500" alt="Screenshot 2026-09-20 220755" src="https://github.com/user-attachments/assets/eec618ee-7128-4c2d-9a53-08270e113c86" />


### 3D View

#### Front

<img width="1212" height="487" alt="Screenshot 2026-09-20 204534" src="https://github.com/user-attachments/assets/cdd40db5-5c34-4101-ad3f-992ca5434a0e" />

#### Back


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
