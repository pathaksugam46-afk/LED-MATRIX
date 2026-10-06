# 12×4 LED Matrix Bord

This is a small 124 LED Matrix PCB I have made in EasyEDA for learning about PCB design and LED Matrix working.

Rather than purchasing a pre-made module, I decided to make one myself with 2 74HC595 shift registers and 4 2N4402 transistors. The board can be driven by an Arduino using only three signal pins.

---

## What This Board Has

- 12 × 4 LED Matrix (48 LEDs)
- 2 × 74HC595D Shift Registers
- 4 × 2N4402 PNP Transistors
- Works with Arduino
  - 5V
  - GND
  - SER
  - CLK
  - LATCH

---

## Why I Made This

I made this project because I wanted to understand how an LED matrix is controlled.

While making this PCB I learned:

- Drawing schematics in EasyEDA
- Using 74HC595 shift registers
- Multiplexing LEDs
- PCB routing

I also re-created the PCB again as I was not happy with the way I had laid out the components originally. I moved a number of the ICs and some of the resistors to the back side of the board to save space.

This project gave me a much better understanding of how to design PCBs and gave me enough confidence that I could build other hardware based projects.

---

## Components

- 48 × Red LEDs
- 1 × Green Power LED
- 2 × 74HC595D
- 4 × 2N4402 PNP Transistors
- 13 × 10kΩ Resistors
- 4 × 1kΩ Resistors
- Headers for power and signal connections

---

## Bill of Materials (BOM)

| Qty | Component | Package | LCSC Link |
|----:|-----------|---------|-----------|
| 48 | Red LED (0402) | 0402 | https://www.lcsc.com/search?q=0402%20Red%20LED |
| 1 | Green LED (Power) | 0603 | https://www.lcsc.com/search?q=0603%20Green%20LED |
| 2 | 74HC595D Shift Register | SOIC-16 | https://www.lcsc.com/search?q=74HC595D |
| 4 | 2N4402 PNP Transistor | TO-92 | https://www.lcsc.com/search?q=2N4402 |
| 13 | 10kΩ Resistor | 0805 | https://www.lcsc.com/search?q=10k%200805%20Resistor |
| 4 | 1kΩ Resistor | 0805 | https://www.lcsc.com/search?q=1k%200805%20Resistor |
| 1 | 2-Pin Header | 2.54mm TH | https://www.lcsc.com/search?q=2.54mm%202%20Pin%20Header |
| 1 | 3-Pin Header | 2.54mm TH | https://www.lcsc.com/search?q=2.54mm%203%20Pin%20Header |

**Estimated Component Cost:** **≈ $1.78 USD**

---

# Pinout

<img width="597" height="438" alt="Pinout" src="https://github.com/user-attachments/assets/2a03b7f0-6582-43ed-8f5d-eb06bfd5dd70" />


- **5V** -> Power
- **GND** -> Ground
- **SER** -> Serial Data
- **CLK** -> Shift Clock
- **LATCH** -> Storage Clock

---

# Arduino Connection

Arduino = LED Bord
5V = 5V
GND = GND
D11 = SER
D13 = CLK
D10 = LATCH

---

# Example Code

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

# Software Used

- EasyEDA
- Arduino IDE

---

# Tools Required to Assamble pcb

- Soldering iron
- Solder wire
- Flux
- Tweezers
- Flush cutter
- Multimeter (optional)

---

# Images

## Schematic

<img width="886" height="512" alt="Schematic" src="https://github.com/user-attachments/assets/a8f30dd3-6f0a-46d6-b860-554d4b586e43" />

---

## PCB

### Front

<img width="983" height="447" alt="PCB Front" src="https://github.com/user-attachments/assets/2a3ba879-41bf-410d-82c5-8fe156413696" />

### Back

<img width="1127" height="761" alt="PCB Back" src="https://github.com/user-attachments/assets/1590d386-3799-4ccf-99d1-51e8f6214fa2" />

---

## 3D View

### Front

<img width="1230" height="715" alt="3D Front" src="https://github.com/user-attachments/assets/0c3b79a0-f5f3-4ba8-8b01-ac5c6a871782" />

### Back

<img width="1126" height="732" alt="3D Back" src="https://github.com/user-attachments/assets/ed304096-d4c4-465f-9250-e10aa148dd2e" />



# Made By

**Sugam Pathak for  hack club**

