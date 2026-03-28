Project Title
Delay Line Time-to-Digital Converter (DLTDC)
One-line Description
A transistor-level CMOS implementation of a Delay Line Time-to-Digital Converter designed and simulated in LTspice using the TSMC 0.18 µm process library, achieving a resolution of 60.00 ps.

About the Project
A Time-to-Digital Converter (TDC) measures the time interval between two events and converts it into a digital code. This project implements a Delay Line TDC at the transistor level using pure CMOS logic. Since LTspice's built-in gates are ideal and cannot model propagation delays, all logic gates and flip-flops were custom-designed from scratch using NMOS and PMOS transistors from the TSMC 0.18 µm library.

Motivation
The micro-electronics community is rediscovering TDCs beyond all-digital PLLs. Modern VLSI technology enables TDC designs that meet commercial requirements for cost, reproducibility, and mass production. This project explores the delay-line approach for its fine resolution, wide dynamic range, and area efficiency.

How It Works
The DLTDC measures the time between a START pulse and a STOP pulse by propagating the START signal through a chain of delay elements and checking how far it traveled when the STOP signal arrives.

Start signal is triggered and propagates through the delay chain
Stop signal halts propagation and samples all delay elements
Elements the START passed through output HIGH — forming a thermometer code
Count of HIGH outputs gives the digital time value
Formula: ΔT = N × t_d (N = HIGH outputs, t_d = delay per element)


Specifications

Achieved Resolution: 60.00 ps
Process Technology: TSMC 0.18 µm CMOS
Supply Voltage: 1.8 V
Dynamic Range: Wide
Linearity: High
Simulation Tool: LTspice XVII


Circuit Components Built
All circuits were designed from scratch using only NMOS and PMOS transistors.
Gates designed: Inverter, NAND2, NAND3, AND, Buffer
D Flip-Flop with asynchronous SET and CLEAR inputs — used as the sampling element in the delay chain
Full DLTDC system assembled from all custom cells

Simulation Results

Inverter — Correct logic inversion verified
NAND2 / NAND3 — Correct truth table verified
NOR — Correct truth table verified
D Flip-Flop — Correct state transitions with SET/CLEAR verified
Full DLTDC System — Thermometer code output verified


Simulation Tool
LTspice XVII by Analog Devices was used for all simulations. TSMC 0.18 µm NMOS/PMOS models were imported for realistic transistor-level delay simulation. Each block was tested with a separate testbench before integration into the full system.

Applications

Particle physics experiments (e.g., LHC time-of-flight measurement)
LIDAR systems in autonomous vehicles and robotics
Time-of-Flight cameras for 3D imaging and gesture recognition
Medical imaging — PET and SPECT scanners
Radar systems for range estimation and target tracking
IC testing and characterization in semiconductor manufacturing
Time-of-arrival localization in wireless communication systems


Limitations

Low readout speed due to cyclic (loop-based) delay line
Nonlinearities present from pre-characterized TSMC library cells
Performance is tied to TSMC 0.18 µm process parameters


Future Scope

Temperature-to-Digital Converter using temperature-dependent delay elements
Analog-to-Digital Converter using time-domain quantization
Unified chip performing time, analog, and temperature conversion
IC layout for actual chip fabrication
Custom transistor-level cell design to reduce nonlinearity

