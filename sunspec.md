## Sunspec Interface Quick-Start Guide

# Overview
EPC Power implements the Sunspec interface, which provides a mapping of various
parameter groupings referred to as models, onto Modbus holding registers.
Further documentation can be found at [https://sunspec.org/](https://sunspec.org/).
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
- Write Multiple registers (16)

## Sunspec header
The start of a Sunspec interface is denoted by the ascii characters 'SunS' (0x53 0x75 0x6E 0x53.)  The EPC model starts at holding register 0.  To confirm proper comms setup, make sure that these characters are received when reading the first two holding holding registers starting at address 0.

## Pysunspec demo script
1. Install python 3.x if you don't already have it. 
2. Create a directory in which to install pysunspec.
3. Follow the instructions [here](https://github.com/epcpower/sunspec-demo) to setup and run a demo that will run EPC inverters via the Sunspec interface.

## Other useful debugging tools
- QModbus is an open-source, cross-platform Modbus RTU and TCP master/client with an easy to use GUI.  The latest release is available on [Github](https://github.com/ed-chemnitz/qmodbus/releases).
- [MinimalModbus](https://minimalmodbus.readthedocs.io/en/master/) is a command-line tool for Modbus RTU.
- [Wireshark](https://www.wireshark.org/) is an open-source, cross-platform network analyzer that can log, filter and parse Modbus TCP traffic.
- [IO Ninja](http://ioninja.com/downloads.html) is a cross-platform network monitor and sniffer that can capture both Modbus RTU and Modbus TCP traffic.  A free evaluation version is available for download.  [Here is a video](https://www.youtube.com/watch?v=i5TitGHQtjg) demonstrating how to setup the Modbus RTU analyzer functionality in IO Ninja.
# Model documentation
Please refer to the Sunspec information Model Reference spreadsheet (named MODBUS_Sunspec-EPC.xls or similar) in the directory matching your [software release](https://github.com/epcpower/epcpower.github.io/tree/master/release_artifacts)
