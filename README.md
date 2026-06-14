# Transistor-Level Standard Cell Logic Design & Verification

## 📌 Project Description
This project focuses on designing and verifying basic digital logic gates (NOT and AND) from the transistor level using **Resistor-Transistor Logic (RTL)** topology. The entire workflow covers schematic capture, hardware-constrained single-layer PCB layout routing, and rigorous SPICE simulation to analyze the transient voltage characteristics.

---

## 🛠️ Tech Stack & EDA Tools
* **Schematic Capture & PCB Layout:** KiCAD E.D.A. 9.0.5
* **Simulation Engine:** LTspice (Transient Analysis)
* **Logic Family:** Resistor-Transistor Logic (RTL)
* **Components:** BC547B NPN Transistors, Carbon Film Resistors, Standard 3mm LEDs

---

## 📐 Circuit & Physical Design Parameters

### 1. Circuit Topology
* **NOT Gate (Inverter):** Implemented using a single NPN transistor (`Q2`) in a common-emitter configuration. Uses a $1\text{k}\ \Omega$ base resistor (`R3`) for current limiting and a $330\ \Omega$ pull-up resistor (`R4`) at the collector output node.
* **AND Gate:** Designed using a cascoded (series) connection of two NPN transistors (`Q1` and `Q3`), ensuring the pull-down path activates only when both inputs are tied High ($5\text{V}$).

### 2. PCB Layout Constraints
* **Layer Strategy:** Constrained to a **Single-Layer Board** for economical prototyping.
* **Routing Layer:** All interconnections are routed entirely on the **Bottom Copper Layer (`B.Cu`)** using optimized track widths for stable current density.
* **DRC Compliance:** Cleared Design Rules Check (DRC) with 0 Errors and 0 Unconnected Items. Mechanical board boundaries are tightly locked on the `Edge.Cuts` layer.

---

## 📊 Simulation & Logic Verification
To validate the physical design pre-fabrication, a SPICE netlist was characterized using **Transient Analysis (`.tran 10m`)** in LTspice.

* **Stimulus:**When the input voltage `V(in_not)` transitions to 5V (Logic 1), the transistor drives into saturation, pulling the output node `V(out_not)` down to near 0V (Logic 0). dynamic square pulse wave input.
* **Result:** The Voltage Transfer Characteristics successfully confirm strict logic inversion. When the input voltage When the input voltage `V(in_not)` transitions to 5V (Logic 1), the transistor drives into saturation, pulling the output node `V(out_not)` down to near 0V (Logic 0). (Logic 1), the transistor drives into saturation, pulling the output node $V(\text{out_not})When the input voltage `V(in_not)` transitions to 5V (Logic 1), the transistor drives into saturation, pulling the output node `V(out_not)` down to near 0V (Logic 0). (Logic 0).

---

## 📸 Project Gallery

### 1. Schematic Design
[Schematic.pdf](https://github.com/user-attachments/files/28925923/Schematic.pdf)


### 2. PCB 3D Hardware Render
<img width="1918" height="892" alt="3D Scratch backside view " src="https://github.com/user-attachments/assets/5b44850c-4a00-4c80-b0b9-aa121fc0389e" /><img width="1918" height="892" alt="3D Scratch view " src="https://github.com/user-attachments/assets/56f14dda-e17b-4512-b53e-4f0ec0fbd5a0" />


### 3. LTspice Transient Waveform Graph
<img width="1920" height="1080" alt="Waveform" src="https://github.com/user-attachments/assets/d0c1b668-b34b-4e31-b566-f6fc6db3352e" />


---

## 📁 Repository Structure
* `/KiCAD_Files/` : Contains the `.kicad_sch` (schematic) and `.kicad_pcb` (board layout) files.
* `/LTspice_Files/` : Contains the SPICE simulation netlist `.cir`/`.net` file.
* `/images/` : Rendered assets and simulation waveforms used in this documentation.
