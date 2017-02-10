# OPAL (Ordinary People Accelerating Learning)

*OPAL* is design tool that uses artificial neural networks (ANN) to automate the design and optimization of other ANNs: neural networks designing neural networks. *OPAL* is available for download as a compiled library (developed in python3) for educational and research purposes. Source code is available for educational and research purposes upon request at [opal@ece.mcgill.ca](mailto:opal@ece.mcgill.ca); for commercialization options, [contact us](mailto:opal@ece.mcgil.ca).

*OPAL* is a joint effort between the Reliable Silicon Systems Lab (RSSL) directed by Professor [Brett H. Meyer](http://rssl.ece.mcgill.ca) and the Integrated Systems for Information Processor (ISIP) Lab directed by Professor [Warren J. Gross](http://www.isip.ece.mcgill.ca). If you use *OPAL* in your research, please cite [our paper](https://arxiv.org/abs/1611.02120):
> Sean C. Smithson, Guang Yang, Warren J. Gross, and Brett H. Meyer, "Neural networks designing neural networks: Multi-objective hyper-parameter optimization," 2016 International Conference On Computer Aided Design (ICCAD’16), November 2016.

## Overview

The design of ANN hyper-parameters has long been considered unwieldy, unintuitive, and as a consequence, ideal for automated hyper-parameter optimization techniques. Most current approaches focus on optimizing accuracy, with little regard to the resulting computational resource requirements. *OPAL* uses response surface modelling to learn the relationship between ANN hyper-parameters and network accuracy, and further employs a model of the cost of network implementation (e.g., in C or CUDA) to direct ANN design space exploration and expose the best accuracy-cost trade-offs possible.

## Usage

The tool can be used by simply executing the *OPAL* terminal script followed by a configuration file as input (e.g. './OPAL example.cfg'). The outputs generated by the tool are binary (numpy '.npy' formatted) and plain text formatted files containing the exploration results (input hyper-parameter and resulting cost/accuracy  pairs). Sets of files containing the entire exploration results as well as only the Pareto-optimal front results are generated.

## Configuration Files

The general structure of the configuration files is split up into five distinct sections: \[General\], \[DSE\], \[Cost\], \[Parameters\], and \[RSM\]. The possible parameters and values for each section are outlined below.

### General Section:

The \[General\] section contains the configuration options pertinent to the input and output file locations, and type of design problem. The possible input to this section are:

Parameter | Description | Possible Values
--------- | ----------- | ---------------
'verbose' | a | a
'experiment_name' | a | a
'results_dir' | a | a
'dataset' | a | a
'dataset_dir' | a | a
'network_type' | a | a
'problem_type' | a | a

### DSE Section:


### Cost Section:


### Parameters Section:


### RSM Section:


It should be noted that care should be taken when writing the \[Parameters\] and \[RSM\] sections of configuration files, as the parameter strings are executed by the Python interpreter. This ability was added for convenience when specifying parameters with many values to be explored; it is a given that the tool should not be run with root privileges.

## Dependencies

Aside from a working Python installation (3.4 or 3.5), the following libraries are required:
 - [numpy](http://www.numpy.org/)
 - [scipy](http://www.scipy.org/)
 - [matplotlib](http://matplotlib.org/)
 - [theano](http://www.deeplearning.net/software/theano/)
 - [lasagne](https://github.com/Lasagne/Lasagne)

The provided AMD64 builds have been tested on Ubuntu versions 14.04 and 16.04, with numpy 2.6.2, scipy 0.18.1, matplotlib 2.0.0, theano 0.9.0b1, and lasagne 0.2.dev1. However, the release may still function with earlier versions.

<!-- ## Frequently Asked Questions -->

