[![MCHP](images/microchip.png)](https://www.microchip.com)

# IoT Provisioning Tool binary releases
Easy-to-use solution for configuring an AVR-IoT, PIC-IoT or SAM-IoT board to connect to Amazon Web Services (AWS), Google IoT Core Platforms and Microsoft Azure

Supported kits:
- AVR-IoT Wx
- PIC-IoT Wx
- SAM-IoT WG
- AVR-IoT Cellular Mini

## Download
Download the [latest release](https://github.com/microchip-pic-avr-tools/iotprovision-bin/releases/latest) and extract the binary from the zip file.

## Getting Started and Documentation

The zip file contains command-line executables for Windows®, macOS®, and Linux® operating systems bundled with all the firmware needed to complete the provisioning. Extract and use the command-line utility corresponding to your operating system. You will find more instructions for running the tool in iotprovision.md in the root folder.

### CLI usage
Getting help:
```
iotprovision --help
```
Provision for Amazon Web Services, using Microchip sandbox account:
```
iotprovision -c aws -m sandbox
```
Provision for Amazon Web Services, using MAR and custom account:
```
iotprovision -c aws -m mar
```
Provision for Amazon Web Services, using JITR and custom account:
```
iotprovision -c aws -m jitr
```
Provision for Google Cloud Platform, using Microchip sandbox account:
```
iotprovision -c google -m sandbox
```
Provision for Microsoft Azure (preliminary - only kit provisioning):
```
iotprovision -c azure
```
The amount of logging is controlled by the -v/--verbose option:
Possible log levels are `debug`, `info`, `warning`, `error`, `critical`.  Default is `info`.
```
iotprovision -v debug
```
Print version info and exit:
```
iotprovision -V
```
Print release info and exit:
```
iotprovision -R
```

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

## Release v2.8.5
This release is in sync with pypi release 2.8.5.191

Changes:
- updated Amazon root CA bundle (in pyawsutils)

## Release v2.8.3

Added:
- support for AVR-IoT Cellular Mini kit

## Release v2.7.1

Added:
- support for SAM-IoT provisioning

## Release v2.5.15

Changes:
- Full stack rebuild (v2)
- Improved reliability of provisioning firmware startup
- Improved and more consistent output (logging)
- Cloud provider argument is now mandatory (AWS is no longer default)
- Added Azure demo application (preliminary support: provisioning only)
- Updated bundled debugger firmware

## Release v1.4.3

Fixes:
- Wildcard character correction in IoT Core policy creation
- Failure on MacOS (Catalina)
- Prevent re-generation of device certificate

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
