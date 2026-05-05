# LF111x - Building a RISC-V CPU Core (Linux Foundation / edX)
Completed a guided implementation of a single-cycle RV32I CPU core in TL-Verilog using the Makerchip IDE. 
Implemented instruction fetch, decode, ALU, register file, branch logic, and load/store memory access at the register level.

I noticed this course in the YouTube video "RISC-V 2026 Update" by ExplainComputer where the interviewed RISC-V International CEO Andrea Gallo
suggested it. Since I'm interested in RISC-V and I'm not really experienced in any assembly I thought it was a good occasion to catch two
birds with one stone.


## What it does

Two test programs were run against the core:

1. The course's **sum 1..9** loop, which exercises immediate arithmetic, branches
   and the loop-back jump. Pass condition: `x14 = 45` and `x30 = 1` at halt.
2. A broader **instruction-by-instruction self-test** via `m4_test_prog()` from
   the course library

   
## Implemented instructions

| Class      | Instructions |
|------------|--------------|
| Imm. ALU   | `ADDI`, `ANDI`, `ORI`, `XORI`, `SLLI`, `SRLI`, `SRAI`, `SLTI`, `SLTIU` |
| Reg. ALU   | `ADD`, `SUB`, `AND`, `OR`, `XOR`, `SLL`, `SRL`, `SRA`, `SLT`, `SLTU` |
| Upper imm. | `LUI`, `AUIPC` |
| Branch     | `BEQ`, `BNE`, `BLT`, `BGE`, `BLTU`, `BGEU` |
| Jump       | `JAL`, `JALR` |
| Memory     | `LW` (load) and `SW` (store path through dmem) |


<img width="591" height="593" alt="Screenshot 2026-05-05 at 14 38 27" src="https://github.com/user-attachments/assets/1573c04a-ccd3-45a5-bf2c-a3273da474f4" />
<img width="568" height="701" alt="Screenshot 2026-05-05 at 14 38 45" src="https://github.com/user-attachments/assets/036f3be3-0493-4688-918c-a29ea2c9beb9" />
