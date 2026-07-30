# 🎵 High-Fidelity Class-D Bluetooth 5.0 Stereo Audio Amplifier (2x50W)

![KiCad 8.0](https://img.shields.io/badge/KiCad-8.0-blue?logo=kicad&logoColor=white)
![Hardware Rev](https://img.shields.io/badge/Hardware%20Rev-v1.0-brightgreen)
![License](https://img.shields.io/badge/License-CERN--OHL--P-orange)
![PCB Layers](https://img.shields.io/badge/PCB%20Layers-2--Layer-purple)
![Audio Output](https://img.shields.io/badge/Output-2x50W%20%40%204%CE%A9-red)

A complete, fully engineered Open-Source Hardware project developed in **KiCad 8.0** for building a high-fidelity **Class-D** stereo audio amplifier featuring an integrated **Bluetooth 5.0 HD** receiver and I2S DAC.

Designed to drive passive speakers (4Ω - 8Ω) with up to **2x50W RMS** output power into a 4Ω load powered by a 24V DC supply.

---

## 📋 Table of Contents
- [Technical Specifications](#-technical-specifications)
- [System Architecture](#-system-architecture)
- [Schematic Circuit Analysis](#-schematic-circuit-analysis)
- [Centralized Library Management](#-centralized-library-management)
- [PCB Design and Layout (KiCad)](#-pcb-design-and-layout-kicad)
- [Bill of Materials (BOM)](#-bill-of-materials-bom)
- [Manufacturing and Assembly Guide](#-manufacturing-and-assembly-guide)
- [Testing and First Power-On Procedure](#-testing-and-first-power-on-procedure)
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
