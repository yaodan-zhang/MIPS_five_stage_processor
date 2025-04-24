# Memory Modules — MIPS Pipelined CPU

This folder contains Verilog implementations of the memory components used in the MIPS five-stage pipelined processor.

## Files

- `InstructionRAM.v`Simulates the instruction memory (ROM). It loads precompiled machine code (`CPU_instruction.bin`) and provides instructions to the CPU during the **IF (Instruction Fetch)** stage.
- `MainMemory.v`
  Simulates data memory (RAM) for `lw` and `sw` instructions, supporting word-addressable read and write operations. After program execution, the memory state is saved to `data.bin` for verification.

## Usage

Both modules are instantiated within the top-level CPU module (`cpu.v`) and interact seamlessly with pipeline stages.

Ensure:

- `CPU_instruction.bin` is present in the working directory before simulation.
- Output `data.bin` is compared against expected results in `/test/cpu_test/`.
