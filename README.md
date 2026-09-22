# Self-Powered-Underwater-Data-Logger
This project is a self-powered underwater data logger built around a PIC16F microcontroller that harvests and stores piezoelectric energy to sustain long-term data logging without an external power source. I wrote the embedded C firmware to record real-time temperature readings during underwater deployment, and implemented a threshold-triggered sleep/wake cycle to conserve harvested energy and maximize the system's operational lifespan. To transmit the logged data, I drove a piezoelectric transducer with microcontroller-generated pulses over GPIO, enabling short-range acoustic communication.

## Features
- **Sustainable Operation:** Harvests and stores energy from a piezoelectric element vibrating in water
- **Temperature Logging:** Records temperature readings continuously during deployment
- **Power Saving:** MCU programmed to wake/sleep for energy conservation
- **Data Transmission:** Logged data is transmitted periodically acoustically through a piezo transducer

## PCB Preview

<p align="center">
<img width="475" height="479" alt="image" src="https://github.com/user-attachments/assets/05c52dc5-d40d-4570-9002-53944f26b4a1" />
  <img width="465" alt="image" src="https://github.com/user-attachments/assets/11682b51-2d4f-44a4-a9de-dd3fa9ae748c" />
</p>
<p align="center">
<strong>A self-powered underwater piezoelectric based data logger with minimized PCB architecture ((20.3 mm × 20.4 mm)</strong>
</p>


## 3D Board Render

<p align="center">
  <img width="475" alt="image" src="https://github.com/user-attachments/assets/d4fe16e6-0846-4fea-b715-440f881fc52f" />
  <img width="475" alt="image" src="https://github.com/user-attachments/assets/e6593780-d1bf-401c-b4e1-b4f43efd624c" />
</p>  
<p align="center">
<strong>PCB render front and back</strong>
</p>

## Schematic
<p align="center">
  <img width="1631" height="733" alt="image" src="https://github.com/user-attachments/assets/0b574a49-3105-4faf-8905-0c7a2ce4b28d" />
</p>
<p align="center">
<strong>Schematic; Energy harvesting and MCU</strong>
</p>

## Firmware Architecture
- **Sleep mode:** The PIC16F stays in low-power sleep  while the LTC3588 rectifies and stores piezoelectric energy in a rechargable battery
- **Threshold wake:** Once capacitor voltage crosses set threshold, an interrupt wakes the MCU
- **Sense and store:** The MCU reads the temperature sensor, maps, and stores the reading
- **Acoustic transmission:** The MCU drives an attached piezoelectric transducer with GPIO-generated pulses to transmit the data acoustically
- **Repeat:** The system returns to sleep and repeats the cycle as energy is harvested

```mermaid
%%{init: {'theme': 'base', 'themeVariables': {'background': '#ffffff', 'primaryColor': '#ffffff', 'primaryBorderColor': '#333333', 'lineColor': '#333333'}}}%%
flowchart LR
    A[Sleep Mode<br/>Low Power] --> B{Stored Energy<br/>Above Threshold?}
    B -- No --> A
    B -- Yes --> C[Wake Up MCU]
    C --> D[Read Temperature Sensor]
    D --> E[Store Reading]
    E --> F[Drive Piezo Transducer<br/>Acoustic Transmission]
    F --> A
```


  <p align="center">
<strong>Firmware Flowchart</strong>
</p>
