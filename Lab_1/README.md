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

To simulate this cell, I created a new schematic and included one R_Divider cell symbol. LTspice was used to simulate the circuit.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_sim.png)

You can see the correct output voltage for this circuit.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_sim_spice.png)

### Electric Layout

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_lay.png)

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_lay_3D.png)

## Lab Questions

## Aditional Comments
