# CPU Module — MIPS 5-Stage Pipelined Processor

This folder contains the Verilog implementation of a **5-stage pipelined MIPS CPU** capable of executing a subset of MIPS instructions.

## CPU Pipeline Stages

1. **IF**: Instruction Fetch
2. **ID**: Instruction Decode & Register Fetch
3. **EX**: Execute (via ALU)
4. **MEM**: Memory Access (`lw`, `sw`)
5. **WB**: Write Back to Registers

## Supported Instructions

- **Data Transfer**: `lw`, `sw`
- **Arithmetic**: `add`, `addu`, `addi`, `addiu`, `sub`, `subu`
- **Logical**: `and`, `andi`, `or`, `ori`, `nor`, `xor`, `xori`
- **Shift**: `sll`, `sllv`, `srl`, `srlv`, `sra`, `srav`
- **Branch/Jump**: `beq`, `bne`, `slt`, `j`, `jr`, `jal`

## Execution Flow

- Separate **Instruction Memory** and **Data Memory** modules provided.
- CPU fetches instructions from `CPU_instruction.bin` and updates `data.bin` after execution.
- Program halts upon executing sentinel instruction `32'hffffffff`.

## Testing

Use provided test cases for validation. Run:

```bash
make test
```

Ensure `cpu.v` and `test_cpu.v` exist for proper compilation and simulation.
