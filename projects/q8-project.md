This markdown describes the quantized 8-bit accelerator project.

The current version of the project is named: dnn_325t_2018_on6678_alltasks

managed with vivado 2018.3

targeting FPGA xc7k325t

the project folder contains the following sub-dirs:
- dnn_690_2018.src, which is mainly our own sources
- dnn_690_2018.xdc, our constraint file is here
- dnn_690_2018.srcs, our main sim dir

the current hardware architecture is described as follows:
- the hardware contains a PE module, which perfroms all 8-bit quantized operations in a cnn network
- the PE module communicate with input reader and output writer transfer data in tiles
- the controller module read vliw cmd and dispatch the control signal to all modules.
- the axi-interconnect connects input reader, output writer, sriorx/tx with ddr-mig, vliw-buffer and bias-buffer.
