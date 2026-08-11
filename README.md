MIPS CPU
========
An implementation of a MIPS I (Revision 3.2) CPU core, written in Verilog. The
project originated as coursework for the instruction set architecture (ISA)
module at Imperial College London and has since been shared here for reference
and reuse. All Verilog files adhere to the subset of SystemVerilog 2012
supported by Icarus Verilog 11.0.

DOCS
----
Contains the original project specification and a report detailing the CPU's
design and implementation, providing a thorough outline of how it functions.

RTL
---
Contains the Verilog source files for synthesizing the MIPS CPU core, along
with a handful of intermediary scripts used during development and testing.

TEST
----
Contains everything needed to verify the functional correctness of the CPU
(or any other MIPS I Revision 3.2 ISA-compliant CPU). Each test case has a
unique identifier of the form `opcode_ID`, where `ID` is an integer.

Four scripts live in the repository's base directory.
*Note: all scripts are intended to be run from the base directory of the repository.*

**test_mips_cpu_bus.sh**

Usage: `bash test/test_mips_cpu_bus.sh $SOURCE_DIRECTORY $INSTRUCTION_OPCODE(optional)`

This script (when called without the second parameter) performs an overall functional
analysis of the CPU found in the `$SOURCE_DIRECTORY` (*Note: will include all files prefixed
with mips_cpu_bus in compilation*). When run successfully any temporary files created
by the script will be automatically removed.

**run_testbench_code**

Usage: `bash test/run_testbench_code.sh $SOURCE_DIRECTORY $TESTBENCH_CODE`

This script will run a single testcase specified by the `$TESTBENCH CODE` parameter.

**run_testbench_instr**

Usage: `bash test/run_testbench_code.sh $SOURCE_DIRECTORY $INSTRUCTION_OPCODE`

This script will run all testcases associated with a particular instruction.
(*Note: test_mips_cpu_bus.sh can also be used to run tests on particular instructions*)

**cleanup.sh**

Usage: `bash test/cleanup.sh`

This script will remove any files created by any of the previous testing scripts.
