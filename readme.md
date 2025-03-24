This is a repo for my potential CV content for a VLSI engineer
specifically for a digital domain

# two basic things
- one is the programming languages and HDL languages i master
as well as the EDA tools, both commercial and open-souce.
- one is the projects that i've gone through, from HDL to implementation.

# skills
- c/c++, python
- verilog/systemverilog
- simulation tools, including modelsim, VCS, etc
- frontend tools, vivado synthesis, synopsys IC
- backend tools, vivado P&R, innovus


# projects
- a 8-bit quantized CNN accelerator implemented in FPGA, with VLIW controller system, different kinds of computational cores, pheripherals
PPA: 204.8GOPs maximum @200MHz, around 120GOPs@200MHz for yolov5. kLUT/kFF/BRAM/DSP=80/64/192/517. vivado reported power. 
- a binary neural network accelerator implemented in FPGA, with VLIW controlling system,
binary processing core and a vector floating point coprocessor for non-binary operations.
PPA: 1024GOPs maximum @250MHz, around 633GOPs for reactnet@250MHz, kLUT/kFF/BRAM/DSP=87/132/221/259, vivado reported power.
- upgrading the BNN accelerator with RISC-V V compliant coprocessors. targeting both FPGA and ASIC.
- common building blocks used in both/all of my projects: FIFO,AXI,pheriphrals,memories

