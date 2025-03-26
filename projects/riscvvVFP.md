To make our VFP-enhanced BNN accelerator compliant to RISCV V standard,
we have to study ara2 paper and github project.

since ara project use make build system,
we better off study the project on ubuntu-linux.

The ara2 project is divided into two big parts: a hardware folder and an app folder which is software side.

## the software side is mainly llvm compile chain to riscv arch program

## Now lets dig into hardware side
The ara2 hardware folder contains the ara2 itself as well as its various kind of dependencies.
so the makefile builder can call the modelsim to start simulation.

we use questasim 10.7c for simulation.

![the ara soc system](./res/ara_soc.svg)

