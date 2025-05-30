 VSDSquadron Research Internship 2025

## Overview

The **VSDSquadron Research Internship 2025** focuses on **RISC-V architecture** and **open-source VLSI design**. The program provides hands-on experience in **chip design** using industry-standard open-source tools. The internship is led by **Kunal Ghosh Sir** and aims to bridge the gap between academia and industry in **VLSI and RISC-V**.

## Internship Details
- **Intern:** CHANDRAKIRAN G  
- **College:** St. Joseph's Institute Of Technology  
- **Email:** [gchandrakiran97@gmail.com](mailto:gchandrakiran97@gmail.com)  
- **GitHub Profile:** [Kiran-VLSI](https://github.com/Kiran-VLSI)  
- **LinkedIn Profile:** [Chandrakiran G](https://www.linkedin.com/in/chandrakiran-g-409816257)  

## Task 1: Tool Installation

The first task is to install all the essential tools required for the internship:
1. **Ubuntu on VirtualBox** – Setting up a Linux environment for development.
2. **GNU Toolchain** – Compiler and assembler for RISC-V development.
3. **GTKWave** – Waveform viewer for debugging simulations.
4. **Yosys** – Open-source synthesis tool for digital circuits.
5. **iVerilog Simulator** – Verilog simulation tool for functional verification.

---

## Table of Contents

1. [Install Ubuntu 20.04 LTS on VirtualBox](#install-ubuntu-2004-lts-on-virtualbox)
2. [Install RISC-V GNU Toolchain](#install-risc-v-gnu-toolchain)
    1. [Clone the Repository](#clone-the-repository)
    2. [Install Dependencies](#install-dependencies)
    3. [Configure and Build Toolchain](#configure-and-build-toolchain)
    4. [Update PATH Variable](#update-path-variable)
    5. [Verify Installation](#verify-installation)
3. [Install Additional Tools](#install-additional-tools)
    1. [GTKWave](#gtkwave)
    2. [Yosys](#yosys)
    3. [iVerilog](#iverilog)
4. [Conclusion](#conclusion)

---

## Install Ubuntu 20.04 LTS on VirtualBox

Follow the steps below to install Ubuntu 20.04 LTS inside a Virtual Machine using Oracle VirtualBox:

### Step 1: Install Oracle VM VirtualBox
- **Download VirtualBox** from [here](https://www.virtualbox.org/).
- **Download Ubuntu 20.04 LTS ISO** from [here](https://releases.ubuntu.com/20.04/).

### Step 2: Set Up Virtual Machine
- Open **VirtualBox** and create a new virtual machine.
- Select **Ubuntu (64-bit)** as the OS type.
- Allocate appropriate memory (2 GB or more recommended) and create a virtual hard disk (20 GB or more).

### Step 3: Install Ubuntu
- Start the VM and choose the downloaded **Ubuntu ISO** as the installation medium.
- Follow the on-screen instructions to complete the Ubuntu installation.

Once Ubuntu is installed, you can proceed to the next steps.

---

## Install RISC-V GNU Toolchain

The RISC-V GNU Toolchain is a free and open-source cross-compiler for creating assembly and machine code for the RISC-V architecture.

### Clone the Repository

1. **Open a terminal** in Ubuntu.
2. Clone the toolchain repository:

```bash
git clone https://github.com/riscv/riscv-gnu-toolchain.git
```

### Install Dependencies

Run the following command to install the necessary dependencies:

```bash
sudo apt-get install autoconf automake autotools-dev curl python3 python3-pip libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev ninja-build git cmake libglib2.0-dev libslirp-dev
```

### Configure and Build Toolchain

1. Create a directory for installing the RISC-V toolchain:

```bash
sudo mkdir /opt/riscv
```

2. Navigate to the `riscv-gnu-toolchain` directory:

```bash
cd riscv-gnu-toolchain
```

3. Configure the toolchain:

```bash
./configure --prefix=/opt/riscv --with-arch=rv64i --with-abi=lp64 --enable-multilib
```

4. Build the toolchain:

```bash
sudo make
```

### Update PATH Variable

After the build is completed, add the toolchain to the system PATH:

1. Open the `.bashrc` file:

```bash
gedit ~/.bashrc
```

2. Add the following line at the end of the file:

```bash
export PATH="$PATH:/opt/riscv/bin"
```

3. Save and close the file, then run the following command to apply the changes:

```bash
source ~/.bashrc
```

### Verify Installation

To verify that the toolchain is installed correctly, run:

```bash
riscv64-unknown-elf-gcc --version
```

If installed correctly, this should display the version of the RISC-V GCC compiler.

---

## Install Additional Tools

These tools are also required for simulation and synthesis:

### GTKWave

GTKWave is a waveform viewer for digital simulation outputs.

bash
sudo apt-get install gtkwave


### Yosys

Yosys is an open-source RTL synthesis tool.

bash
sudo apt-get install yosys


### iVerilog

iVerilog is a Verilog simulator used for compiling and simulating Verilog designs.

bash
sudo apt-get install iverilog

### Task 4: Task is to identify instruction type of all the given instructions with its exact 32 bits instruction code in the desired instruction type format
###🧠 RISC-V Instruction Formats

This repository provides a complete reference for the six fundamental **RISC-V instruction formats** used in the RV32I base ISA. It’s designed to help students, engineers, and VLSI/Computer Architecture enthusiasts understand how each instruction type works at the bit level.

---

## 📘 About RISC-V

**RISC-V** (Reduced Instruction Set Computer - Five) is a free, open-source Instruction Set Architecture (ISA) designed for simplicity, modularity, and scalability. It supports a wide range of applications — from embedded systems to high-performance computing — and is ideal for academic research, industry, and open hardware projects.

---

## 📦 Instruction Format Overview

Each instruction in RISC-V (RV32I) is **32 bits long** and conforms to one of six formats:

| Format | Description                      | Used For                                  | Registers       | Immediate Type |
|--------|----------------------------------|-------------------------------------------|------------------|----------------|
| R-type | Register operations              | Arithmetic, logic, and shift operations    | rd, rs1, rs2     | No immediate   |
| I-type | Immediate operations             | ALU operations with immediates, loads, JALR | rd, rs1         | 12-bit         |
| S-type | Store instructions               | Write data to memory                      | rs1, rs2         | 12-bit         |
| B-type | Branch instructions              | Conditional branching                     | rs1, rs2         | 13-bit (signed)|
| U-type | Upper immediate                  | Load upper immediate into register        | rd               | 20-bit         |
| J-type | Jump instructions                | Unconditional jumps (JAL)                 | rd               | 21-bit (signed)|

---
![png](https://github.com/user-attachments/assets/8c8d4fc9-1c9f-4f15-967f-c82341cfb365)

All these instructions follow the RISC-V instruction formats (R, I, S, B, U, J) and are encoded according to the RISC-V specification.

1. addi sp, sp, -96
addi (Add Immediate): Adds an immediate value to a register and stores the result in the destination register.

Instruction: addi sp, sp, -96

Opcode: 0010011 (7 bits)

Immediate: -96 (12 bits, 111110100000)

Destination Register (rd): sp (x2, 00010)

Source Register (rs1): sp (x2, 00010)

Function (funct3): 000 (3 bits)

Binary Representation: 111110100000 00010 000 00010 0010011

2. sd s3, 0(sp)
sd (Store Doubleword): Stores a 64-bit value from a source register into memory.

Instruction: sd s3, 0(sp)

Opcode: 0100011 (7 bits)

Immediate: 0 (12 bits, 000000000000; imm[11:5]=0000000, imm[4:0]=00000)

Source Register (rs2): s3 (x19, 10011)

Base Register (rs1): sp (x2, 00010)

Function (funct3): 011 (3 bits)

Binary Representation: 0000000 10011 00010 011 00000 0100011

3. mv s3, a0
mv (Move): Pseudo-instruction, translates to addi s3, a0, 0.

Instruction: addi s3, a0, 0

Opcode: 0010011 (7 bits)

Immediate: 0 (12 bits, 000000000000)

Destination Register (rd): s3 (x19, 10011)

Source Register (rs1): a0 (x10, 01010)

Function (funct3): 000 (3 bits)

Binary Representation: 000000000000 01010 000 10011 0010011

4. sd s4, 8(sp)
sd (Store Doubleword): Stores a 64-bit value from a source register into memory.

Instruction: sd s4, 8(sp)

Opcode: 0100011 (7 bits)

Immediate: 8 (12 bits, 000000001000; imm[11:5]=0000000, imm[4:0]=01000)

Source Register (rs2): s4 (x20, 10100)

Base Register (rs1): sp (x2, 00010)

Function (funct3): 011 (3 bits)

Binary Representation: 0000000 10100 00010 011 01000 0100011

5. sd s5, 16(sp)
sd (Store Doubleword): Stores a 64-bit value from a source register into memory.

Instruction: sd s5, 16(sp)

Opcode: 0100011 (7 bits)

Immediate: 16 (12 bits, 000000010000; imm[11:5]=0000000, imm[4:0]=10000)

Source Register (rs2): s5 (x21, 10101)

Base Register (rs1): sp (x2, 00010)

Function (funct3): 011 (3 bits)

Binary Representation: 0000000 10101 00010 011 10000 0100011

6. sd s6, 24(sp)
sd (Store Doubleword): Stores a 64-bit value from a source register into memory.

Instruction: sd s6, 24(sp)

Opcode: 0100011 (7 bits)

Immediate: 24 (12 bits, 000000011000; imm[11:5]=0000000, imm[4:0]=11000)

Source Register (rs2): s6 (x22, 10110)

Base Register (rs1): sp (x2, 00010)

Function (funct3): 011 (3 bits)

Binary Representation: 0000000 10110 00010 011 11000 0100011

7. sd s7, 32(sp)
sd (Store Doubleword): Stores a 64-bit value from a source register into memory.

Instruction: sd s7, 32(sp)

Opcode: 0100011 (7 bits)

Immediate: 32 (12 bits, 000000100000; imm[11:5]=0000001, imm[4:0]=00000)

Source Register (rs2): s7 (x23, 10111)

Base Register (rs1): sp (x2, 00010)

Function (funct3): 011 (3 bits)

Binary Representation: 0000001 10111 00010 011 00000 0100011

8. sd s8, 40(sp)
sd (Store Doubleword): Stores a 64-bit value from a source register into memory.

Instruction: sd s8, 40(sp)

Opcode: 0100011 (7 bits)

Immediate: 40 (12 bits, 000000101000; imm[11:5]=0000001, imm[4:0]=01000)

Source Register (rs2): s8 (x24, 11000)

Base Register (rs1): sp (x2, 00010)

Function (funct3): 011 (3 bits)

Binary Representation: 0000001 11000 00010 011 01000 0100011

9. jal ra, <enornlz>
jal (Jump and Link): Jumps to a target address and saves the return address.

Instruction: jal ra, <enornlz>

Opcode: 1101111 (7 bits)

Destination Register (rd): ra (x1, 00001)

Immediate: Encoded 20-bit offset (depends on target address)

Binary Representation: [Depends on offset]

10. sub s3, a0, a0
sub (Subtract): Subtracts the second source register from the first and stores the result.

Instruction: sub s3, a0, a0

Opcode: 0110011 (7 bits)

Destination Register (rd): s3 (x19, 10011)

Source Register 1 (rs1): a0 (x10, 01010)

Source Register 2 (rs2): a0 (x10, 01010)

Function (funct3): 000 (3 bits)

Function (funct7): 0100000 (7 bits)

Binary Representation: 0100000 01010 01010 000 10011 0110011

11. addi s2, sp, 52
addi (Add Immediate): Adds an immediate value to a register and stores the result in the destination register.

Instruction: addi s2, sp, 52

Opcode: 0010011 (7 bits)

Immediate: 52 (12 bits, 000000110100)

Destination Register (rd): s2 (x18, 10010)

Source Register (rs1): sp (x2, 00010)

Function (funct3): 000 (3 bits)

Binary Representation: 000000110100 00010 000 10010 0010011

12. addi a5, s2, 78
addi (Add Immediate): Adds an immediate value to a register and stores the result in the destination register.

Instruction: addi a5, s2, 78

Opcode: 0010011 (7 bits)

Immediate: 78 (12 bits, 000001001110)

Destination Register (rd): a5 (x15, 01111)

Source Register (rs1): s2 (x18, 10010)

Function (funct3): 000 (3 bits)

Binary Representation: 000001001110 10010 000 01111 0010011

13. sh zero, -2(a5)
sh (Store Halfword): Stores a 16-bit value from a source register into memory.

Instruction: sh zero, -2(a5)

Opcode: 0100011 (7 bits)

Immediate: -2 (12 bits, 111111111110; imm[11:5]=1111111, imm[4:0]=11110)

Source Register (rs2): zero (x0, 00000)

Base Register (rs1): a5 (x15, 01111)

Function (funct3): 001 (3 bits)

Binary Representation: 1111111 00000 01111 001 11110 0100011

14. lhu a5, 0(a4)
lhu (Load Halfword Unsigned): Loads a 16-bit unsigned value from memory into a register.

Instruction: lhu a5, 0(a4)

Opcode: 0000011 (7 bits)

Immediate: 0 (12 bits, 000000000000)

Destination Register (rd): a5 (x15, 01111)

Base Register (rs1): a4 (x14, 01110)

Function (funct3): 101 (3 bits)

Binary Representation: 000000000000 01110 101 01111 0000011

15. bne a5, a3, <etermain+0x158>
bne (Branch Not Equal): Branches if rs1 ≠ rs2.

Instruction: bne a5, a3, <etermain+0x158>

Opcode: 1100011 (7 bits)

Source Register 1 (rs1): a5 (x15, 01111)

Source Register 2 (rs2): a3 (x13, 01101)

Function (funct3): 001 (3 bits)

Immediate: Encoded 12-bit offset (depends on branch target)

Binary Representation: [Depends on offset]

Note: Immediate fields and binary representations for branch and jump instructions depend on the actual target address and PC value. For pseudo-instructions like mv, the actual binary is that of the underlying instruction (e.g., addi with imm=0).

---




