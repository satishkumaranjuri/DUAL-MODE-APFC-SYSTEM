# DUAL-MODE-APFC-SYSTEM
A Raspberry Pi-based Dual-Mode Automatic Power Factor Correction (APFC) system supporting Household and Industrial loads with Hardware-in-the-Loop (HIL) simulation

# Dual-Mode Automatic Power Factor Correction (APFC) System
An advanced, embedded solution designed to optimize electrical efficiency and reduce penalty tariffs by dynamically correcting the power factor ($\text{PF}$). Powered by a Raspberry Pi, this system features a dual-mode control architecture tailored to handle the distinct characteristics of both household and industrial inductive loads. To ensure safety and scalability during development, the system incorporates Hardware-in-the-Loop (HIL) simulation.

## 🚀 Features

* **Dual-Mode Control Logic:**
  * **Household Mode:** Optimized for highly fluctuating, single-phase single-device or small-scale inductive loads.
  * **Industrial Mode:** Engineered for heavy, balanced/unbalanced three-phase inductive loads requiring multi-stage capacitor bank switching.
* **Hardware-in-the-Loop (HIL) Simulation:** Simulates dynamic load profiles and high-voltage environments safely in real time, allowing full validation of control loops without physical high-voltage hazards.
* **Anti-Chattering & Over-Correction Protection:** Built-in software delays and threshold logic prevent rapid relay toggling (chattering) and leading power factor scenarios.
* **Real-time Monitoring:** Python-driven execution loop tracking active power ($P$), apparent power ($S$), and target vs. current power factor.

---

## 🛠️ System Architecture

The core of the system relies on the mathematical optimization of the power factor triangle:

$$\text{PF} = \frac{P}{S} = \cos(\theta)$$

Where:
* $P$ = Active Power (Watts)
* $S$ = Apparent Power (VA)
* $Q$ = Reactive Power (VAR)

When an inductive load causes the power factor to drop, the Raspberry Pi calculates the precise reactive power compensation required ($Q_c$) and activates the corresponding relay stages to introduce capacitor steps.

### Block Diagram

