# GCD Computation Unit on FPGA

## Overview

This project implements a Greatest Common Divisor (GCD) Computation Unit using Verilog HDL and targets the Xilinx Spartan-7 FPGA. The design follows a classic VLSI architecture consisting of a Datapath and a Controller (Finite State Machine).

The GCD is computed using the subtraction-based Euclidean algorithm. The controller generates the required control signals, while the datapath performs arithmetic operations and stores intermediate values.

---

## Features

* Verilog HDL implementation
* Datapath and Controller architecture
* Finite State Machine (FSM) based control
* Vivado simulation and synthesis
* FPGA implementation on Spartan-7
* Resource utilization analysis
* Complete testbench verification

---

## Architecture

The design consists of:

### Datapath

* Input registers A and B
* Comparator logic
* Subtraction unit
* GCD output register

### Controller

* FSM-based controller
* Generates:

  * load
  * sub_a
  * sub_b
  * capture

### Top Module

* Integrates datapath and controller
* Connects status and control signals

---

## FSM States

| State   | Description            |
| ------- | ---------------------- |
| IDLE    | Waits for start signal |
| LOAD    | Loads input operands   |
| COMPARE | Compares A and B       |
| SUB_A   | Computes A ← A − B     |
| SUB_B   | Computes B ← B − A     |
| DONE    | Outputs GCD result     |
| ERROR   | Handles invalid input  |

---

## Simulation Results

The design was verified using a dedicated testbench in Vivado.

| A   | B  | GCD |
| --- | -- | --- |
| 48  | 18 | 6   |
| 100 | 75 | 25  |
| 255 | 85 | 85  |
| 12  | 8  | 4   |
| 7   | 3  | 1   |
| 9   | 9  | 9   |
| 8   | 0  | 8   |
| 0   | 18 | 18  |

All test cases produced the expected GCD values.

---

## Resource Utilization

| Resource        | Used | Utilization |
| --------------- | ---- | ----------- |
| Slice LUTs      | 38   | 0.12%       |
| Slice Registers | 32   | 0.05%       |
| Slices          | 14   | 0.17%       |
| Bonded IOBs     | 31   | 14.76%      |
| BUFGCTRL        | 1    | 3.13%       |

---

## Tools Used

* Verilog HDL
* Xilinx Vivado
* Spartan-7 FPGA
* XDC Constraints

---

## Author

Reddy Bhargavi Chenga

Electronics and Communication Engineering

National Institute of Technology Durgapur

