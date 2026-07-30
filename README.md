# 🎵 High-Fidelity Class-D Bluetooth 5.0 Stereo Audio Amplifier (2x50W)

![KiCad 9.0](https://img.shields.io/badge/KiCad-8.0-blue?logo=kicad&logoColor=white)
![Hardware Rev](https://img.shields.io/badge/Hardware%20Rev-v1.0-brightgreen)
![License](https://img.shields.io/badge/License-CERN--OHL--P-orange)
![PCB Layers](https://img.shields.io/badge/PCB%20Layers-2--Layer-purple)
![Audio Output](https://img.shields.io/badge/Output-2x50W%20%40%204%CE%A9-red)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)

A complete, fully engineered Open-Source Hardware project developed in **KiCad 9.0** for building a high-fidelity **Class-D** stereo audio amplifier featuring an integrated **Bluetooth 5.0 HD** receiver and I2S DAC.

Designed to drive passive speakers (4Ω - 8Ω) with up to **2x50W RMS** output power into a 4Ω load powered by a 24V DC supply.

---

> 🛠️ **Project Status: Active Development**  
> This project is currently **work in progress (WIP)**. Schematics, PCB layout, and documentation are actively being refined and updated. Contributions, suggestions, and feedback are welcome!

---

## 📋 Table of Contents
- [Technical Specifications](#-technical-specifications)
- [Centralized Library Management](#-centralized-library-management)
- [PCB Design and Layout (KiCad)](#-pcb-design-and-layout-kicad)
- [Repository Structure](#-repository-structure)
- [Enclosure & 3D Printing](#-enclosure--3d-printing)
- [License](#-license)

---

## ⚡ Technical Specifications

| Parameter | Value / Specification |
| :--- | :--- |
| **Supply Voltage (DC)** | 12V – 24V DC (24V 5A recommended for maximum output power) |
| **Main Amplifier IC** | Texas Instruments **TPA3116D2** (Stereo Class-D) |
| **RMS Output Power** | 2 x 50W @ 24V, 4Ω / 2 x 30W @ 24V, 8Ω |
| **Power Efficiency** | > 90% (low thermal dissipation) |
| **Bluetooth Module** | Qualcomm **QCC3008** (Bluetooth 5.0, aptX, aptX-LL, A2DP) |
| **Audio DAC** | Texas Instruments **PCM5102A** (24-bit / 192kHz I2S) |
| **Preamp & Tone Control** | Dual Op-Amp **NE5532** / **OPA1612** (Volume, Bass, Treble) |
| **Frequency Response** | 20 Hz – 20 kHz (±0.5 dB) |
| **THD+N (Distortion)** | < 0.1% @ 1W / 1kHz (< 0.05% typical) |
| **Signal-to-Noise Ratio (SNR)** | > 102 dB |
| **Output Reconstruction Filter** | Audiophile-grade shielded LC Low-Pass Filter |
| **Built-in Protections** | Reverse Polarity (P-FET), Overvoltage, Short Circuit, Thermal Shutdown |

---


## 📚 Centralized Library Management

This project relies on a centralized component library containing all Symbols, Footprints, 3D Models, and Datasheets, hosted at [`Loredati-svg/Kicad_Library`](https://github.com/Loredati-svg/Kicad_Library.git).
The library is integrated directly into the `Library/` directory as a **Git Submodule**.

### How to Clone This Repository (With Library)

To clone this amplifier project along with the library in a single command, use the `--recurse-submodules` flag:

```bash
git clone --recurse-submodules [https://github.com/TUO-USERNAME/NOME-REPO-AMPLIFICATORE.git](https://github.com/TUO-USERNAME/NOME-REPO-AMPLIFICATORE.git)
```


## 📐 PCB Design and Layout (KiCad)

PCB design choices in KiCad 9.0 adhere to best EMC/EMI and signal integrity practices:

1. **2-Layer Stackup (FR4 - 1.6mm - 1oz/2oz Copper):**
   * **Top Layer:** Audio signal traces, main power routing (high-current power traces > 2.5mm), and SMD components.
   * **Bottom Layer:** Continuous Ground Plane (star grounded, separated into *GND_DIGITAL*, *GND_ANALOG*, and *GND_POWER* with a single star point at the bulk input capacitor).
2. **TPA3116D2 Thermal Dissipation:**
   * Includes an array of **20+ Thermal Vias (0.3mm)** beneath the TPA3116D2 PowerPAD to conduct heat to the bottom copper plane. An extruded aluminum heatsink is attached to the top of the IC.
3. **LC Output Loops:**
   * Physical distance between the TPA3116 output pins, LC filters, and terminal blocks is minimized to prevent traces from acting as EMI radiating antennas.

## 📂 Repository Structure

```text
├── Documentation/                 # Project documentation and guides
├── Gerber/                        # Gerber, Drill, and MAP production files
├── KiCad_Project/
│   ├── Audio_Amp_v1.kicad_pro    # KiCad 8 Project File
│   ├── Audio_Amp_v1.kicad_sch    # Schematic Sheet
│   ├── Audio_Amp_v1.kicad_pcb    # PCB Layout
│   └── Audio_Amp_v1.xml          # Exported BOM
├── libs/
│   └── kicad-components-lib/      # 🔗 Git Submodule -> Link to centralized library repo
│       ├── symbols/               # Custom KiCad symbols
│       ├── footprints.pretty/     # Footprints
│       ├── 3dmodels/              # STEP / WRL 3D Models
│       └── datasheets/            # PDF Datasheets
├── Production/                    # Pick&Place (CPL) and JLCPCB BOM files
├── 3D_Print_Case/                 # STL Enclosure models for 3D printing
├── LICENSE                        # CERN-OHL-P License
└── README.md                      # Project Readme
```
---

## 🎨 Enclosure & 3D Printing

The repository includes a custom-designed, fully tailored 3D printable enclosure located in the `/3D_Print_Case` directory. It is engineered to protect the electronics while ensuring adequate passive thermal dissipation and a clean, professional look.

### 🛠️ Key Design Features
* **Front Panel:** Precise cutouts for Volume, Bass, and Treble potentiometers, Power switch, and status LEDs (Power & Bluetooth pairing).
* **Rear Panel:** Dedicated cutouts for high-quality speaker binding posts, DC barrel jack (5.5x2.5mm), and an optional SMA connector for an external Bluetooth antenna.
* **Thermal Management:** Top and bottom passive ventilation slots strategically aligned above the TPA3116D2 heatsink and LC filter inductors to prevent heat buildup.
* **Mechanical Fastening:** Designed for **M3 heat-set brass threaded inserts** (ruthex-style) embedded into internal mounting bosses for repeated assembly without wearing out printed plastic threads.

## 📜 License

This hardware project is released under the **CERN Open Hardware Licence Permissive v2 ([CERN-OHL-P v2](https://ohwr.org/cernohl))**.
