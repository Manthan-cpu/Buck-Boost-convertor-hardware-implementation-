# Buck-Boost Converter Design, Simulation and Hardware Implementation

## Overview

This project presents the design, simulation, and hardware implementation of an inverting Buck-Boost Converter developed as part of the EE252 Electrical Machines and Power Electronics Laboratory at IIT Indore.

The converter is designed to operate from a fixed 15 V DC input source and provide a controllable output voltage in the range of 12–18 V while delivering up to 1 A load current. Both Continuous Conduction Mode (CCM) and Discontinuous Conduction Mode (DCM) operations were studied and experimentally verified.

The project includes:

- Theoretical design calculations
- MATLAB/Simulink simulation
- Gate driver implementation using TL494 and TC4428A
- Hardware prototype fabrication
- Experimental waveform verification

---

## Project Specifications

| Parameter | Value |
|------------|---------|
| Input Voltage | 15 V |
| Output Voltage | 12 – 18 V |
| Output Current | 1 A |
| Switching Frequency | 12.5 kHz |
| Converter Type | Inverting Buck-Boost |
| Inductor | 1 mH |
| Output Capacitor | 470 µF |
| PWM Controller | TL494 |
| Gate Driver | TC4428A |
| Power MOSFET | IRFZ44NPbF |
| Diode | QH08TZ600 |

---

## Working Principle

The Buck-Boost converter stores energy in the inductor during the ON period of the MOSFET and transfers the stored energy to the load during the OFF period.

### MOSFET ON

- Diode is reverse biased
- Inductor stores energy
- Inductor current rises linearly

### MOSFET OFF

- Diode becomes forward biased
- Stored energy is delivered to the output
- Inductor current decreases linearly

The ideal voltage conversion ratio is:

\[
\frac{V_o}{V_{in}} = -\frac{D}{1-D}
\]

where:

- \(D\) = Duty Cycle
- Negative sign indicates output polarity inversion

---

## Gate Driver Design

### TL494 PWM Controller

The TL494 PWM controller is used for generating switching pulses.

Features:

- Adjustable duty cycle
- Adjustable frequency
- Internal oscillator
- Dead-time control
- Error amplifiers

### TC4428A MOSFET Driver

The TC4428A driver provides:

- Fast gate charging
- Fast gate discharging
- Reduced switching losses
- Improved switching performance

The driver board includes:

- D-VARY potentiometer for duty cycle control
- F-VARY potentiometer for frequency control

---

## MATLAB Simulation

The converter was modeled and simulated in MATLAB Simulink.

### Simulation Objectives

- Verify voltage conversion ratio
- Observe inductor voltage waveform
- Observe diode current waveform
- Verify CCM operation
- Verify DCM operation

### Simulation Results

- Output Voltage
- Inductor Voltage
- Diode Current
- Inductor Current in DCM

Simulation results matched theoretical expectations.

---

## Hardware Implementation

The hardware prototype consists of:

- TL494 PWM Controller Board
- TC4428A MOSFET Driver
- IRFZ44NPbF Power MOSFET
- QH08TZ600 Hyperfast Diode
- 1 mH Toroidal Inductor
- 470 µF Output Capacitor
- Variable Rheostat Load

The circuit was assembled on a soldered PCB and tested under laboratory conditions.

---

## Experimental Verification

### Continuous Conduction Mode (CCM)

Verified Waveforms:

- Output Voltage
- Inductor Voltage
- Diode Current
- Gate Pulse

Observations:

- Inductor current remains above zero
- Stable output voltage
- Expected diode conduction intervals

### Discontinuous Conduction Mode (DCM)

DCM was demonstrated by reducing the switching frequency.

Observed:

- Inductor current reaches zero
- Diode current exhibits zero-current interval
- Energy transfer becomes discontinuous

---

## Results

The hardware results showed good agreement with:

- Theoretical calculations
- MATLAB simulations

Minor differences were caused by:

- MOSFET switching losses
- Diode forward voltage drop
- Inductor winding resistance
- Capacitor ESR
- PCB parasitic effects

---

## Applications

- Battery-powered devices
- Electric vehicles
- Renewable energy systems
- Solar photovoltaic systems
- Embedded electronics
- Industrial automation
- Portable instrumentation

---

## Repository Contents
