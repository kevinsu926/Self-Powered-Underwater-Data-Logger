# Self-Powered-Underwater-Data-Logger
<p align="center">
<img width="475" height="479" alt="image" src="https://github.com/user-attachments/assets/05c52dc5-d40d-4570-9002-53944f26b4a1" />
</p>

<p align="center">
<strong>A self-powered underwater piezoelectric based data logger</strong>
</p>

---
## Overview

This project is a self-powered underwater data logger built around a PIC16F microcontroller that harvests and stores piezoelectric energy to sustain long-term data logging without an external power source. I wrote the embedded C firmware to record real-time temperature readings during underwater deployment, and implemented a threshold-triggered sleep/wake cycle to conserve harvested energy and maximize the system's operational lifespan. To transmit the logged data, I drove a piezoelectric transducer with microcontroller-generated pulses over GPIO, enabling short-range acoustic communication.

## PCB Preview

### 3D Board Render

<p align="center">
  <img width="700" alt="image" src="https://github.com/user-attachments/assets/c4431743-d05b-402f-9910-60ced047558e" />
</p>
---
