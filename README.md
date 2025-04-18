# AnalogHeart-by-Meditrones
This is the detailed project description of the ECG monitoring device built using analog electronics by the team Meditrones
## Table of Contents
1. [Introduction](#introduction)
2. [Functionality](#functionality)
3. [Printed Circuit Board](#printed-circuit-board)
4. [Enclosure Design](#enclosure-design)
5. [Contributors](#contributors)

---

## Introduction
An electrocardiogram (ECG) is a widely used diagnostic tool for evaluating heart activity by detecting electrical signals through electrodes attached to the skin. These signals have amplitudes ranging from 0.001 mV to 100 mV and frequencies between 0.01 Hz and 180 Hz. However, amplifying and filtering these signals presents challenges due to their susceptibility to noise, power line interference, and other distortions.

Our project aims to address these challenges by designing an analog circuit that amplifies and filters ECG signals using basic electronic components such as resistors, capacitors, and operational amplifiers (OpAmps). The design incorporates multiple stages of signal conditioning, which are detailed below.

We simulated the design using LTSpice before implementation and used Altium Designer for PCB layout and SolidWorks for enclosure design.
<img src="https://github.com/user-attachments/assets/ed1dd3c9-1c8a-4b50-ace4-8166f585bfdb" alt="Simulated Circuit" width="800">


---

## Functionality
The AnalogHeart ECG Monitor includes the following features:
- **Real-time heart rate monitoring.**
- **User-friendly interface for operation.**
- **Accurate heart rate display with filtering.**
- **Adjustable settings for different scenarios.**
- **Data logging and export options.**
- **Detailed documentation for developers and users.**

### Signal Conditioning Stages
1. **Instrumentation Amplifier**
   - Amplifies small differential signals from the electrodes while rejecting common-mode noise.
   - Implemented using TL072CP OpAmps for high Common Mode Rejection Ratio (CMRR).
   - Adjustable gain using an external potentiometer.

2. **Right Leg Drive**
   - Reduces common-mode noise by injecting an inverted signal back into the body.
   - Built using a TL072CP OpAmp configured as an inverting buffer.

3. **Filter Stages**
   - **High Pass Filter**: Removes low-frequency noise and DC offset. First-order design with a cutoff at 0.15 Hz.
   - **Low Pass Filter**: Eliminates high-frequency noise using a fifth-order Bessel filter with a cutoff at 164 Hz.
   - **Notch Filter**: Suppresses power-line interference (50/60 Hz) with a Twin-T configuration and adjustable parameters.

4. **Power Circuit**
   - Dual supply (+12V and -12V) generated by TPS61040 boost converters for OpAmps.
   - 3.3V regulated output for ESP32 MCU using AMS117-3.3 regulator.
   - Rechargeable Li-Po battery support with a charging module for portability.

5. **Analog-to-Digital Conversion**
   - Captures conditioned ECG signals via ESP32's ADC input.
   - Includes level-shifting and scaling circuits to ensure signals fit within the 0-3.3V input range of the ESP32.

---

## Printed Circuit Board
The PCB was designed using Altium Designer and features:
- **Two-layer layout** for signal integrity and minimal interference.
- **Separate routing** for signal and power traces to reduce noise.
- **Compact design** with 0805 SMD components and IC bases for easy replacement.
- **Hand-soldered components** for prototyping and testing.
<img src="https://github.com/user-attachments/assets/df98d67f-a293-4048-aef6-e016502b796e" alt="PCB " width="500">

### PCB Highlights:
- **Power traces**: 25 mils for reliability.
- **Signal traces**: 15 mils to maintain integrity.
- **Isolated signal processing**, power, and ADC circuits.

---

## Enclosure Design
The enclosure was modeled using SolidWorks and designed for:
- **Protection and ventilation** to prevent overheating.
- **Removable top lid** for easy assembly and maintenance.
- **Battery holder and charging port** for portability.
- **Display mount and slots** for connectors, switches, and ventilation.
- **3D-printed construction** for rapid prototyping.
<img src="https://github.com/user-attachments/assets/a20569d8-06bf-4df4-be3d-d1c720de780e" width="500">


---

## Contributors
- [@MohamedAazir](https://github.com/MohamedAazir)  - Circuit design, enclosure design, and optimization.
- [@msboralugoda](https://github.com/msboralugoda)  - PCB design, documentation, and testing.
- [@Banu-Liyanage](https://github.com/Banu-Liyanage)  -PCB design,Circuit design, PCB assembly.
- [@Madusanka20](https://github.com/Madusanka20)  - Enclosure design and circuit testing and Debuging.


---

For further details, visit the GitHub repository: [AnalogHeart by Meditrones](https://github.com/Banu-Liyanage/AnalogHeart-by-Meditrones)




