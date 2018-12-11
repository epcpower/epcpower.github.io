## Sunspec Interface Quick-Start Guide

# Overview
EPC Power implements the Sunspec interface, which provides a mapping of various
parameter groupings referred to as models, onto Modbus holding registers.
Further documentation can be found at [https://sunspec.org/](https://sunspec.org/)
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

## Sunspec header
The start of a Sunspec interface is denoted by the ascii characters 'SunS' (0x53 0x75 0x6E 0x53.)  The EPC model starts at holding register 0.  To confirm proper comms setup, make sure that these characters are received when reading the first two holding holding registers starting at address 0.

## Pysunspec demo script
1. Install python 3.x if you don't already have it. 
2. Create a directory in which to install pysunspec.
3. Download the [pysunspec package](https://ci.appveyor.com/api/buildjobs/da3eo9j30a8ogop7/artifacts/dist%2Fpysunspec-1.1.0.dev2.post66-py2.py3-none-any.whl) into the directory you created in step 2.
4. Download the latest demo script and [smdx files](https://github.com/altendky/st/archive/sunspec.zip) and copy them into the directory you created in step 2.
5. In the same directory, create a virtual environment using the following command: `python -m venv env`
This will create a directory named env in which you can install pysunspec and all of its dependencies.
6. In the same directory, install pysunspec via a command prompt (cmd.exe, powershell, bash etc)
- On Windows: `.\env\Scripts\python -m pip install .\pysunspec-1.1.0.dev2.post66-py2.py3-none-any.whl`
- On Mac, Linux, or Unix: `env/bin/python -m pip install pysunspec-1.1.0.dev2.post66-py2.py3-none-any.whl`
7. Run the demo script with the following command:
- On Windows: `.\env\Scripts\python .\Pysunspec_demo.py --invert-hw-enable --serial-port COM3`
- On Mac, Linux, or Unix: `/env/bin\python Pysunspec_demo.py --invert-hw-enable --serial-port /dev/ttyUSB0`
(use correct serial port number for your system)

# Model documentation
TBD
