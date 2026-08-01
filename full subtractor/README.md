# Full Subtractor using Verilog

## Overview
This project implements a **1-bit Full Subtractor** in Verilog HDL.

A Full Subtractor subtracts three input bits:
- A (Minuend)
- B (Subtrahend)
- Bin (Borrow In)

It produces:
- Difference (D)
- Borrow Out (Bout)

## Truth Table

| A | B | Bin | Difference | Borrow |
|---|---|-----|------------|--------|
|0|0|0|0|0|
|0|0|1|1|1|
|0|1|0|1|1|
|0|1|1|0|1|
|1|0|0|1|0|
|1|0|1|0|0|
|1|1|0|0|0|
|1|1|1|1|1|

## Boolean Expressions

Difference = A ⊕ B ⊕ Bin

Borrow = (~A & B) | (~A & Bin) | (B & Bin)

## Files

- `src/full_subtractor.v` - Verilog design
- `tb/full_subtractor_tb.v` - Testbench
- `simulation/` - Waveform and output

## Software Used

- ModelSim
- Vivado
- Icarus Verilog
- GTKWave

## Simulation

Run using Icarus Verilog:

```bash
iverilog -o full_subtractor tb/full_subtractor_tb.v src/full_subtractor.v
vvp full_subtractor
gtkwave full_subtractor.vcd
```

