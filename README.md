# CMOS Circuit Design Spice Simulation - Sky130nm
Hands on workshop covers MOSFET fundamentals, CMOS design, NGSPICE simulations using sky130 technology

# Workshop Overview
This workshop follows a structured learning:

# Day 1: Basics of NMOS Drain Current(Id) vs Drain-to-source Voltage(Vds)
1) Introduction to Circuit Design and Spice Simulations - Why do we need SPICE simulations?, Introduction to basic element in circuit design-NMOS, Strong inversion and threshold voltage, Threshold voltage with positive substrate potential
2) NMOS resistive region and Saturation region of operation - Resistive region of operation with small drain-source voltage, Drift current theory, Drain current model for Linear region of operation, SPICE conclusion to resistive operation, Pinch-off region condition, Drain current model for saturation region of operation
3) Introduction to SPICE - Basic SPICE setup, Circuit description in SPICE syntax, Define Technology parameters, First SPICE simulation, SPICE lab with Sky130 models

# Day 2: Velocity saturation and basics of CMOS inverter VTC
1) SPICE simulation for lower nodes and velocity saturation effect - SPICE simulation for lower nodes, Drain current vs gate voltage for long and short channel device, Velocity saturation at lower and higher electric fields, Velocity saturation drain current model, Labs Sky130 Id-Vgs, Labs Sky130 Vt
2) CMOS voltage transfer characteristics (VTC) - MOSFET as a switch, Introduction to standard MOS voltage current parameters, PMOS/NMOS drain current vs drain voltage, Step1- Convert PMOS gate-source-voltage to Vin, Step2 & Step3- Convert PMOS and NMOS drain-source-voltage to Vout, Step4- Merge PMOS-NMOS load curves and plot VTC

# Day 3: CMOS switching threshold and dynamic simulations
1) Voltage transfer characteristics-SPICE simulations - SPICE deck creation for CMOS inverter, SPICE simulation for CMOS inverter, Labs Sky130 SPICE simulation for CMOS
2) Static behaviour evaluation-CMOS inverter robustness-Switching Threshold - Switching Threshold, Vm, Analytical expression of Vm as a function of (W/L)n and (W/L)p, Analytical expression of (W/L)n and (W/L)p as a function of Vm, Static and Dynamic simulation of CMOS inverter, Static and Dynamic simulation of CMOS inverter with increased PMOS width, Applications of CMOS inverter in clock network and STA

# Day 4: CMOS Noise Margin robustness evaluation  
1) Static behaviour evaluation-CMOS inverter robustness-Noise Margin - Introduction to Noise Margin, Noise Margin voltage parameters, Noise margin equation and summary, Noise margin variation with respect to PMOS width, Sky130 Noise margin labs

# Day 5: CMOS power supply and device variation robustness evaluation  
1) Static behaviour evaluation-CMOS inverter robustness-Power supply variation - Smart SPICE simulations for power supply variations, Advantages and disadvantages using low supply voltage, Sky130 Supply variation Labs
2) Static behaviour evaluation-CMOS inverter robustness-Device variation - Sources of variation - Etching process, Oxide Thickness, Smart SPICE simulation for device variations, Conclusion, Sky130 device variations labs
   
# Introduction to Circuit Design and SPICE Simulations
## L1: Why do we need SPICE simulations?
In CMOS circuit design, PMOS and NMOS transistors are connected together to form logic gates such as NAND, NOR, AND, OR, etc. These basic gates are the building blocks of all digital circuits.</br>

<img width="498" height="501" alt="image" src="https://github.com/user-attachments/assets/0f1df6c3-cd81-41d3-98c3-70f95b2b0062" />

The inverter shown above has certain electrical characteristics. To understand its behavior, we perform SPICE simulations. These simulations help us analyze important parameters such as delay, switching behavior, and performance. Based on these results, we can determine the proper W/L (Width/Length) ratio of the transistors.</br>

<img width="808" height="582" alt="image" src="https://github.com/user-attachments/assets/c45af49c-15c7-4608-baa1-e767506be15a" />

- Why do we need SPICE?
SPICE (Simulation Program with Integrated Circuit Emphasis) is a very important tool in circuit design. It is used to analyze and predict the behavior of electronic circuits before actual fabrication.</br>

Modern design techniques such as clock tree synthesis, timing analysis, and crosstalk evaluation are all based on SPICE simulations. Without SPICE, it would not be possible to calculate delays, and without delay information, physical design and timing verification would not be meaningful.</br>

For example, consider a clock distribution network where buffers are connected with different capacitive loads.</br>

  
















