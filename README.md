 ### VSDSquadron Research Internship 2025

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

## Task 4: Task is to identify instruction type of all the given instructions with its exact 32 bits instruction code in the desired instruction type format
🧠 RISC-V Instruction Formats

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

# 🚀 RISC-V Instructions

It contains the decoding of 15 essential RISC-V assembly instructions. Each instruction includes its type, opcode, register usage, immediate value, and the full 32-bit binary encoding.

---

## 🧠 Instruction Format Key

| Field    | Meaning               |
|----------|------------------------|
| `rd`     | Destination Register   |
| `rs1`    | Source Register 1      |
| `rs2`    | Source Register 2      |
| `imm`    | Immediate Value        |
| `funct3` | Function 3 bits        |
| `funct7` | Function 7 bits        |
| `opcode` | Operation Code         |

---

## 🔧 Instructions and Encodings

### 1. `addi sp, sp, -96`
- **Type**: I-type  
- **Opcode**: `0010011`  
- **funct3**: `000`  
- **rd / rs1**: x2 (sp)  
- **imm**: -96 → `111110100000`  
- **Binary**: `111110100000 00010 000 00010 0010011`

---

### 2. `sd s3, 0(sp)`
- **Type**: S-type  
- **Opcode**: `0100011`  
- **funct3**: `011`  
- **rs2**: x19 (s3), **rs1**: x2 (sp)  
- **imm**: 0 → `0000000 00000`  
- **Binary**: `0000000 10011 00010 011 00000 0100011`

---

### 3. `mv s3, a0` *(pseudo)* → `addi s3, a0, 0`
- **Type**: I-type  
- **Opcode**: `0010011`  
- **funct3**: `000`  
- **rs1**: x10 (a0), **rd**: x19 (s3)  
- **imm**: 0 → `000000000000`  
- **Binary**: `000000000000 01010 000 10011 0010011`

---

### 4. `sd s4, 8(sp)`
- **Type**: S-type  
- **Opcode**: `0100011`  
- **funct3**: `011`  
- **rs2**: x20 (s4), **rs1**: x2 (sp)  
- **imm**: 8 → `0000000 01000`  
- **Binary**: `0000000 10100 00010 011 01000 0100011`

---

### 5. `sd s5, 16(sp)`
- **Type**: S-type  
- **Opcode**: `0100011`  
- **funct3**: `011`  
- **rs2**: x21 (s5), **rs1**: x2 (sp)  
- **imm**: 16 → `0000000 10000`  
- **Binary**: `0000000 10101 00010 011 10000 0100011`

---

### 6. `sd s6, 24(sp)`
- **Type**: S-type  
- **Opcode**: `0100011`  
- **funct3**: `011`  
- **rs2**: x22 (s6), **rs1**: x2 (sp)  
- **imm**: 24 → `0000000 11000`  
- **Binary**: `0000000 10110 00010 011 11000 0100011`

---

### 7. `ld s3, 0(sp)`
- **Type**: I-type  
- **Opcode**: `0000011`  
- **funct3**: `011`  
- **rd**: x19 (s3), **rs1**: x2 (sp)  
- **imm**: 0 → `000000000000`  
- **Binary**: `000000000000 00010 011 10011 0000011`

---

### 8. `ld s4, 8(sp)`
- **Type**: I-type  
- **Opcode**: `0000011`  
- **funct3**: `011`  
- **rd**: x20 (s4), **rs1**: x2 (sp)  
- **imm**: 8 → `000000001000`  
- **Binary**: `000000001000 00010 011 10100 0000011`

---

### 9. `ld s5, 16(sp)`
- **Type**: I-type  
- **Opcode**: `0000011`  
- **funct3**: `011`  
- **rd**: x21 (s5), **rs1**: x2 (sp)  
- **imm**: 16 → `000000010000`  
- **Binary**: `000000010000 00010 011 10101 0000011`

---

### 10. `ld s6, 24(sp)`
- **Type**: I-type  
- **Opcode**: `0000011`  
- **funct3**: `011`  
- **rd**: x22 (s6), **rs1**: x2 (sp)  
- **imm**: 24 → `000000011000`  
- **Binary**: `000000011000 00010 011 10110 0000011`

---

### 11. `sub a0, a0, a1`
- **Type**: R-type  
- **Opcode**: `0110011`  
- **funct3**: `000`, **funct7**: `0100000`  
- **rd / rs1**: x10 (a0), **rs2**: x11 (a1)  
- **Binary**: `0100000 01011 01010 000 01010 0110011`

---

### 12. `add a0, a0, a1`
- **Type**: R-type  
- **Opcode**: `0110011`  
- **funct3**: `000`, **funct7**: `0000000`  
- **rd / rs1**: x10 (a0), **rs2**: x11 (a1)  
- **Binary**: `0000000 01011 01010 000 01010 0110011`

---

### 13. `beq a0, a1, label`
- **Type**: B-type  
- **Opcode**: `1100011`  
- **funct3**: `000`  
- **rs1**: x10 (a0), **rs2**: x11 (a1)  
- **imm**: depends on label (e.g., `000000000100`)  
- **Binary (example)**: `000000 01011 01010 000 00010 1100011`

---

### 14. `jal ra, offset`
- **Type**: J-type  
- **Opcode**: `1101111`  
- **rd**: x1 (ra)  
- **imm**: 20-bit offset to label (e.g., `00000000000000000010`)  
- **Binary (example)**: `00000000000000000010 00001 1101111`

---

### 15. `jalr ra, 0(ra)`
- **Type**: I-type  
- **Opcode**: `1100111`  
- **funct3**: `000`  
- **rd**: x1 (ra), **rs1**: x1 (ra)  
- **imm**: 0 → `000000000000`  
- **Binary**: `000000000000 00001 000 00001 1100111`

---

## 📝 Notes
- The immediate (`imm`) field is sign-extended where necessary.
- Pseudo-instructions like `mv` are internally translated into base instructions (`addi` with zero immediate).
- For branch (`beq`) and jump (`jal`) instructions, the immediate is calculated relative to the program counter (PC).

---
## Task - 5:By making use of RISCV Core: Verilog Netlist and Testbench, perform an experiment of Functional Simulation and observe the waveforms

---

### ✅ Updated Steps for `kiran_riscv32i.v` (Assuming Verilog file)

#### 🗂️ **1. Create Project Directory**

```bash
mkdir kiran_riscv_project
cd kiran_riscv_project
```

#### 🧾 **2. Create Required Files**

Rename or create the Verilog and testbench files:

```bash
cp /path/to/kiran_riscv32i.v4 kiran_riscv32i.v
touch kiran_riscv32i_tb.v
```


#### 🧠 **3. Add Code**

* Open `kiran_riscv32i.v` and paste or verify the RISC-V core code.
* In `kiran_riscv32i_tb.v`, write the testbench code.

```verilog
initial begin
  $dumpfile("kiran_riscv32i.vcd");
  $dumpvars(0, testbench_top);
end
```

> Replace `testbench_top` with the top module name of your testbench.

---

#### ⚙️ **4. Compile & Simulate**

```bash
iverilog -o kiran_riscv32i kiran_riscv32i.v kiran_riscv32i_tb.v
./kiran_riscv32i
```

---

#### 📊 **5. View in GTKWave**
![GTKWave Window](https://github.com/user-attachments/assets/7dcdcd8e-b803-4e60-b2bb-79e3561eb20a)

```bash
gtkwave kiran_riscv32i.vcd
```
This table compares a set of basic RISC-V RV32I instructions with their corresponding hardcoded instruction encodings used in a Verilog-based instruction memory model. The Standard RISC-V ISA column shows the official binary encodings, while the Hardcoded ISA column lists the values manually assigned in memory during simulation.

| Operation         | Standard RISC-V ISA | Hardcoded ISA     |
|-------------------|---------------------|-------------------|
| ADD R6, R2, R1     | 32'h00110333        | 32'h02208300      |
| SUB R7, R1, R2     | 32'h402083b3        | 32'h02209380      |
| AND R8, R1, R3     | 32'h0030f433        | 32'h0230a400      |
| OR R9, R2, R5      | 32'h005164b3        | 32'h02513480      |
| XOR R10, R1, R4    | 32'h0040c533        | 32'h0240c500      |
| SLT R11, R2, R4    | 32'h0045a0b3        | 32'h02415580      |
| ADDI R12, R4, 5    | 32'h00520613        | 32'h00520600      |
| SW R3, 2(R1)       | 32'h0020a023        | 32'h00209181      |
| LW R13, 2(R1)      | 32'h0020a283        | 32'h00208681      |
| BEQ R0, R0, 15     | 32'h00f00063        | 32'h00f00002      |
| ADD R14, R2, R2    | 32'h002107b3        | 32'h00210700      |

Analysing the Output Waveform of various instructions that we have covered in TASK-2

# Instruction 1: ADD R6, R1, R2
![ISA-1](https://github.com/user-attachments/assets/f5d81e6a-100c-4a6f-a9b7-2f235294de24)

# Instruction 2: SUB R7, R1, R2
![ISA-2](https://github.com/user-attachments/assets/f2abaf97-402c-4801-ba3f-976807b9c4cf)

# Instruction 3: AND R8, R1, R3
![ISA-3](https://github.com/user-attachments/assets/052a3bbf-2475-4c67-9728-4494628cfede)

# Instruction 4: OR R9, R2, R5
![image](https://github.com/user-attachments/assets/6f585e9b-aaca-4169-853e-21f6746f75a4)

# Instruction 5:XOR r10, r1, r4



---

