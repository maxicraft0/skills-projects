

# modelsim SE-2020.4 for windows
under folder "Mentor Graphics ModelSim SE 2020.4 x64.rar"
- a package for installation
- a crack folder

# questasim 10.7c for ubuntu-linux
- package Mentor Graphics QuestaSim 10.7c linux64 for pure installation, we should install both base and linux
- mentor2021_crack containing a python2 script for license gen and a patch program
- python2 script generated license is configured through LM_LICENSE_FILE
- patch pubkey_verify should be moved to questasim installation folder for patching

# cmdline and tcl script for modelsim

## create lib and remove lib

```
vlib work
```
```
vdel -all work
```

## compile modules into the lib
```
vsim -c -work work -do compile.tcl
```
where compile.tcl is the tcl script for compilation.

the tcl script may look like this
```
if {[catch { vlog -incr -sv \
    -suppress vlog-2583 -suppress vlog-13314 -suppress vlog-13233 -work work \
    +define+TARGET_ARA_TEST \
    +define+TARGET_CV64A6_IMAFDCV_SV39 \
    +define+TARGET_CVA6_TEST \
    +define+TARGET_EXCLUDE_FIRST_PASS_DECODER \
    +define+TARGET_RTL \
    +define+TARGET_SIMULATION \
    +define+TARGET_TECH_CELLS_GENERIC_INCLUDE_TC_CLK \
    +define+TARGET_TECH_CELLS_GENERIC_INCLUDE_TC_SRAM \
    +define+TARGET_VSIM \
    +define+NR_LANES=4 \
    +define+VLEN=4096 \
    +define+ARIANE_ACCELERATOR_PORT=1 \
    +incdir+include	\
	"config_pkg.sv"	\
	"cv64a6_imafdcv_sv39_config_pkg.sv"	\
	"riscv_pkg.sv" \
	"rvv_pkg.sv" \
	"cf_math_pkg.sv"	\
	"axi_pkg.sv"	\
	"fpnew_pkg.sv"	\
	"ara_pkg.sv" \
    "build_config_pkg.sv"   \
    "ara_sequencer_tb.sv" \
    "lzc.sv" \
    "ara_sequencer.sv" \
    "counter.sv" \
    "delta_counter.sv" 
}]} {return 1}

exit
```
curly braces are used to describe literal string while square braces are for substitution.

## simulate the hardware design
```
vsim -work work work.ara_sequencer_tb -voptargs=+acc -do wave.do
```
wave.do is also a tcl script
