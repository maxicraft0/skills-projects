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
PPA: 204.8 GOPs maximum @200MHz, around 100 for yolov5? around 80kLUT and 50kFF in area. vivado reported power. hand over to a co-worker.
- a binary neural network accelerator implemented in FPGA, with VLIW controlling system,
binary convolution core and vector floating point coprocessor for non-binary operations.
PPA: 1024 GOPs peak @250MHz, around xx for reactnet, around 80kLUT and 80 kFF in area, vivado reported power.
- upgrading the BNN accelerator with RISC-V V compliant coprocessors. targeting both FPGA and ASIC.
- common building blocks used in both/all of my projects: FIFO,AXI,pheriphrals,memories

