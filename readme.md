This is a repo for my CV content for VLSI engineer

# skills
- c/c++, python
- verilog/systemverilog
- simulation tools, including [modelsim](./EDA/modelsim.md), [synopsys](./EDA/synopsys.md) VCS, etc
- frontend tools, [vivado](./EDA/vivado.md) synthesis, [synopsys](./EDA/synopsys.md) DC
- backend tools, [vivado](./EDA/vivado.md) P&R, innovus, [openroad](./EDA/openroad.md)


# projects
- a [8-bit quantized CNN accelerator](./projects/q8-project.md) implemented in FPGA, with VLIW controller system, different kinds of computational cores, pheripherals
PPA: 204.8GOPs maximum @200MHz, around 120GOPs@200MHz for yolov5. kLUT/kFF/BRAM/DSP=80/64/192/517. vivado reported power. 
- a [binary neural network accelerator](./projects/bnn-project.md) implemented in FPGA, with VLIW controlling system,
binary processing core and a vector floating point coprocessor for non-binary operations.
PPA: 1024GOPs maximum @250MHz, around 633GOPs for reactnet@250MHz, kLUT/kFF/BRAM/DSP=87/132/221/259, vivado reported power.
- ASIC implementation of opensource CVA6 scalar core.

