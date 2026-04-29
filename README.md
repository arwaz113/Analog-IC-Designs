# Analog IC Designs & Simulations

This repository contains schematic-level designs and LTspice simulations of fundamental analog circuits. The objective is to analyze practical transistor-level trade-offs, specifically gain vs. bandwidth and headroom vs. speed.

## Project 1: Two-Stage OTAs (`/OpAmps`)
This directory explores the design of two-stage Operational Transconductance Amplifiers, progressing from theoretical baselines to practically biased circuits.

* **Ideal Biasing:** Simulated Telescopic and Folded Cascode topologies using ideal current and voltage sources to establish theoretical maximums for DC gain, Unity Gain Bandwidth (UGB), and Phase Margin. 
* **Practical Biasing:** Replaced ideal sources with a supply-independent constant-gm (beta-multiplier) network to ensure robustness across Process, Voltage, and Temperature (PVT) variations.
* **Topology Analysis:** Evaluated four variations (NMOS and PMOS input Telescopic and Folded OTAs). AC analysis confirmed that Telescopic designs achieved higher bandwidth (e.g., 64.72 MHz UGB for the Telescopic N-MOS), while Folded topologies traded high-frequency speed for improved Input Common Mode Range (ICMR) and output voltage swing.

## Project 2: Low Dropout (LDO) Voltage Regulator (`/LDO`)
A linear LDO regulator designed and simulated using the TSMC 180nm technology node. 

* **Architecture:** Features a core error amplifier driving a PMOS pass transistor, regulated by a resistive feedback network.
* **Line Regulation:** Verified stable output tracking, stabilizing at 1.2V as the input supply sweeps from 0V to 2.0V.
* **Load Regulation:** Maintained tight regulation at ~1.2V across a steady-state load current sweep from 0mA to 20mA.
* **Transient Response:** Load transient analysis validated system recovery time and voltage spike suppression during instantaneous step changes in load current.
