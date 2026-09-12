# HAR-SMI-500 — High-Altitude Resilient 500W Solar Micro-Inverter

A high-altitude, extreme-environment **500W solar micro-inverter architecture** designed for operation under subzero temperatures and reduced atmospheric pressure. The design combines a **GaN-based LLC DC-DC conversion stage**, isolated planar transformer, **SiC full-bridge grid inverter**, LCL filtering, deterministic C2000 control, and ESP32-S3-based edge telemetry.

The system is designed around a **28–50V DC PV input**, **400V DC-link**, and **230V AC / 50Hz grid output**, with a target peak efficiency of **97.2%**.



<img width="1722" height="884" alt="HAR_SMI_500" src="https://github.com/user-attachments/assets/44850da4-2113-4de3-8a5a-e5e24ab0305c" />





## Key Features

* **500W continuous power conversion**
* 28–50V DC photovoltaic input
* 400V regulated DC-link
* 230V AC, 50Hz single-phase output
* GaN full-bridge LLC converter
* 2:20 planar isolation transformer
* SiC full-bridge grid inverter
* LCL output filter
* TI **TMS320F28379D C2000** real-time power controller
* **ESP32-S3** edge-processing and telemetry controller
* Galvanically isolated SPI communication using **ISO7741-Q1**
* Incremental Conductance MPPT
* SOGI-PLL grid synchronization
* 20kHz proportional-resonant current control
* Hardware over-voltage and over-current trip protection
* PT100, BME280, SHT45 and solar-irradiance sensing
* SX1262-based LoRaWAN telemetry
* Autonomous cold-start pre-heating using a 25W PTC heater
* High-altitude PCB clearance and creepage design
* Designed for −40°C to +55°C operation

The complete architecture is divided into hierarchical functional blocks covering PV input protection, LLC conversion, isolation and rectification, DC-link storage, SiC inversion, LCL filtering, gate drivers, sensing, dual-MCU control, RF telemetry, auxiliary power, and mechanical interfaces.

## Control & Protection

The C2000 controller provides the deterministic power-conversion control loop, including MPPT, LLC frequency modulation, grid synchronization, PR current control, and hardware Trip-Zone protection. The ESP32-S3 is isolated from the power-control domain and handles environmental diagnostics, cold-start supervision, data logging, and wireless telemetry.

## High-Altitude Design

The architecture incorporates altitude-aware electrical insulation design with an enforced **≥4.5 mm clearance** and **≥6.0 mm creepage**, along with milled isolation slots, conformal coating, selective potting, and minimized high-dv/dt power loops.

## Cold-Start System

At temperatures below −20°C, the system enters an autonomous pre-heating state before enabling normal inverter operation. A 25W PTC heater combined with controlled GaN switching provides approximately 38W of heating power, targeting a transition from −40°C to −10°C in approximately 11.58 minutes.

