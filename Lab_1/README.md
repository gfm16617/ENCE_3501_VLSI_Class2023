# Lab 1 - 5-bit DAC

## Table of Contents
- [Lab Description](#lab-description)
- [General Schematic](#general-schematic)
- [Technology Description](#technology-description)
- [R_Divider Cell](#r_divider-cell)
  - [Electric Schematic](#electric-schematic)
  - [Electric Layout](#electric-layout)

## Lab Description
The goal with this lab is to design a 5-bit R-2R Ladder Digital to Analog Converter (DAC) without an op-amp.

## General Schematic
![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/5bit_DAC_schematic.png)

## Technology Description

For all labs in this class, we are using the ON Semiconductor's C5 process and fabrication through [MOSIS](https://www.themosisservice.com/). This CMOS process has 3 metals layers, 2 poly layers, and a high resistance layer. The labs also use the MOSIS scalable CMOS (SCMOS) submicron design rules.

You can find more information about the process technology on this [link](https://www.onsemi.com/site/pdf/C5-D.PDF).

For this lab we are interested on the table that contains the device characteristic of resistors.

resistor_c5_process -> picture

## R_Divider Cell

Since the R-2R Ladder relies on connecting a bunch of resistors in a voltage divider fashion, let's create a cell that represents the 2R and R components first.

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/dac_subsection.png)

### Electric Schematic

For this lab, we are building the resistors at the n-well layer and we are only using 10k resistors.

n_well_menu -> picture

To select the correct resistor dimensions (L and W), we need to select the

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_sch.png)

### Electric Layout

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_lay.png)

![image](https://github.com/gfm16617/ENCE_3501_VLSI_Class2023/blob/main/Lab_1/images/r_divider_lay_3D.png)

## Aditional Comments
