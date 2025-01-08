Universal Shift Register

This repository contains the Verilog implementation of a Universal Shift Register along with its testbench. The universal shift register supports parallel loading, left shift, right shift, and holding its current state.

Features

Supports Four Operations:

Hold: Maintains the current state.
Parallel Load: Loads parallel input data into the register.
Left Shift: Shifts the data to the left with serial input.
Right Shift: Shifts the data to the right with serial input.
Parameterizable 4-bit Design: Can be expanded to handle wider data widths.
Reset Signal: Resets the register to a known state.

Design Description

Module: uni_shi_rtl
The universal shift register is implemented using Verilog and operates based on the select input.

Ports

Inputs:

clk: Clock signal.
reset_n: Active-low reset signal.
select: 2-bit signal to select the operation (Hold, Left Shift, Parallel Load, Right Shift).
s_in: Serial input for shift operations.
p_in: Parallel input for loading data.

Outputs:

p_out: Parallel output representing the current state of the register.
s_out: Serial output (leftmost or rightmost bit of the register).

Functionality

select	Operation	Description

00	Left Shift	Shifts left with s_in as the new LSB.

01	Right Shift	Shifts right with s_in as the new MSB.

10	Parallel Load	Loads p_in into the register.

11	Hold Current State	Retains the current state.

Testbench Description

Module: shi_reg_tb
The testbench verifies the functionality of the universal shift register by:

Applying various combinations of select and inputs.
Monitoring the register's output (p_out) and serial output (s_out).

Key Test Scenarios

Reset the register and verify the output.
Perform parallel loading of input data.
Execute left and right shifts with varying serial inputs.
Validate the hold operation.
