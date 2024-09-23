## Members
Nicholas Pacheck, Electrical Engineering Student (2026)
Eddie Pritchard, Computer Engineering Student (2024)

## Mentor
Eddie Pritchard

## Current Status
IN PROGRESS. SUPER HOT.

## Project Overview

Pacheck's BLDC driver is a 3 phase motor driver which uses HEXFETS and International Rectifier fet drivers. The main board is the FET/Driver board with optional daughter cards for control signal generation. 

The daughtercard supplies 3 phases of PWM as well as 3 phases of active low shutdown pins. The Channel inverter uses HEXFETS rated for automotive applications (40V, 160A). These HEXFETS will need to turn on and off relatively fast, as the PWM is 10kHZ-20kHZ. Yet they have a effective gate charge of around 300 nano Coulombs from the FETs gate capacitance (which needs to be filled quickly). 

Hence the Daughtercard provides the PWM to 3 IR2104 Mosfet drivers, which have an external bootstrap capacitor charged by a diode during the low-side commutation, preparing the cap to dump current into the high side gate.

The board also supports high current inline sensing using a 5mOhm shunt resistor on each phase. In line sensing was selected to avoid concerns about the instrumentation amplifier having to satisfy some Common-Mode-Rejection-Ratio requirement, as common mode voltage on high side sensing can seep into the output of our amp. Low side sensing wasn't selected due to the inability to detect fault currents. The current sense output should peak 3.3V output for a 15A load. 
In addition to current sensing, the board also offers switch node voltage sensing. The switch node is divided into a low current branch that feeds an antialiasing filter prior to ADC.

The ADC was spec.ed out for 38kHz on the atmega328-pu. Hence the highest frequency we can sample is 19kHz; thus I added an anti-aliasing low pass filter with a 19.2kHz BW prior to all adc conversions w 200 kHz transition range.

## Educational Value Added

Control Electronics, PCB design, POWER electronics and FET driver circuitry. Current sense circuitry. FOC motor drive schema.

## Tasks

ORDER PCB and components.

## Design Decisions

Designing around parts available at JLC PCBA assembly. 


## BOM + Component Cost

~$250 for 5 drivers. 

## Timeline

Order NOW!

## Log

9/23/2024 - Eddie Makes the project page
