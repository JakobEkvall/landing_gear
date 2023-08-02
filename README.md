# landing_gear
PCB for the Shafter quadrotor landing platforms stepper motor and limit switches. 

Schematics and PCB designed with KiCad. 

Mouser cart for the needed components: https://www.mouser.se/ProjectManager/ProjectDetail.aspx?AccessID=22832bf478

The core of the circuit is an Atmega328P, set up in the same way as the Arduino Nano MCU with a USB connection. 

Stepper motor is driven with a DRV8825 IC.

Limit switches are active LOW.

The whole circuit is powered with a battery, minimum input voltage should be around 8V (otherwise the stepper motor driver will not work) and the maximum battery voltage should not exceed 15V, otherwise the 5V regulator could be damaged. Heatsinks might be needed for the stepper driver IC and the 5V regulator, depending on the input battery voltage and the power consumption of the stepper motor. 

Two resistors on the PCB, R3 and R4, do not have values as that depends on the specific model of  stepper motor used and other factors, see section 8.3.2 in the datasheet for further information on resistor value selection https://www.ti.com/lit/ds/symlink/drv8825.pdf?ts=1690949266854&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FDRV8825. 

 All of the digital pins on the stepper motor IC are routed to pins on the microcontroller, so MODE and DECAY etc will have to be defined in code and is not preset. 
