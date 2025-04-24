# MIPS Processor Test Suite

This folder contains a comprehensive set of 8 test programs designed to validate the correctness of the five-stage pipelined MIPS CPU implementation.

Each test includes:

- An assembly source file (`mipsX.asm`)
- The corresponding machine code (`machine_codeX.txt`)
- The expected data memory output (`DATA_RAMX.txt`) after execution

These tests incrementally cover a variety of MIPS instruction types and hazard handling scenarios.

## Test Descriptions

| Test File                             | Purpose                                                                                           |
| ------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `mips1.asm` / `machine_code1.txt` | **Basic Functionality Test** (no hazards). Verifies add, srl, and other basic instructions. |
| `mips2.asm` / `machine_code2.txt` | **Data Hazard Test (MEM→EX, WB→EX)**. Verifies bypassing paths.                           |
| `mips3.asm` / `machine_code3.txt` | **Load-Use Hazard Test**. Verifies correct insertion of stalls for `lw`.                  |
| `mips4.asm` / `machine_code4.txt` | **Simultaneous Register Read/Write Test**. Verifies register file access logic.             |
| `mips5.asm` / `machine_code5.txt` | **Branch Instruction Test**. Verifies `beq`, `bne` branching behavior.                  |
| `mips6.asm` / `machine_code6.txt` | **Jump Instruction Test**. Verifies `j`, `jal`, and `jr`.                             |
| `mips7.asm` / `machine_code7.txt` | **JR Hazard Test**. Verifies forwarding behavior when using `jr`.                         |
| `mips8.asm` / `machine_code8.txt` | **Branch Hazard Test**. Verifies forwarding behavior in branch-dependent paths.             |

## Program Termination

All programs terminate with the special instruction:

`32'hffffffff`

This is used as a sentinel value to stop execution in simulation.
