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

## synopsys Functional Verification Solution(VCS)
