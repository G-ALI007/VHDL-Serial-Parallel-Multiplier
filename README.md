# VHDL Serial-Parallel Multiplier

## Overview
This repository contains a structural VHDL implementation of a 4-bit Serial-Parallel Multiplier. [cite_start]The top-level entity, `sp_multiplier`, takes two 4-bit input vectors (`a` and `b`) and computes an 8-bit product (`prod`) using a clock-driven pipeline[cite: 6, 7].

## System Architecture
[cite_start]The design utilizes a structural architecture approach, instantiating several lower-level modules to perform the multiplication process[cite: 7]. The core components included in this project are:

* [cite_start]**`sp_multiplier`:** The top-level entity integrating all sub-components to generate the 8-bit product and a `data_ready` signal.
* [cite_start]**`pipe`:** A pipelined computational unit that combines a full adder with registers to hold the sum and carry bits[cite: 16, 17].
* **`full_adder`:** A gate-level implementation of a standard full adder using XOR, AND, and OR logic gates to produce the sum and carry-out (`cout`)[cite: 4, 5].
* **`shiftReg`:** A parameterized shift register with a generic max width (defaulting to 8 bits) that shifts data continuously on the clock's rising edge when enabled[cite: 19, 21].
* [cite_start]**`reg`:** A basic D flip-flop register that synchronizes data (`d`) to the output (`q`) on the rising edge of the clock signal (`clk`), equipped with an asynchronous reset (`rst`)[cite: 1, 2].

## Getting Started

### Prerequisites
To simulate and synthesize the VHDL files in this repository, you will need an EDA tool such as:
* ModelSim / QuestaSim
* Intel Quartus Prime
* Xilinx Vivado

### Usage
1. Clone the repository to your local machine:
   ```bash
   git clone [https://github.com/G-ALI007/VHDL-Serial-Parallel-Multiplier.git](https://github.com/G-ALI007/VHDL-Serial-Parallel-Multiplier.git)
Import the VHDL files into your preferred simulation tool.

Ensure all components are compiled in the correct order (bottom-up), starting with the basic gates (dff.txt, fulladder.txt) before compiling the top-level structural entity (mult.txt).

Run a testbench to verify the multiplication outputs.
