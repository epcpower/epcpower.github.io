## Sunspec Interface Quick-Start Guide

# Overview
EPC Power implements the Sunspec interface, which provides a mapping of various
parameter groupings referred to as models, onto Modbus holding registers.
Further documentation can be found at https://sunspec.org/
Presently, EPC implements the following models:
- Common (1)
- Serial (17)
- Inverter (103)
- EPC Vendor specific (65534)

# Getting Started

## Physical connection
TBD

## Serial interface settings
The RS-485 connection has the following default settings:
- Baudrate: 9600
- Drop Number (slave address) 1
- Monitor timeout: 20,000 ms
- Protocol: N81 (No parity, 8 data bits, 1 stop bit)
These settings can be modified via the Serial model, or via the CAN interface
with the EPyQ tool in the 'Parameters' tab under Communication->Serial.

## Modbus function codes
EPC supports the following function codes:
- Read Holding registers (3)
- Write Multiple registsers (16)

## Pysunspec demo script
Install python 3.x if you don't already have it.
Assuming you're on Windows, use the 32 bit version

download the pysunspec package
https://ci.appveyor.com/api/buildjobs/da3eo9j30a8ogop7/artifacts/dist%2Fpysunspec-1.1.0.dev2.post66-py2.py3-none-any.whl

install pysunspec via a command prompt (cmd.exe or powershell) in the
same directory as the downloaded .whl file
  py -3.6 -m pip install ./pysunspec-1.1.0.dev2.post66-py2.py3-none-
any.whl

download the latest demo script and smdx files
  https://github.com/altendky/st/archive/sunspec.zip

extract above .zip and open prompt into the extracted directory with the 
Pysunspec_demo.py file:
  py -3.7 .\Pysunspec_demo.py --serial-port COM3
  (use correct com port number for your system)

# Model documentation
TBD
