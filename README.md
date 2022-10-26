[![MCHP](images/microchip.png)](https://www.microchip.com)

# IoT Provisioning Tool binary releases
Easy-to-use solution for configuring an AVR-IoT, PIC-IoT, SAM-IoT or AVR-IoT Cellular Mini board to connect to Amazon Web Services (AWS), Google IoT Core Platforms and Microsoft Azure

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
iotprovision-bin --help
```
Provision for Amazon Web Services, using Microchip sandbox account:
```
iotprovision-bin -c aws -m sandbox
```
Provision for Amazon Web Services, using MAR and custom account:
```
iotprovision-bin -c aws -m mar
```
Provision for Amazon Web Services, using JITR and custom account:
```
iotprovision-bin -c aws -m jitr
```
Provision for Google Cloud Platform, using Microchip sandbox account:
```
iotprovision-bin -c google -m sandbox
```
Provision for Microsoft Azure (preliminary - only kit provisioning):
```
iotprovision-bin -c azure
```
The amount of logging is controlled by the -v/--verbose option:
Possible log levels are `debug`, `info`, `warning`, `error`, `critical`.  Default is `info`.
```
iotprovision-bin -v debug
```
Print version info and exit:
```
iotprovision-bin -V
```
Print release info and exit:
```
iotprovision-bin -R
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

## Other uses of the binary distribution

When installing the iotprovision Python wheel as described in the previous section, all its dependencies will also be installed automatically. This includes other useful CLI programs like pymcuprog, pytrust, pysequans, etc. These will be directly available from the command line.

When installing the iotprovision-bin binary, this does not seem to be the case. However, all these resources are actually present inside the binary, and starting with the iotprovision 2.10 release, they can be accessed in various ways, which are described below. The out-of-the-box behaviour of the binary named iotprovision-bin is to work exactly the same as the iotprovision Python wheel. This behaviour is referred to as the `iotprovision skin` of the binary. The remainder of this section describes ways of changing to other skins, to get access to other tools.

Whenever the following subsections refer to renaming the executable file, the same effect can be accomplished by creating a symbolic link to the original file, or copying it. Shell aliases (Mac/Linux) will not work for this purpose.

### The mcu8tools skin

This is the preferred skin for users wanting to use multiple tools frequently. It transforms the binary into a tool with all the bundled tools directly available as subcommands. To enable this, rename `iotprovision-bin[.exe]` to `mcu8tools[.exe]`. Invoking `mcu8tools` without arguments will list all the available subcommands. In this configuration, in order to use iotprovision to provision for AWS sandbox, you can do:
```
mcu8tools iotprovision -c aws -m sandbox
```
and to get help for our pymcuprog tool:
```
mcu8tools pymcuprog --help
```

### Single-tool skins

iotprovision-bin is an example of a single-tool skin. The binary can be reconfigured to all of the included tools by means of renaming it to the desired tool. For example, renaming it to `pymcuprog[.exe]` will cause it to behave like the pymcuprog Python wheel.

### One-shot skin change

If you only occasionally need to use a different tool, all single-tool configurations of the binary can be invoked with the `--skin` option to change skin temporarily, without need for renaming. This option must be the first argument present in the command line. Also note that this option can not be used to change neither to nor from the `mcu8tools` skin.

Example: User of iotprovision-bin needs to upgrade AVR-IoT Cellular Mini kit Sequans Monarch 2 firmware:
```
iotprovision-bin --skin=pysequans upgrade full
```

### List of available tools
As of release 2.10, these tools are available as installed packages when iotprovsion Python wheel is installed, and as subcommands/skins in the binary release:

- [pykitinfo](https://github.com/microchip-pic-avr-tools/pykitinfo) - List information about connected Microchip kits
- [pymcuprog](https://github.com/microchip-pic-avr-tools/pymcuprog) - MCU programming tool for selected AVR, PIC and SAM devices
- [pydebuggerupgrade](https://pypi.org/project/pydebuggerupgrade/) - Firmware upgrade utility for tools with DFU bootloader
- [pydebuggerconfig](https://pypi.org/project/pydebuggerconfig/) - Access PKOB nano on-board debugger configuration
- [pytrust](https://github.com/microchip-pic-avr-tools/pytrustplatform) - Command line interface for Microchip pytrustplatform
- [pyawsutils](https://github.com/microchip-pic-avr-tools/pyawsutils) - AWS account management for IoT kits
- [pyazureutils](https://github.com/microchip-pic-avr-tools/pyazureutils) - Azure account management for IoT kits
- [pywinc](https://github.com/microchip-pic-avr-tools/iotprovision) - WINC firmware upgrader and utilities for WiFi IoT kits (part of iotprovision package)
- [pysequans](https://pypi.org/project/pysequansutils/) - Firmware upgrader and utilities for the Sequans Monarch 2 platform in cellular kits
- [iotprovision](https://github.com/microchip-pic-avr-tools/iotprovision) - Provisioning tool for IoT kits
- [pyserial-miniterm](https://github.com/pyserial/pyserial) - Simple terminal program, from pyserial package

## Known issues
-  -a AWS_PROFILE, --aws-profile AWS_PROFILE argument does not work, i.e. only the default profile works (DSG-5722 and DSG-5724)
- Firmware upgrades for subsystems WINC, debugger, and Sequans Monarch 2 platform are handled inconsistently. WINC and debugger firmware will not be checked for upgrades unless explicitly requested by user, using arguments `wincupgrade` and `debuggerupgrade`, respectively, in which case firmware will be upgraded automatically. On the other hand, Sequans Monarch 2 firmware will be checked automatically by default, and user will be advised how to do the upgrade if needed. (DSG-5726)
