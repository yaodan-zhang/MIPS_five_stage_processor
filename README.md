
# MIPS Five-Stage Pipelined Processor

This project implements a **five-stage pipelined MIPS CPU** using Verilog, designed to simulate core functionalities of a MIPS processor including arithmetic, logic, memory access, branching, and hazard handling.

Developed as part of a computer architecture course, this CPU adheres to standard MIPS pipeline architecture: **IF → ID → EX → MEM → WB**.

## Features

- Implements key MIPS instructions:
  - **Arithmetic & Logic**: `add`, `addi`, `sub`, `and`, `or`, `nor`, `xor`, `sll`, `srl`, `sra`, etc.
  - **Memory Access**: `lw`, `sw`
  - **Branch & Jump**: `beq`, `bne`, `j`, `jr`, `jal`
  - **Comparison**: `slt`, `slti`, etc.
- Basic hazard detection and forwarding implemented.
- Separate **Instruction Memory** and **Data Memory** modules.
- Automatic termination on `32'hffffffff` sentinel instruction.
- Comprehensive test suite covering instruction execution, hazard handling, and control flow.

## Project Structure

```
MIPS_five_stage_processor/
├── src/           # Verilog source code (CPU, ALU, Memory, Control)
├── test/          # Assembly tests, machine code, expected outputs
├── bin/           # Compiled binaries (instruction & data memory files)
├── docs/          # Project report and specifications
├── Makefile       # Build and simulation automation
└── README.md
```

## How to Build & Run

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yaodan-zhang/MIPS_five_stage_processor.git
   cd MIPS_five_stage_processor
   ```
2. **Run Tests**
   Navigate to the desired module or CPU directory and execute:

   ```
   make test
   ```
3. **Simulate CPU Execution**
   The CPU reads from `CPU_instruction.bin` and writes results to `data.bin`. Compare output with expected `DATA_RAMX.txt` files in `/test/cpu_test/`.

## Test Suite

* Located in `/test/cpu_test/`, the suite includes 8 targeted programs verifying:
  * Basic instruction correctness
  * Data and control hazard handling
  * Branching and jumping logic
  * Register file behavior

Programs halt upon encountering `32'hffffffff`.

## Notes

* Addressing uses **word units** ; manual conversion from byte to word addressing is required when preparing memory files.
* Hazard handling is implemented at a basic level per course requirements.
* Developed and tested using Icarus Verilog.

## Documentation

Detailed design decisions, pipeline diagrams, and hazard mitigation strategies are documented in `/docs/report.pdf`.

## License

This project is for educational purposes.
