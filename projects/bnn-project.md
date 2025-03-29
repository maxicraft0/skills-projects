This is for the description of the binary neural network acclerator project which is enhanced by a floating vector coprocessor.

The current project folder name is bnninf,

the project is with vivado 2021.2 

and targeting xilinx xcvu9p FPGA

The folder contains the following:
- bnninf.srcs main folder for our source and constraints, and sim tbs
- latex folder contains the paper content
- mapping/model_extraction for extracting parameter/input data from pytorch
- mapping/pytools for manual VLIW generation
- mapping/mapping for transfer to/from the FPGA
- mapping folder also contains the performance breakdown of ReActNet

The current hardware architecture is described as follows.
- two main computational modules exist: the BPU and the VFP coprocessor.
- The BPU perform all binary convolutions.
- the VFP coprocessor perform floating point operations before and after the binary convolution.
- axi interconnect connects the in/out dmas, the vliw buffer and ddr-mig.
- three sub-controllers, controller for BPU, controller for pre-conv and controller for post-conv. The main controller dispatch controll signals to the three sub-controllers.
- the pre/post conv controller is a little complicated since it has to issue not only instructions but also control data transfer from fbuf to VFP PEG.

