# 4-Channel Bidirectional Level Shifter

## Overview
This board is a 4-channel bidirectional logic level converter designed to safely interface between different voltage domains (typically 3.3V and 5V). It is based on the [Adafruit 4-channel I2C-safe Bi-directional Logic Level Converter](https://www.adafruit.com/product/757).

The circuit is ideal for bidirectional communication protocols like I2C, but also works for unidirectional signals like SPI or UART.

## Technical Specifications
- **Core Logic:** 4x BSS138 N-channel MOSFETs.
- **Pull-up Resistors:** 10kΩ on all input/output signal lines.
- **Voltage Range:** 
  - **LV (Low Voltage):** Typically 1.8V to 3.3V.
  - **HV (High Voltage):** Typically up to 5V (limited by MOSFET Vgs/Vds).
- **Decoupling:** 100nF ceramic capacitors on both power rails for noise suppression.

## Pinout

### J1 (High Voltage Side)
| Pin | Label | Description |
|:---:|:---:|:---|
| 1 | **5V** | High Voltage Power Rail (e.g., 5V) |
| 2 | **HV1** | Channel 1 High Side |
| 3 | **HV2** | Channel 2 High Side |
| 4 | **HV3** | Channel 3 High Side |
| 5 | **HV4** | Channel 4 High Side |
| 6 | **GND** | Ground |

### J2 (Low Voltage Side)
| Pin | Label | Description |
|:---:|:---:|:---|
| 1 | **3.3V** | Low Voltage Power Rail (e.g., 3.3V) |
| 2 | **LV1** | Channel 1 Low Side |
| 3 | **LV2** | Channel 2 Low Side |
| 4 | **LV3** | Channel 3 Low Side |
| 5 | **LV4** | Channel 4 Low Side |
| 6 | **GND** | Ground |

## PCB Features
- **Compact Form Factor:** Approximately 16.5mm x 18.2mm.
- **Signal Integrity:** Solid ground planes on both layers with stitching vias.
- **Usability:** Clear silkscreen labeling for all channels and power pins.

## Usage Guide
1. **Power:** Connect your low-voltage supply to **3.3V** and your high-voltage supply to **5V**.
2. **Ground:** Connect **GND** to your common system ground.
3. **Logic:** Connect your 3.3V logic signals to the **LVn** pins; the corresponding **HVn** pins will provide the 5V shifted output (and vice-versa for bidirectional signals).

---
*Developed as a KiCad 10 project.*
