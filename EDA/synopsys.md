This page record how to install synopsys EDA tools.

Synopsys2018 folder contains all sub-packages of synopsys EDAs.

also can refer to this page https://blog.csdn.net/qq_33589780/article/details/108720685 for installation process

# Install the synopsis installer first
Use the installer to install other synopsys EDAs.
1. you see the installer package contains a .run file, run it, specifying the installation directory
2. after install, run the setup.sh under the installation path. run setup.sh each for each package installation.
3. follow this sequence: scl -> other products
4. i have tickled both common and linux64 for each product

# Set up properly the PATH viarable

## create this shell and source it in .bashrc
```
#LICENCE
export SNPSLMD_LICENSE_FILE=27123@shrd-loan-it10
alias lmgrd_start='lmgrd -c /data_2t/chenzh/synopsys_scl/synopsys.lic'  #change to your lic file path

#scl
export PATH=$PATH:/data_2t/chenzh/synopsys_scl/scl/2018.06/linux64/bin    #scl install bin path

#Design Compalier
# export SYNOPSYS=/home/cjw/synopsys/dc2016           #not sure if this necessary
export PATH=$PATH:/data_2t/chenzh/synopsys_DC/syn/O-2018.06-SP1/bin     #DC bin path
# export DC_HOME=/home/cjw/Synopsys/dc2016  # not sure if this necessary
```



# synopsys design compiler(DC)

## need a few tricks upon installation
installation of DC on redhat linux may need libmng.1,
but installation using yum require sudo,
so we install manually
1. yum list libmng
2. yumdownloader libmng.x86_64
3. rpm2cpio libmng-2.0.3-7.el8.x86_64.rpm | cpio -idvm, but this is libmng.2 version, so
4. ln -s libmng.so.2 libmng.so.1
5. export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/data_2t/chenzh/usr/lib64

lc_shell requires a zlib specific version, we just remove the shlib/zlib.so.1 into a backup folder 

## DC process
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
