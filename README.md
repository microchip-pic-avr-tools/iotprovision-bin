[![MCHP](images/microchip.png)](https://www.microchip.com)

# IoT Provisioning Tool binary releases
Easy-to-use solution for configuring an AVR-IoT or PIC-IoT board to connect to Amazon Web Services (AWS) and Google IoT Core Platforms

Supported kits:
- AVR-IOT Wx
- PIC-IOT Wx

## Download
Download the [latest release](https://github.com/microchip-pic-avr-tools/iotprovision-bin/releases/latest) and extract the binary from the zip file.

## Getting Started and Documentation

The zip file contains command-line executables for Windows®, macOS®, and Linux® operating systems bundled with all the firmware needed to complete the provisioning. Extract and use the command-line utility corresponding to your operating system. You will find more instructions for running the tool in iotprovision.md found in the root folder.

### Other Helpful Resources

[Switch Cloud Providers with the IoT Provisioning Tool (Video)](https://www.youtube.com/watch?v=nwP8obSRaaE)

[Connect to Your Private AWS Account with IoT Provisioning Tool (GitHub Tutorial)](https://github.com/microchip-pic-avr-solutions/microchip-iot-developer-guides-for-aws/tree/master/connect-the-board-to-your-aws-account)

[How the IoT Provisioning Tool Works - AWS JITR (GitHub Tutorial)](https://github.com/microchip-pic-avr-solutions/microchip-iot-developer-guides-for-aws/tree/master/a-more-thorough-look-into-the-provisioning-process)

## Python wheel
The binaries here are generated from Python source.  If you are more comfortable using Python the iotprovision wheel can be installed from the Python package index pypi.org

```
pip install iotprovision
```

PyPi project: [pypi.org/project/iotprovision](https://pypi.org/project/iotprovision/)


# Release notes

## Release v1.4.0

Added:
- provisioning to AWS custom account using MAR
- WINC FW upgrade
- Azure provisioning (preliminary/alpha)

## Release v1.1.11

Added:
- provisioning to AWS custom account using JITR

## Initial release (v1.0.90)

Support for:
- provisioning AVR-IoT and PIC-IoT kits to the Microchip sandbox account on AWS
- provisioning AVR-IoT and PIC-IoT kits to the Microchip sandbox account on Google
