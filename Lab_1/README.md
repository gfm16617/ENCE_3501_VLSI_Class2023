# Lab 1 - 5-bit DAC

## Table of Contents
- [Lab Description](#lab-description)
- [General Schematic](#general-schematic)
- [Technology Description](#technology-description)
  - [Fabrication Process](#fabrication-process)
  - [Design Rules](#design-rules)
- [R_Divider Cell](#r_divider-cell)
  - [Electric Schematic](#electric-schematic)
  - [Electric Layout](#electric-layout)
- [5Bit DAC](#5bit-dac)
  - [Electric Schematic (DAC)](#electric-schematic-(dac))
  - [Electric Layout (DAC)](#electric-layout-(dac))
- [Lab Questions](#lab-questions)
- [Additional Comments](#additional-comments)

## Lab Description
The goal with this lab is to design a 5-bit R-2R Ladder Digital to Analog Converter (DAC) without an op-amp.

## General Schematic
![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/5bit_DAC_schematic.png)

## Technology Description

### Fabrication Process

For all labs in this class, we are using the ON Semiconductor's C5 process and fabrication through [MOSIS](https://www.themosisservice.com/). This CMOS process has 3 metals layers, 2 poly layers, and a high resistance layer.

You can find more information about the process technology on this [link](https://www.onsemi.com/site/pdf/C5-D.PDF).

For this lab we are interested on the table that contains the device characteristic of resistors.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/resistor_c5_process.png)

### Design Rules

The labs are also using the MOSIS scalable CMOS (SCMOS) submicron design rules [(Link)](https://www.egr.msu.edu/classes/ece410/demlow/files/DRC_rule_scmos.pdf).

Since this lab is about resistors implemented at the well layer, below you have the table with the minimum dimensions for the well width, space and overlap.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/submicron_drc_rules.png)

## R_Divider Cell

Since the R-2R Ladder relies on connecting a bunch of resistors in a voltage divider fashion, let's create a cell that represents the 2R and R components first.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/dac_subsection.png)

### Electric Schematic

For this lab, we are building the resistors at the n-well layer and we are only using 10k resistors.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/n_well_menu.png)

To select the correct resistor dimensions (L and W), we will use the equation (in black) below. Have in mind that for the technology that we are using the resistance per square at the n-well is 855 ohm/sq.

We are also going to work with a fixed width. We can select any width that we want as long as it is bigger than 12 (DRC Sub-micron rule). I will be working with a width of 15.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/n_well_RCalc.jpg)

The schematic is then created with the defined requirements.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_sch.png)

To simulate this cell, create a new schematic and includ one R_Divider cell symbol. LTspice is used to simulate the circuit.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_sim.png)

You can see the correct output voltage for this circuit, that means that the schematic was designed correctly.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_sim_spice.png)

### Electric Layout

The layout follows the same design process used during the schematic design. Select n-well resistors and adjust the dimensions accordingly.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/n_well_lay_menu.png)

The resistors are laid out in parallell having the same x-position but varying y-positions (serpentine layout).

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_lay.png)

You can view the layout in 3D.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_lay_3D.png)

To simulate this layout cell, create a new layout and include one R_Divider layout cell. LTspice is used to simulate the circuit.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_lay_sim.png)

You can see the correct output voltage for this circuit, that means that the layout was designed correctly.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_lay_sim_spice.png)

## 5Bit DAC

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/project_cells.png)

### Electric Schematic (DAC)

TODO

### Electric Layout (DAC)

TODO

## Lab Questions

- Find and explain how to determine the output resistance of the DAC
- Delay driving the load
  - Ground all DAC inputs except B4. Connect B4 to a pulse source (0 to vdd) and show and predict using 0.7RC, the delay the DAC has driving a 10pF load
  - Verify the simulation results match your hand calculation
- Simulations to verify your design functions correctly
  - Apply different values to the input of the DAC and check if the output has the correct value
  - Explain what happens if the DAC drives a 10k load

## Aditional Comments

- DRC and NCC your design (show the results of the test)
