# 1×2 Demultiplexer Using Verilog

## Project Overview

This project implements a **1×2 Demultiplexer (DEMUX)** using Verilog HDL.

A 1×2 Demultiplexer is a combinational logic circuit that has:

* **1 data input**
* **1 select line**
* **2 outputs**

The select line determines which output receives the input data.

## Inputs and Outputs

### Inputs

* `D` – Data input
* `S` – Select line

### Outputs

* `Y0` – Output 0
* `Y1` – Output 1

## Block Diagram

```text
                    ┌──────────────┐
             D ────►│              │───► Y0
                    │    1 × 2     │
             S ────►│    DEMUX     │───► Y1
                    │              │
                    └──────────────┘
```

## Truth Table

| S | D | Y0 | Y1 |
| - | - | -- | -- |
| 0 | 0 | 0  | 0  |
| 0 | 1 | 1  | 0  |
| 1 | 0 | 0  | 0  |
| 1 | 1 | 0  | 1  |

## Logic Equations

```text
Y0 = D & ~S
Y1 = D & S
```

## Working Principle

* When `S = 0`, the input `D` is connected to `Y0`.
* When `S = 1`, the input `D` is connected to `Y1`.
* When `D = 0`, both outputs remain `0`.

## Project Files

```text
1x2-demultiplexer/
├── README.md
├── demux_1x2.v
├── demux_1x2_tb.v
└── output/
    └── simulation_output.txt
```

### Files Description

* `demux_1x2.v` – Verilog design code
* `demux_1x2_tb.v` – Verilog testbench
* `output/simulation_output.txt` – Simulation output

## How to Run

Using Icarus Verilog:

```bash
iverilog -o demux_sim demux_1x2.v demux_1x2_tb.v
```

Run the simulation:

```bash
vvp demux_sim
```

## Applications

1×2 Demultiplexers are used in:

* Data routing
* Data distribution
* Digital communication
* Control systems
* Digital logic circuits
* Memory selection

## Conclusion

The 1×2 Demultiplexer successfully routes a single input signal to one of two outputs depending on the select line.

The Verilog design is verified using a testbench that checks all possible combinations of the input and select signals.

## Author

**Verilog HDL Digital Logic Project**
