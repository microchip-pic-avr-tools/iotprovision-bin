
# Changelog
Version numbers refer to the iotprovision version bundled in this binary. Other tools have their own version numbers.

## [2.10.7] - October 2022

### Added
- DSG-5399 Multi-tool support in binary release
- DSG-4701 Pysequans utility, to support upgrading Sequans Monarch 2 firmware, and storing custom certificates and private keys

### Changes
- DSG-5161 Moved device certificate storage in Sequans Monarch 2 platform from NVM storage slot 0 to 18, to be compliant with Sequans use of reserved NVM storage slots
- DSG-5078 Updated bundled debugger firmware
- DSG-5618, DSG-5624 Improved port auto-detection

## [2.8.2] - June 2022

### Added
- DSG-4818 support for AVR-IoT Cellular Mini kit

## [2.7.1] - April 2022

### Added
- DSG-4600 support for SAM-IoT provisioning

## [2.5.15] - December 2021

### Changes
- Full stack rebuild (v2)
- Improved reliability of provisioning firmware startup
- Improved and more consistent output (logging)
- Cloud provider argument is now mandatory (AWS is no longer default)
- Added Azure demo application (preliminary support: provisioning only)
- Updated bundled debugger firmware

## [1.4.3]

### Fixes
- Wildcard character correction in IoT Core policy creation
- Failure on MacOS (Catalina)
- Prevent re-generation of device certificate

## [1.4.0]

### Added
- provisioning to AWS custom account using MAR
- WINC FW upgrade
- Azure provisioning (preliminary/alpha)

## [1.1.11]

### Added
- provisioning to AWS custom account using JITR

## Initial release (v1.0.90)

### Support for
- provisioning AVR-IoT and PIC-IoT kits to the Microchip sandbox account on AWS
- provisioning AVR-IoT and PIC-IoT kits to the Microchip sandbox account on Google
