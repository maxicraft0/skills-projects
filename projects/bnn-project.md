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

