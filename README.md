# Self-Powered-Underwater-Data-Logger
This project is a self-powered underwater data logger built around a PIC16F microcontroller that harvests and stores piezoelectric energy to sustain long-term data logging without an external power source. I wrote the embedded C firmware to record real-time temperature readings during underwater deployment, and implemented a threshold-triggered sleep/wake cycle to conserve harvested energy and maximize the system's operational lifespan. To transmit the logged data, I drove a piezoelectric transducer with microcontroller-generated pulses over GPIO, enabling short-range acoustic communication.

## PCB Preview

<p align="center">
<img width="475" height="479" alt="image" src="https://github.com/user-attachments/assets/05c52dc5-d40d-4570-9002-53944f26b4a1" />
</p>
<p align="center">
<strong>A self-powered underwater piezoelectric based data logger with minimized PCB architecture ((20.3 mm × 20.4 mm)</strong>
</p>


## 3D Board Render

<p align="center">
  <img width="475" alt="image" src="https://github.com/user-attachments/assets/d4fe16e6-0846-4fea-b715-440f881fc52f" />
</p>

## Schematic
<p align="center">
  <img width="1631" height="733" alt="image" src="https://github.com/user-attachments/assets/0b574a49-3105-4faf-8905-0c7a2ce4b28d" />
</p>

## Firmware Architecture

