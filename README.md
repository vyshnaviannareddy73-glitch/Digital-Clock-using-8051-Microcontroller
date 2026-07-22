
<div align="center">

# ⏰ Digital Clock using 8051 Microcontroller

[![Microcontroller](https://img.shields.io/badge/MCU-8051%20Family-blue.svg)](#)
[![Display](https://img.shields.io/badge/Display-6--Digit%207--Segment-red.svg)](#)
[![Platform](https://img.shields.io/badge/Platform-Breadboard%20Prototyping-orange.svg)](#)
[![Status](https://img.shields.io/badge/Status-Hardware%20Verified-brightgreen.svg)](#)

A complete hardware realization of a 24-Hour Digital Clock built with an **8051 Microcontroller**, display drivers, and 7-segment LED modules on interconnected breadboards.

<br />

<img src="./digital%20clock%20ss/digital%20clock.jpeg" alt="Digital Clock Powered On" width="650" />

</div>

---

## 📸 Project Hardware Gallery

| Unpowered Circuit Assembly | Active Display Output | Close-up Hardware View |
| :---: | :---: | :---: |
| <img src="./digital%20clock%20ss/digital%20clock1.jpeg" width="240" alt="Unpowered Breadboard Setup"/> | <img src="./digital%20clock%20ss/digital%20clock.jpeg" width="240" alt="Powered Display Output"/> | <img src="./digital%20clock%20ss/dital%20clock2.jpeg" width="240" alt="Close-up Powered View"/> |

---

## 💡 Key Features

* **Full HH:MM:SS Timekeeping:** Tracks real-time Hours, Minutes, and Seconds across three dual 7-segment displays.
* **Precise 8051 Timer Interrupts:** Uses internal 8051 hardware timers referenced by a crystal oscillator for accurate 1-second pulse increments.
* **Manual Calibration Controls:** Push buttons allow quick manual adjustment of Hours and Minutes.
* **Portable Power:** Operates using a dual 18650 Li-ion battery setup connected directly to the power rails.
* **Solderless Prototyping:** Built on a multi-breadboard matrix for testing and modular hardware debugging.

---

## 🛠️ Hardware Stack & Specifications

| Component | Function / Role |
| :--- | :--- |
| **8051 Microcontroller** | Central processing unit handling time counters and interrupt routines |
| **7-Segment LED Displays** | Output readout for HH : MM : SS digits |
| **Display Drivers / Decoder ICs** | BCD decoding and segment output driving |
| **Crystal Oscillator** | Precise clock source (e.g., 11.0592 MHz / 12 MHz) |
| **Push Buttons** | Manual input for setting hours and minutes |
| **18650 Li-ion Battery Setup** | Portable DC power source |

---

## ⚙️ Logic Flow

```text
  +------------------+         +--------------------------+         +-------------------+
  |  Push Buttons    | ------> |    8051 Microcontroller   | ------> | Driver ICs / BCD  |
  | (Hour/Min Set)   |         |  (Timer 0/1 Interrupt)   |         | Decoders          |
  +------------------+         +--------------------------+         +-------------------+
                                            ^                                 v
                                            |                       +-------------------+
                                   +-----------------+              | 6-Digit Display   |
                                   | Crystal Osc.    |              |   (HH : MM : SS)  |
                                   +-----------------+              +-------------------+
