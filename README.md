# 🚦 Traffic Light Controller in Verilog

This repository contains the Verilog code for a simple **Traffic Light Controller** for an intersection between a **Highway** and a **Farm Road**.

---

## 📌 Project Overview
The project models a traffic light system where the **highway traffic has priority**.  
- By default, the **Highway light stays Green** while the **Farm road light stays Red**.  
- The system only changes state when a **car is detected** on the farm road via sensor **C**.  
- The controller is implemented as a **Finite State Machine (FSM)**.

---

## ✨ Features
- **Default State:** Highway = Green, Farm = Red.  
- **Sensor-based Trigger:** Light cycle starts when sensor `C = 1` (car detected).  
- **State Sequence:**
  1. **Highway Green / Farm Red** → Initial & default state.  
  2. **Highway Yellow / Farm Red** → Highway turns yellow for **3 seconds**.  
  3. **Highway Red / Farm Green** → Farm road turns green for **10 seconds**.  
  4. **Highway Red / Farm Yellow** → Farm road turns yellow for **3 seconds**.  
  5. Returns to **Highway Green / Farm Red**.  
- **Active-low Reset:** System can be reset to the initial state.

---

## 📂 File Descriptions
- `traffic_light.v` → Main Verilog module for the **Traffic Light Controller FSM**.  
- `tb_traffic.v` → Testbench file to **simulate and verify** functionality.  

---

## ▶️ How to Use
1. Install a Verilog simulator (e.g., **ModelSim**, **Vivado**, or **Icarus Verilog**).  
2. Compile both files:  
   ```bash
   iverilog -o traffic_sim traffic_light.v tb_traffic.v
   vvp traffic_sim
3. Run the simulation with tb_traffic as the top module.

4. Open the generated waveform (.vcd file) in GTKWave (or a supported viewer) to observe behavior.

## 📊 Simulation Waveform

The waveform demonstrates the state transitions when the farm road sensor C is triggered.

- Default (Highway Green / Farm Red)

- Highway Yellow → Farm Green → Farm Yellow

- Back to Default

## 🖥️ Simulation Objects

Key signals and registers observed in simulation:

- FSM State

- Highway Lights (Green/Yellow/Red)

- Farm Road Lights (Green/Yellow/Red)

- Sensor Input (C)

- Reset Signal

## ⚡ Tech Stack

- **Language**: Verilog HDL

- **Concepts**: FSM, Sequential Logic, Testbench Simulation
