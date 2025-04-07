This page record how to install synopsys EDA tools.

Synopsys2018 folder contains all sub-packages of synopsys EDAs.

# Install the synopsis installer first
Use the installer to install other synopsys EDAs.

# Set up properly the PATH viarable
```
export PATH=xxx;
```

# The license must be provided with lmgrd
```
export SNPSLMD_LICENSE_FILE=27000@simon-computer
alias lmgrd="lmgrd -c /home/simon/EDA/license/synopsys.dat"
```


## synopsys design compiler(DC)
Start the dc using design_vision.
This is mainly a tcl command line tool. Should be familiar with tcl cmd.
We can write a read_sv.tcl to analyze all the design files.
After analyzing, elaborate the design and specify top level module.
Then, source set_lib.tcl to set link lib and target lib,
source sdc constraint files.
Finally, use compile_ultra to compile and optimize the design.
After few minutes compilation, report timing/power/area, output netlist using write command.

- analyze the HDL sources. using a tcl is recomended.
- elaborate your_top_module
- source set_lib.tcl, which set link_library and target_library.
- source xxx.sdc to set design rule and optimization constraints.
- compile_ultra.
- report_timing, report_area, report_power
- write -format verilog -hierarchy -output your_output_netlist

## synopsys Functional Verification Solution(VCS)
Not commonly use, i think modelsim is enough.
