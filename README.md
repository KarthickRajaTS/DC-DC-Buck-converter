# Validating and Debugging a DC-DC Buck Converter Design Based on the LM2596 Datasheet

# LM2596 DC-DC Buck Converter

This project simulates the **LM2596** step-down (buck) converter using **LTSpice** to convert high input DC voltage (e.g., 24V) to a stable low output DC voltage (e.g., 3.3V). The simulation focuses on circuit accuracy by verifying pin configurations using the SPICE model rather than relying solely on datasheet schematics.

---

## 🔧 Features

- Converts high DC voltage (24V) to a stable 3.3V output
- High-resolution and ripple-free output waveform
- Can be used to create multiple power rails from a single input
- Circuit validated using SPICE model rather than datasheet schematic
- Demonstrates proper debugging practice using simulation tools

---

## 🧩 Components Used

| Component         | Value / Part No.  |
|------------------|-------------------|
| Power Supply      | 24V DC            |
| Input Capacitor   | 820µF             |
| Buck Converter IC | LM2596            |
| Diode             | MBRS340 (alternative component to datasheet recommended part number) |
| Inductor          | 33µH              |
| Output Capacitor  | 470µF             |

---

## 📐 Circuit Diagram

The schematic was drawn in **LTSpice**, and the IC pins were mapped based on the included `.lib` SPICE model file.

![LM2596 Schematic](LM2596_Spicemodel%20schematic.png)

---

## 🧪 Simulation Details

- **Tool**: LTSpice
- **Analysis Type**: Transient analysis
- **Duration**: 10ms
- **SPICE Model Used**: `LM2596_3P3_TRANS.LIB`
- **Node Probed**: Output voltage node

---

## 📊 Output Waveform

The output waveform shows the voltage ramping up to a steady **3.3V**, confirming proper operation.

![LM2596 Correct Waveform](LM2596%20correct%20wave%20form.png)



---

## 🛠️ How to Simulate

1. Open the `.asc` schematic file in **LTSpice**.
2. Ensure the correct `.lib` file for LM2596 is included.
3. Set up transient analysis for **10ms** using `.tran 10ms`.
4. Run the simulation and observe the output node.

---

## 🧠 Debugging & Observations

Initially, the simulation failed when using the circuit from the **datasheet**. This project takes a debugging-first approach:

- **Problem**: Datasheet schematic gave errors during simulation.
- **Resolution**: Pin configuration was cross-verified using the SPICE model.
- **Outcome**: Simulation succeeded and provided the expected 3.3V output.

✅ Lesson: Don’t trust the datasheet blindly in simulation—always verify with the actual SPICE model provided by the manufacturer.

---

## 🔍 IC Pin Details Reference

This section documents how the actual pin configuration of the LM2596 was verified using the SPICE model, due to mismatches when following the datasheet schematic.

### 📂 Reference Files

- [`LM2596_3P3_TRANS.LIB`](./LM2596_3P3_TRANS.LIB) – The SPICE model file used for simulation

### 🖼️ Screenshot from SPICE Model


![IC_pin_order_reference_from_spice_model](IC%20pin%20order%20reference%20from%20spice%20model.png)



### 📌 Extracted from `.LIB` file:
```spice
.SUBCKT LM2596_3P3_TRANS VIN FB OUT GND ON_OFF_N


## 🔮 Future Work

- Explore other fixed-output variants of LM2596 (e.g., 5V, 12V)
- Add current load testing to validate performance
- Design PCB based on verified schematic

---

## 👤 Author

**Karthick Raja T S**  
Date: July 2025  
Contact: *(Optional - GitHub, LinkedIn, etc.)*

---

