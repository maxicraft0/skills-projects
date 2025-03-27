To make our VFP-enhanced BNN accelerator compliant to RISCV V standard,
we have to study ara2 paper and its github project.

## AXI package dependency that is used by ara2 is extensively studied
This portion is under project bnninf2 with windows vivado.
We simulate the common building blocks: xbar, dw_converter, cdc, and build a parameterized axi-interconnect.

## Two main parts of the ara2 project
- the software side, which compiles source codes into elf.
- the hardware side, which technically includes both ara2 and cva6 the scalar core.

the block diagram of the soc is here.

![the ara soc system](./res/ara_soc.svg)

## Focusing on the scalar core CVA6
we want to simulate the cva6 first then synthesize it using frontend tools.

### cvatest project which is converted and adapted from ara2 project
The project eliminated ara2. The simulation tb are mostly untouched.

We get the 5 main components/stages of the cva6: frontend->instr_decode->issue->execute->commit
