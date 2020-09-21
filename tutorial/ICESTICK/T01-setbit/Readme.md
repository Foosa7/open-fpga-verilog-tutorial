## Description

Component "hello world" with an output pin that is always at '1'.
When charging it on the iCEstick, led D1 lights up

## Simulation

To carry out the simulation enter the directory and execute:
```
make sim
```
Automatically icarus verilog will be invoked to do the compilation / simulation and gtkwave to see the result of the simulation graphically

## Synthesis

To implement the design in the FPGA we execute the command:
```
make sint
```
We generate the file setbit.bin that contains the FPGA configuration so that our digital circuit is implemented.

We then download it to the fpga using the command:
```
sudo iceprog setbit.bin
```




