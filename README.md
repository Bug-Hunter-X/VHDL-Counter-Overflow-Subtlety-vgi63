# VHDL Counter: A Subtle Overflow Issue
This repository demonstrates a subtle potential overflow issue in a simple VHDL counter.  While the code seems functionally correct, it might lead to unpredictable results depending on the synthesis tool and its optimizations.

## The Bug
The `buggy_counter.vhdl` file contains the flawed counter implementation. The issue lies in the potential for unexpected behavior if the counter is not properly synchronized with the clock, especially during reset or at very high clock frequencies. Certain synthesis tools may interpret the code differently, resulting in incorrect counting sequences or even unpredictable output.

## The Solution
The `buggy_counter_fixed.vhdl` file offers an improved version.  This solution improves the robustness by explicitly handling the potential race conditions during reset and ensuring that the counter's state is updated atomically.  This is a far more robust implementation in the face of potentially complex synthesis tools.

## Running the Code
To test the code, you'll need a VHDL simulator (like ModelSim or GHDL) and a synthesis tool (like Xilinx Vivado or Intel Quartus). Simulate both the buggy and fixed versions to observe the difference in behavior.  Synthesis will highlight potential timing issues that might not be apparent during simulation.
