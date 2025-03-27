To make our VFP-enhanced BNN accelerator compliant to RISCV V standard,
we have to study ara2 paper and github project.

since ara project use make build system,
we better off study the project on ubuntu-linux.

The ara2 project is divided into two big parts: a hardware folder and an app folder which is software side.

## before learning this ara2 project, we first get familiar with its AXI package dep
The test and AXI-Interconnect is found in BNNINF2 project folder.

## the software side is mainly llvm compile chain to riscv arch program

## Now lets dig into hardware side
The ara2 hardware folder contains the ara2 itself as well as its various kind of dependencies.
so the makefile builder can call the modelsim to start simulation.

we use questasim 10.7c for simulation.

the block diagram of the soc is here.

![the ara soc system](./res/ara_soc.svg)

## Firstly focus on only the CVA6 itself
we want to simulate the cva6 first then synthesize it using fronend tools.

### the cva6 simulation requirement
we need a L2 memory, an axi system connect the L2 with cva6.

we need the software under test, and we have to init the L2 upon simulation. 

we can simply remove the ara2 from the block diagram, and remove the mux as well.

### create a seperate project under ubuntu named cvatest
The project made small adaptations to ara2 project that only focus on the cva6 core

