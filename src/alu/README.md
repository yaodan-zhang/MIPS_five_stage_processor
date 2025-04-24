# ALU Module — MIPS Pipelined CPU Project

This folder contains the implementation of the **Arithmetic and Logic Unit (ALU)** for a five-stage pipelined MIPS CPU, written in Verilog.

## Overview

The ALU performs core arithmetic, logical, shift, and comparison operations based on parsed MIPS instructions. It receives opcode and register inputs, computes results, and outputs status flags for further CPU pipeline control.

## Features

- Supports key MIPS instructions:

  - **Arithmetic**: `add`, `addi`, `addu`, `addiu`, `sub`, `subu`
  - **Logical**: `and`, `andi`, `or`, `ori`, `nor`, `xor`, `xori`
  - **Shift**: `sll`, `sllv`, `srl`, `srlv`, `sra`, `srav`
  - **Comparison & Branch**: `beq`, `bne`, `slt`, `slti`, `sltiu`, `sltu`
  - **Memory**: `lw`, `sw`
- Outputs:

  - `result` (32-bit computation result)
  - `flags` (3-bit: zero, negative, overflow)
- Handles simplified register fetching (2-register setup for testing).

## Module Interface

```verilog
module alu(
  input [31:0] instruction,
  input [31:0] regA,
  input [31:0] regB,
  output [31:0] result,
  output [2:0] flags  // {zero, negative, overflow}
);
```

## Flag Handling Notes

* **Overflow flag** : Set for `add`, `addi`, `sub`.
* **Zero flag** : Set for `beq`, `bne`.
* **Negative flag** : Set for `slt`, `slti`, `sltiu`, `sltu`.

## Testing

Run the following inside `/src/alu`:

`make test`

Ensure `alu.v` and `test_alu.v` are present for compilation and testing.
