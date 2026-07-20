# TLV61070 Ultra-Low Voltage Solar Harvester & Booster

A low-cost, ultra-low voltage energy harvesting and management circuit built around the **TI TLV61070** synchronous boost regulator. By incorporating a precision external operational amplifier loop (`MCP6001T`) and an adjustable voltage reference (`TL432`), this design implements a reliable Constant Voltage (CV) input control scheme ("Fixed MPPT") to maximize solar extraction without collapsing low-power panels.

---
![Rendering](https://github.com/Grunwalskii/TLV61070-Ultra-Low-Volage-Solar-Charger---CV-Input---Fixed-MPPT-/blob/main/Images/3DRendering.png)
## Technical Specifications & Features

* **Wide Input Range:** Handles `0.5V to 5.5V` (Absolute max: `7.0V`).
* **Ultra-Low Start-up:** Triggers at `1.3V` and operates down to `0.5V` once running.
* **Flexible Output Range:** Programmable between `2.2V and 5.5V` (with built-in `5.7V` Output Overvoltage Protection).
* **True Disconnect Shutdown:** Completely disconnects the chip from input power during shutdown, dropping current draw to just `0.1 µA`.
* **Integrated Safety:** Features integrated short-circuit protection and thermal shutdown.

### Quiescent Current Breakdown
* **$V_{in}$ Quiescent Current:** ~`11 µA` (Voltage Divider) + `1 µA` (TLV)
* **$V_{out}$ Quiescent Current:** ~`176 µA` total (`100 µA` Op-amp, `47 µA` Reference, `9 µA` Voltage Divider, `20 µA` TLV).

---

## Real-World Measured Efficiency

The synchronous rectification design delivers excellent power conversion efficiency across typical harvesting and step-up scenarios:

| Input ($V_{in}$) | Output ($V_{out}$) | Output Current ($I_{out}$) | Input Power | Output Power | Efficiency |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **3.6 V** | 5.0 V | 5.0 mA | 26.71 mW | 25.00 mW | **94%** |
| **3.6 V** | 5.0 V | 50.0 mA | 284.00 mW | 250.00 mW | **88%** |
| **1.8 V** | 5.0 V | 50.0 mA | 264.00 mW | 250.00 mW | **94%** |
| **1.8 V** | 4.0 V | 40.0 mA | 172.00 mW | 160.00 mW | **93%** |

## Thermal Test
Input: 1.8V/2A - Output: 4V - TLV Temp: 82c at 24C Room

## Circuit Tuning & Potentiometers

The design features dual adjustment windows via resistor/potentiometer networks to easily dial in your specific solar panel characteristics and target storage voltage:

### 1. Input Side (Fixed MPPT Threshold)
Uses a `47k` resistor base to set the `0.5V` reference point tracking.
* **Minimum (10k):** `0.6V` MPPT lock voltage.
* **Middle (260k):** `3.3V` MPPT lock voltage.
* **Maximum (510k):** `6.0V` MPPT lock voltage.
* *Current draw across the input divider is approximately `11 µA`.*

### 2. Output Side (Target Voltage Configuration)
Uses a `47k` resistor base to match the reference feedback loop.
* **Minimum (100k):** `1.6V` target output.
* **Middle (350k):** `4.3V` target output.
* **Maximum (600k):** `6.9V` target output.
* *Current draw across the output divider is approximately `9 µA`.*

## Support

If you enjoy this project and want to support its development, you can buy me a coffee:

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/W1L623I6WG)

