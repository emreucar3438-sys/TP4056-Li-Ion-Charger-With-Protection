# TP4056-Li-Ion-Charger-With-Protection
A professional-grade USB-C Li-Ion battery charger PCB featuring TP4056, dedicated battery protection (DW01A), and optimized thermal management.
This project features a high-performance PCB design for charging and protecting single-cell Lithium-Ion/Polymer batteries. It is designed with industrial standards in mind, focusing on thermal stability and power integrity.


## Overview
This board integrates the **TP4056** charging IC with a dedicated protection circuit (**DW01A** + **FS8205A**). Unlike standard modules, this design is optimized for better heat dissipation and reliable soldering through advanced PCB layout techniques.

## Key Features
- **Input:** USB Type-C (5V)
- **Charging Current:** 1A (Adjustable via R3)
- **Protection:** Over-charge, over-discharge, and over-current/short-circuit protection.
- **Indicators:** Dual onboard LEDs for charging status (Charging/Standby).

## Hardware & Bill of Materials (BOM)
| Ref | Component | Description |
U1 =	TP4056	Lithium-Ion Battery Charger IC (SOP-8)
U2 =	DW01A	Battery Protection IC (SOT-23-6)
Q1 =	FS8205A	Dual N-Channel Power MOSFET (SOT-23-6)
U5 =	TYPE-C-31-M-12A	USB Type-C 16-Pin Power Input Connector
U3 =	DB127L-5.08-2P	2-Pin Screw Terminal Block (Battery Output)
D1 =	ESD9B5V	ESD Protection Diode for USB Input
LED1 =	Green LED (0603)	Standby / Fully Charged Indicator
LED2 =	Red LED (0603)	Charging Process Indicator
C1 =	10uF (SMD ECAP)	Electrolytic Output Filtering Capacitor
C4, C5 =	10uF (0805)	Ceramic Input/Output Decoupling Capacitors
R1 =	1.2k Ohm (0805)	Charge Current Setting Resistor (Sets 1A)
R2 =	1k Ohm (0805)	Protection IC Voltage Detection Resistor
R3, R5 =	1k Ohm (0805)	Current Limiting Resistors for Status LEDs
R4 =	100 Ohm (0805)	Protection Circuit Current Sensing Resistor
R6, R7 =	5.1k Ohm (0805)	USB-C CC1/CC2 Configuration Resistors

## Technical Design Details

### 1. Thermal Management
The TP4056 can generate significant heat during 1A charging. To address this, **Thermal Vias** are implemented directly under the IC's exposed pad (GND). This transfers heat from the top layer to the bottom copper plane, acting as a passive heatsink.

### 2. Neckdown Technique
High-current traces are intentionally narrowed (**Neckdown**) just before connecting to small component pads (e.g., FS8205A). This prevents solder bridging and ensures thermal balance during the soldering process without sacrificing current capacity.



### 3. Power Integrity
- **Dual-Layer Ground Plane:** Both top and bottom layers feature large **GND Copper Pours** to minimize EMI and reduce trace resistance.
- **Clearance Optimization:** Trace-to-pour clearance is carefully tuned to prevent short circuits, especially around the USB-C shield pads.

## Tools Used
- **EDA:** EasyEDA
- **Mechanical:** Fusion 360 (for 3D verification)

---
**Designed by: Emre Uçar**
