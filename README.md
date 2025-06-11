# RISC-V Pipelined Processor Design

This project implements a modular 32-bit pipelined RISC-V processor using Verilog. The processor supports essential instruction types including R-type, I-type, memory access (`LW`, `SW`), and control flow (`BEQ`, `JAL`, `JALR`) instructions. The design features classic 5-stage pipelining and includes data forwarding and hazard handling mechanisms for correct and efficient execution.

## Features

- **5-stage Pipeline**:
  - Instruction Fetch (IF)
  - Instruction Decode (ID)
  - Execute (EX)
  - Memory Access (MEM)
  - Write Back (WB)
- **Supported Instructions**:
  - R-type: `ADD`, `SUB`, `AND`, `OR`, `XOR`, etc.
  - I-type: `ADDI`, `ANDI`, `ORI`, `LW`, etc.
  - S-type: `SW`
  - B-type: `BEQ`, `BNE`
  - J-type: `JAL`, `JALR`
- **Hazard Mitigation**:
  - Data hazard resolution via forwarding
  - Control hazard handling with flushing logic
- **Modular Design**:
  - Separate Verilog modules for ALU, Register File, Immediate Generator, Control Unit, and Pipeline Registers

## Getting Started

### Prerequisites

- Verilog simulator (e.g., [Icarus Verilog](http://iverilog.icarus.com/), ModelSim, etc.)
- GTKWave (optional, for waveform viewing)

### Build and Run

```bash
cd test
iverilog -o cpu_test ../src/*.v tb_Processor.v
vvp cpu_test
```

To view waveforms:
```bash
gtkwave dump.vcd
```
