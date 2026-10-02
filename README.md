# Comparative Analysis, Characterization and Simulation of a Flyback DC-DC Converter Planar Topology Transformer

**Paper ID:** 10754

**Authors:** Gabriel R. Bruzinga, Ademir Pelizari, Alfeu S. Filho, Jose Alberto Torrico Altuna and Vinicius Graias

---

## Overview

This repository contains the simulation and characterisation files supporting the paper above. The work compares two analytical sizing methodologies (Type A and Type B) for a planar transformer (PTT) used in a 20 W, 100 kHz CCM flyback converter, and validates the selected design through 3D finite-element analysis, prototype measurements and converter-level simulation.

The files are described below in British English, together with the figures and tables of the paper to which each one relates.

---

## File Descriptions

### 1) `trafo_plano_eddy.aedt`

An Ansys HFSS (or Ansys Electronics Desktop) project containing the 3D electromagnetic model of the planar transformer, used to evaluate the magnetic flux density, the electric-potential distribution, the current-density effects (skin and proximity), and the eddy-current behaviour in the windings.

**Related figures and tables:**

| Type | Label | Caption |
|------|-------|---------|
| Figure | `13` | Geometry and Boundary Conditions of the Studied Problem, Applicable to Electrostatic, Magnetostatic and Thermal Analyses. |
| Figure | `14` | Electrostatic Analysis of the Winding Tracks, Showing Sufficient Insulation Between Adjacent Turns. |
| Figure | `15` | Magnetostatic Analysis of the Core, Showing Magnetic Flux Densities Below Saturation Levels. |
| Figure | `17` | Current Density Analysis and Induction with Proximity Effect. |
| Table | `XVI` | Boundary Conditions. |

> *Assumption:* the electrostatic, magnetostatic and eddy-current results were grouped under this file, since they all derive from the same 3D electromagnetic model. If the electrostatic study is stored in a separate project, this mapping should be revised.

---

### 2) `trafo_plano_termica.aedt`

An Ansys Icepak (or thermal) project containing the thermal model of the planar transformer, used to evaluate the temperature distribution in the core and in the windings, as well as the loss density limits imposed by the admissible temperature rise.

**Related figures and tables:**

| Type | Label | Caption |
|------|-------|---------|
| Figure | `16` | Core Thermal and Windings Thermal Analysis. |
| Table | `III` | Steinmetz Coefficients — 3C95. |
| Table | `V` | Material's Coefficients. |
| Table | `XIII` | Detailed Type B Loss Budget at 100 kHz. |

> *Assumption:* the Steinmetz and material-coefficient tables are listed here because they feed the thermal/loss-density criterion used by the Type B methodology. If you prefer them under the analytical file, this can be moved.

---

### 3) `Conversor_Flyback_Planar_2.psimsch`

A PSIM schematic of the planar flyback converter, including the control loop, used to simulate the converter's dynamic behaviour, the regulated output voltage and the primary-switch waveforms using experimentally obtained transformer parameters.

**Related figures and tables:**

| Type | Label | Caption |
|------|-------|---------|
| Figure | `22` | Schematic of the Flyback Converter with the Designed PTT, Including the Control Loop, Implemented in PSIM. |
| Figure | `23` | Measured output voltage of the converter, reaching 10 V with 400 mV<sub>pp</sub> ripple at steady state. |
| Figure | `21` | Measured Voltage and Current Waveforms of the Primary Switch. |
| Table | `XIX` | Control Loop Parameters. |

> *Assumption:* the short-circuit and no-load tables were used as input parameters for this PSIM model, but they are listed under the measurement/supplementary file below. If you would rather associate them with the PSIM file, this can be adjusted.

---

### 4) `Conversor_Flyback_Planar_3.txt`

A plain-text file containing supplementary data and parameters supporting the analytical design, the loss calculations and the converter characterisation 

**Related figures and tables:**

| Type | Label | Caption |
|------|-------|---------|
| Figure | `6` | Power Loss Density at 100 kHz and 160 mT. |
| Figure | `7` | Maximum Flux Density at 100 kHz and 100 °C. |
| Figure | `9` | Estimated AC Resistances in the Primary Side as a Function of the *m* Factor. |
| Figure | `10` | Estimated AC Resistances in the Secondary Side as a Function of the *m* Factor. |
| Figure | `11` | Flowchart of the code for the 20 W case. |
| Figure | `19` | Measured impedance Z(ω) at the primary terminals. |
| Figure | `20` | Experimental Bench Used for the Functional Tests. |
| Figure | `18` | Measured DC and AC Resistances of the Prototype at 25 °C. |
| Table | `VIII` | Adopted Values. |
| Table | `IX` | Primary Side Winding Parameters. |
| Table | `X` | AC Resistance in Primary Side. |
| Table | `XI` | Secondary Side Winding Parameters. |
| Table | `XII` | AC Resistance in Secondary Side. |
| Table | `XVII` | Short-Circuit Results. |
| Table | `XVIII` | No-Load Test Results. |
| Table |  `XIV` | Sensitivity of the 2D Correction to the Track-to-gap Distance. |
| Table | `XV` | Comparison of the modelling levels. |

> *Assumption:* this file is treated as the "supporting data" container for the analytical and experimental results that are not directly produced by the 3D FEM or PSIM projects. If the content is narrower (for example, only the harmonic/2D extrapolation data), the list should be trimmed accordingly.

---

## Notes

- The `.aedt` files require Ansys Electronics Desktop (HFSS/Icepak) to open.
- The `.psimsch` file requires PSIM to open.
- The `.txt` file can be viewed with any text editor.
- All correlations above are cross-referenced to the `\label{}` names used in the paper's LaTeX source, so they remain unambiguous even if figure/table numbering changes.

---
