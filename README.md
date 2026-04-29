# ⚡ Analog IC Designs & Simulations

Welcome to my Analog IC Design repository! This workspace contains my schematic-level designs, simulations, and performance analyses of fundamental analog circuits. 

My goal with this repository is to bridge the gap between theoretical textbook concepts and practical, real-world transistor-level design, with a strong focus on understanding fundamental engineering trade-offs (e.g., gain vs. bandwidth, headroom vs. speed).

## 📂 Project 1: Two-Stage Operational Transconductance Amplifiers (OTAs)
*Located in the `OpAmps` directory.*

This project explores the design and optimization of two-stage OTAs, progressing from idealized theoretical testbenches to robust, practically biased circuits. 

* **Phase 1: Ideal Biasing (Theoretical Baselines)**
  * Simulated **Telescopic Cascode** and **Folded Cascode** topologies using ideal current/voltage sources.
  * *Objective:* To establish theoretical maximums for DC gain, Unity Gain Bandwidth (UGB), and Phase Margin before introducing the parasitic effects of a real bias network.
* **Phase 2: Practical Biasing (Constant-gm / Beta-Multiplier)**
  * Replaced ideal sources with self-biased constant-gm networks to ensure Process, Voltage, and Temperature (PVT) independence.
  * Designed and analyzed four variations: NMOS/PMOS input Telescopic OTAs and NMOS/PMOS input Folded OTAs.
  * *Key Takeaways:* Successfully demonstrated the real-world trade-offs. The Telescopic designs achieved superior high-frequency performance (~64.7 MHz UGB), while the Folded topologies sacrificed some speed to provide a vastly improved Input Common Mode Range (ICMR) and output voltage swing.

## 📂 Project 2: Low Dropout (LDO) Voltage Regulator
*Located in the `LDO` directory.*

A complete schematic design of a linear Low Dropout (LDO) regulator, engineered using the **TSMC 180nm** technology node. The architecture features a core error amplifier driving a PMOS pass transistor with a resistive feedback network.

**Simulated Verifications:**
* **Line Regulation:** Verified stable output tracking (regulating to 1.2V) as the input supply sweeps from 0V to 2.0V.
* **Load Regulation:** Confirmed tight voltage maintenance across a steady-state load current sweep from 0mA up to 20mA.
* **Transient Response:** Extracted voltage spike and recovery time metrics during instantaneous step changes in load current to guarantee dynamic stability.

## 🛠️ Tools & Technologies
* **Simulation Environment:** LTspice
* **Technology Nodes:** TSMC 180nm CMOS model parameters
* **Analysis Types:** AC Sweep (Bode plots), DC Sweep, Transient Analysis, Operating Point (.op) extraction.

## 🚀 Future Roadmap
* Integrating digital control with these analog blocks.
* Developing a "SmartBias" hardware-in-the-loop system using an STM32 microcontroller and I2C DACs for automated PVT compensation of these amplifier topologies.
* Full-custom layout design and DRC/LVS verification using industry-standard EDA tools.
