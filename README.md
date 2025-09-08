# Wireless Smoke Detector (433MHz Sub-1GHz RF + NB-IoT)

## 📌 Overview
This project implements a **wireless smoke detector system** using a **433MHz Sub-1GHz RF module** and **NB-IoT connectivity**.  
The system supports **star or mesh networking**, enabling multiple smoke detectors to communicate over RF and forward alerts to an NB-IoT gateway for cloud monitoring.  
A dedicated **Holtek HT68RV035 MCU** controls the RF and peripherals, while the **BC2161 RF IC** handles OOK modulation/demodulation at 433MHz.  

---

## ⚙️ System Architecture
[ Smoke Sensor ] ---> [ MCU (Holtek) ] ---> [ RF Module (BC2161, 433MHz) ] ---> [ Gateway / NB-IoT ]
|
v
[ Buttons, LEDs, Speaker (Audio Feedback) ]



- **MCU (Holtek HT68RV035)**  
  - Manages RF communication and peripheral control  
  - Handles button inputs, LED indicators, and buzzer alerts  
  - Programmed in Embedded C for real-time RF signal processing  

- **RF System (BC2161, 433MHz)**  
  - OOK modulation/demodulation at Sub-1GHz band  
  - Supports star and mesh networking  
  - Includes LC matching network and RF frontend  

- **User Interface**  
  - 4 programmable push buttons  
  - LED for status indication (pairing, alarm, fault)  
  - 8Ω/0.25W buzzer for audible alerts and RF pairing feedback  

- **Networking**  
  - Local RF: 433MHz Sub-1GHz  
  - Cloud uplink: NB-IoT gateway  
  - Supported topology: Star / Mesh  

---

## 🖥 Illustrations

### 1. RF Schematic (433MHz Frontend + MCU)
<img src="./Images/9e8ad36d-ccb5-41ab-a6aa-cda763a9ee73.jpg" width="600">  
- LC matching network for 433MHz band.  
- Holtek HT68RV035 MCU managing I/O, RF, and peripherals.  
- Buzzer and LED connected via GPIO with PWM support.  

---

### 2. RF Board – Top View
<img src="./Images/bm23p105-r41-1.png" width="500">  
- Main PCB with Holtek MCU and BC2161 RF IC.  
- Header for programming/debugging.  
- Integrated 433MHz helical antenna.  

---

### 3. Control Board with Buttons & Buzzer
<img src="./Images/bm23p105-r41-02.png" width="500">  
- 4 programmable push buttons for control and RF pairing.  
- Small 8Ω/0.25W buzzer for sound alerts.  
- Helical antenna soldered directly on PCB.  

---

### 4. RF Module (Assembled PCB, Back View)
<img src="./Images/bm23p105-r41-03.png" width="500">  
- Back side of PCB with RF IC, MCU, and passive components.  
- Optimized ground plane layout for RF stability.  
- Compact design suitable for smoke detector housing integration.  

---

## 🔧 Hardware Specifications
- **MCU**: Holtek HT68RV035  
- **RF IC**: BC2161 (433MHz, OOK)  
- **Peripherals**:  
  - 4 push buttons (control/pairing)  
  - 1 LED status indicator  
  - 1 buzzer 8Ω / 0.25W (PWM)  
- **RF Network**: 433MHz helical antenna + LC matching circuit  
- **Power**: Battery + 3.3V LDO regulator  

---

## 🛡 Safety Features
- Real-time smoke alarm via RF + NB-IoT  
- On-site audible + visual alert  
- RF re-pairing mode via push button  
- MCU watchdog timer for reliability  
- Mesh forwarding support for alert relays if direct link fails  

---

## 🚀 Future Improvements
- Add AES encryption for RF packets  
- Ultra-low power mode for extended battery life  
- FSK modulation support for better noise immunity  
- Cloud logging for alarm history tracking  

---

## 📑 Notes
This document is a **summary of the project**.  
Due to **customer confidentiality policies**, detailed design (full schematic, firmware, PCB layout) **cannot**

