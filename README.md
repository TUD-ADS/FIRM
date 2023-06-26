# FIRM

The FPGA Interfaces for Robotics Middlewares (FIRM) Tool generated VHDL components to interface hardware accelerators with the Robot Operating System (ROS) middleware

## Overview

FIRM produces components to serialize (msg2axis) and deserialize (axis2msg) ROS messages from/to AXI Stream.

## Features

- Full ROS and ROS2 support
- Generation of hardware IPs in VHDL to interface hardware accelerators with ROS and ROS2 without modifying the interfaces of the accelerators, improving their reusability
- FIRM also provides native ROS nodes to generate a stimulus input for a VHDL simulation by populating the message to be tested with random data

## Usage

If you want to generate only the .vhd files, you have to specify the output path once.
In case you want to output the configuration file for the template engine, you have to specify its path as well. This is optional.

### Converters
#### axis2msg

`java -jar FIRM.jar axis2msg ROS_PACKAGE/ROS_MSG /VHDL_OUTPUT_PATH [/YAML_OUTPUT_PATH]`

Example: `java -jar FIRM.jar msg2axis sensor_msgs/Image /tmp/FIRM /tmp/FIRM`

#### msg2axis

`java -jar FIRM.jar msg2axis ROS_PACKAGE/ROS_MSG /VHDL_OUTPUT_PATH [/YAML_OUTPUT_PATH]`

### Stimulus

`java -jar FIRM.jar stimulus ROS_PACKAGE/ROS_MSG /VHDL_OUTPUT_PATH [/YAML_OUTPUT_PATH]`

### Different templates

FIRM comes with Hardware Description Templates (HDTs) based on VHDL for ROS and ROS2. If you want to use your own templates, you can include them as:
`java -jar FIRM.jar axis2msg -t /path/to/templates ROS_PACKAGE/ROS_MSG /VHDL_OUTPUT_PATH [/YAML_OUTPUT_PATH]`

Note: The definition of the ROS message is the same for ROS and ROS2 (e.g., sensor_msgs/Image)

## License

This tool is released under the GPLv3 license. See the [LICENSE](LICENSE) file for more information.

## References

If you use FIRM in your research work or commercial product, please consider citing it:

```bibtex
@article{podlubne2021model,
  title={Model-Based Approach for Automatic Generation of Hardware Architectures for Robotics},
  author={Podlubne, Ariel and Mey, Johannes and Sch{\"o}ne, Ren{\'e} and A{\ss}mann, Uwe and G{\"o}hringer, Diana},
  journal={IEEE Access},
  volume={9},
  pages={140921--140937},
  year={2021},
  publisher={IEEE},
  doi={https://doi.org/10.1109/ACCESS.2021.3119061}
}
