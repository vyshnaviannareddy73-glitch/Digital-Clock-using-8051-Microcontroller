<div align="center">

# ⏱️ Digital Clock Using 8051 Microcontroller

[![Microcontroller](https://img.shields.io/badge/MCU-AT89C51%20%2F%20AT89S52-blue.svg)](#)
[![Language](https://img.shields.io/badge/Language-Embedded%20C-orange.svg)](#)
[![Toolchain](https://img.shields.io/badge/Tool-Keil%20%C2%B5Vision-green.svg)](#)
[![Status](https://img.shields.io/badge/Status-Hardware%20Tested-brightgreen.svg)](#)

A hardware-based digital clock project designed and implemented using an 8051 microcontroller, featuring multiplexed 7-segment displays, precise timer interrupts, and push-button time configuration.

<br />

![Digital Clock Hardware](digital%20clock%20ss/digital%20clock.jpeg)

</div>

---

## 📸 Hardware Circuit Gallery

| Breadboard Overview | Display Setup | Circuit & Controls |
| :---: | :---: | :---: |
| ![Overview](digital%20clock%20ss/digital%20clock.jpeg) | ![Display](digital%20clock%20ss/digital%20clock1.jpeg) | ![Controls](digital%20clock%20ss/dital%20clock2.jpeg) |

---

## 💡 Key Features

* **Real-Time Clock (RTC) Logic:** Tracks seconds, minutes, and hours using internal 8051 Timer interrupts for high accuracy.
* **Multiplexed 7-Segment Displays:** Efficiently drives multiple digit pairs to display hours, minutes, and seconds.
* **Manual Time Setting:** Equipped with hardware push buttons for easy hour and minute incrementing with debouncing logic.
* **Standalone Operation:** Powered via a portable battery pack configured on a breadboard layout.

---

## 🛠️ Hardware Stack & Specifications

| Component | Function / Role |
| :--- | :--- |
| **8051 Microcontroller (AT89C51/S52)** | Central processing unit executing timekeeping and display refreshing |
| **7-Segment Displays** | Visual output interface showing hours, minutes, and seconds |
| **Push Buttons (x2)** | Time-setting controls for Hours (`BTN_HOUR`) and Minutes (`BTN_MIN`) |
| **Resistors & Capacitors** | Current limiting and reset/oscillator circuit configuration |
| **Battery Power Supply** | Dual-cell DC power source supplying stable voltage to the breadboard |

---

## ⚙️ Logic Flow

```text
  +------------------+         +--------------------------+         +-------------------+
  |   Push Buttons   | ------> |      8051 MCU Input      | ------> |    Timer 0 ISR    |
  |  (Hour / Minute) |         |     (Port Polling)       |         |  (1ms Tick Count) |
  +------------------+         +--------------------------+         +-------------------+
                                                                              |
                                                                              v
  +------------------+         +--------------------------+         +-------------------+
  | 7-Segment Output | <------ |     Time Calculation     | <------ | Second / Minute / |
  | (Multiplexed LED)|         |   (Sec -> Min -> Hour)   |         |    Hour Rollover  |
  +------------------+         +--------------------------+         +-------------------+
