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

Task 4: Task is to identify instruction type of all the given instructions with its exact 32 bits instruction code in the desired instruction type format
# 🧠 RISC-V Instruction Formats

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
Based on the image you provided (a terminal view of RISC-V assembly with corresponding machine codes), I’ve extracted **15 unique RISC-V instructions** and presented their machine code breakdowns in the format you've requested.

---

### ✅ **1. Instruction: `addi sp, sp, -96`**

* **Machine Code**: `fa010113`
* **Type**: I-Type
* **Opcode**: `0010011`
* **Immediate (-96)**: `111111101000`
* **rs1 (sp = x2)**: `00010`
* **funct3**: `000`
* **rd (sp = x2)**: `00010`

| imm\[11:0]     | rs1     | funct3 | rd      | opcode    |
| -------------- | ------- | ------ | ------- | --------- |
| `111111101000` | `00010` | `000`  | `00010` | `0010011` |

---

### ✅ **2. Instruction: `sd s0, 80(sp)`**

* **Machine Code**: `02813023`
* **Type**: S-Type
* **Opcode**: `0100011`
* **funct3**: `011`
* **rs1 (sp = x2)**: `00010`
* **rs2 (s0 = x8)**: `01000`
* **imm (80)**: `0000101 00000`

| imm\[11:5] | rs2     | rs1     | funct3 | imm\[4:0] | opcode    |
| ---------- | ------- | ------- | ------ | --------- | --------- |
| `0000101`  | `01000` | `00010` | `011`  | `00000`   | `0100011` |

---

### ✅ **3. Instruction: `lhu a0, 2(a5)`**

* **Machine Code**: `0027d703`
* **Type**: I-Type
* **Opcode**: `0000011`
* **funct3**: `101`
* **rd (a0 = x10)**: `01010`
* **rs1 (a5 = x15)**: `01111`
* **imm**: `000000000010`

| imm\[11:0]     | rs1     | funct3 | rd      | opcode    |
| -------------- | ------- | ------ | ------- | --------- |
| `000000000010` | `01111` | `101`  | `01010` | `0000011` |

---

### ✅ **4. Instruction: `jal ra, 14280 <enorm1z>`**

* **Machine Code**: `e7dfc0ef`
* **Type**: J-Type
* **Opcode**: `1101111`
* **rd (ra = x1)**: `00001`
* **imm** (split into 20-bit format): reverse engineered from address

\| imm\[20|10:1|11|19:12] | rd   | opcode   |
\|------------------------|--------|------------|
\| See address offset      | `00001` | `1101111` |

---

### ✅ **5. Instruction: `mv s2, a0`**

* **Machine Code**: `00050913`
* **Pseudo-instruction**: `addi s2, a0, 0`
* **Type**: I-Type

| imm\[11:0]     | rs1     | funct3 | rd      | opcode    |
| -------------- | ------- | ------ | ------- | --------- |
| `000000000000` | `01010` | `000`  | `10010` | `0010011` |

---

### ✅ **6. Instruction: `slli a0, a0, 3`**

* **Machine Code**: `00351513`
* **Type**: I-Type
* **Opcode**: `0010011`
* **funct3**: `001` (for SLLI)
* **rd/rs1 (a0 = x10)**: `01010`
* **shamt**: `000000000011`

| shamt          | rs1     | funct3 | rd      | opcode    |
| -------------- | ------- | ------ | ------- | --------- |
| `000000000011` | `01010` | `001`  | `01010` | `0010011` |

---

### ✅ **7. Instruction: `sw a4, -20(s0)`**

* **Machine Code**: `fec42723`
* **Type**: S-Type
* **Opcode**: `0100011`
* **funct3**: `010`
* **rs1 (s0 = x8)**: `01000`
* **rs2 (a4 = x14)**: `01110`
* **imm (-20)**: Two's complement → `1111110 01100`

| imm\[11:5] | rs2     | rs1     | funct3 | imm\[4:0] | opcode    |
| ---------- | ------- | ------- | ------ | --------- | --------- |
| `1111110`  | `01110` | `01000` | `010`  | `01100`   | `0100011` |

---

### ✅ **8. Instruction: `ld s1, 72(sp)`**

* **Machine Code**: `04813483`
* **Type**: I-Type
* **Opcode**: `0000011`
* **funct3**: `011`
* **rs1 (sp = x2)**: `00010`
* **rd (s1 = x9)**: `01001`
* **imm (72)**: `00000001001000`

| imm\[11:0]       | rs1     | funct3 | rd      | opcode    |
| ---------------- | ------- | ------ | ------- | --------- |
| `00000001001000` | `00010` | `011`  | `01001` | `0000011` |

---

### ✅ **9. Instruction: `bne a5, a4, <offset>`**

* **Machine Code**: `00e78c63`
* **Type**: B-Type
* **Opcode**: `1100011`
* **funct3**: `001`
* **rs1 (a5 = x15)**: `01111`
* **rs2 (a4 = x14)**: `01110`
* **imm**: offset derived from instruction address

\| imm\[12|10:5] | rs2   | rs1   | funct3 | imm\[4:1|11] | opcode   |
\|---------------|--------|--------|---------|----------------|------------|
\| \[based on PC] | `01110` | `01111` | `001`     | \[based on PC]  | `1100011` |

---

### ✅ **10. Instruction: `jalr a1, 0(a0)`**

* **Machine Code**: `00058593`
* **Type**: I-Type
* **Opcode**: `1100111`
* **funct3**: `000`
* **rs1 (a0 = x10)**: `01010`
* **rd (a1 = x11)**: `01011`
* **imm**: `000000000000`

---

### ✅ **11. Instruction: `li a5, 2`**

* **Machine Code**: `00200793`
* **Pseudo-instruction**: `addi a5, zero, 2`

| imm\[11:0]     | rs1     | funct3 | rd      | opcode    |
| -------------- | ------- | ------ | ------- | --------- |
| `000000000010` | `00000` | `000`  | `01111` | `0010011` |

---

### ✅ **12. Instruction: `sub a4, s0, s2`**

* **Machine Code**: `41240533`
* **Type**: R-Type
* **Opcode**: `0110011`
* **funct3**: `000`
* **funct7**: `0100000` (for SUB)
* **rs1 (s0 = x8)**: `01000`
* **rs2 (s2 = x18)**: `10010`
* **rd (a4 = x14)**: `01110`

| funct7    | rs2     | rs1     | funct3 | rd      | opcode    |
| --------- | ------- | ------- | ------ | ------- | --------- |
| `0100000` | `10010` | `01000` | `000`  | `01110` | `0110011` |

---

### ✅ **13. Instruction: `slli a4, a4, 2`**

* **Machine Code**: `00271713`
* **Type**: I-Type
* **Opcode**: `0010011`
* **funct3**: `001`
* **rd/rs1 (a4 = x14)**: `01110`
* **shamt**: `000000000010`

---

### ✅ **14. Instruction: `ld a1, 88(sp)`**

* **Machine Code**: `05813583`
* **Type**: I-Type
* **Opcode**: `0000011`
* **rd (a1 = x11)**: `01011`
* **rs1 (sp = x2)**: `00010`
* **funct3**: `011`
* **imm**: `00000001011000`

---

### ✅ **15. Instruction: `sh a5, -24(a0)`**

* **Machine Code**: `fe9797a3`
* **Type**: S-Type
* **Opcode**: `0100011`
* **funct3**: `001`
* **rs1 (a0 = x10)**: `01010`
* **rs2 (a5 = x15)**: `01111`
* **imm (-24)**: `111111001000`

| imm\[11:5] | rs2     | rs1     | funct3 | imm\[4:0] | opcode    |
| ---------- | ------- | ------- | ------ | --------- | --------- |
| `1111110`  | `01111` | `01010` | `001`  | `01000`   | `0100011` |

---

Here is the data in the requested format for 15 RISC-V instructions extracted from the image:

---

### **1. Instruction**: `addi sp, sp, -96`

**2. Breakdown**:

* Opcode: `0010011`
* funct3: `000`
* rd (sp): `00010`
* rs1 (sp): `00010`
* imm (-96): `111111101000`

**3. Binary Representation**:
`111111101000 00010 000 00010 0010011` → `fa010113`

---

### **2. Instruction**: `sd s0, 80(sp)`

**2. Breakdown**:

* Opcode: `0100011`
* funct3: `011`
* rs1 (sp): `00010`
* rs2 (s0): `01000`
* imm (80): `0000101 00000`

**3. Binary Representation**:
`0000101 01000 00010 011 00000 0100011` → `02813023`

---

### **3. Instruction**: `lhu a0, 2(a5)`

**2. Breakdown**:

* Opcode: `0000011`
* funct3: `101`
* rd (a0): `01010`
* rs1 (a5): `01111`
* imm (2): `000000000010`

**3. Binary Representation**:
`000000000010 01111 101 01010 0000011` → `0027d703`

---

### **4. Instruction**: `jal ra, 14280 <enorm1z>`

**2. Breakdown**:

* Opcode: `1101111`
* rd (ra): `00001`
* imm: Offset to 14280 (represented over bits \[20|10:1|11|19:12])

**3. Binary Representation**:
`imm[20|10:1|11|19:12] 00001 1101111` → `e7dfc0ef`

---

### **5. Instruction**: `mv s2, a0` (Pseudo: `addi s2, a0, 0`)

**2. Breakdown**:

* Opcode: `0010011`
* funct3: `000`
* rd (s2): `10010`
* rs1 (a0): `01010`
* imm: `000000000000`

**3. Binary Representation**:
`000000000000 01010 000 10010 0010011` → `00050913`

---

### **6. Instruction**: `slli a0, a0, 3`

**2. Breakdown**:

* Opcode: `0010011`
* funct3: `001`
* rd/rs1 (a0): `01010`
* shamt: `000000000011`

**3. Binary Representation**:
`000000000011 01010 001 01010 0010011` → `00351513`

---

### **7. Instruction**: `sw a4, -20(s0)`

**2. Breakdown**:

* Opcode: `0100011`
* funct3: `010`
* rs1 (s0): `01000`
* rs2 (a4): `01110`
* imm (-20): `111111001100` → split into `imm[11:5]=1111110`, `imm[4:0]=01100`

**3. Binary Representation**:
`1111110 01110 01000 010 01100 0100011` → `fec42723`

---

### **8. Instruction**: `ld s1, 72(sp)`

**2. Breakdown**:

* Opcode: `0000011`
* funct3: `011`
* rd (s1): `01001`
* rs1 (sp): `00010`
* imm: `00000001001000`

**3. Binary Representation**:
`00000001001000 00010 011 01001 0000011` → `04813483`

---

### **9. Instruction**: `bne a5, a4, offset`

**2. Breakdown**:

* Opcode: `1100011`
* funct3: `001`
* rs1 (a5): `01111`
* rs2 (a4): `01110`
* imm: offset bits rearranged as `imm[12|10:5]` and `imm[4:1|11]`

**3. Binary Representation**:
`imm[12|10:5] 01110 01111 001 imm[4:1|11] 1100011` → `00e78c63`

---

### **10. Instruction**: `jalr a1, 0(a0)`

**2. Breakdown**:

* Opcode: `1100111`
* funct3: `000`
* rd (a1): `01011`
* rs1 (a0): `01010`
* imm: `000000000000`

**3. Binary Representation**:
`000000000000 01010 000 01011 1100111` → `00058593`

---

### **11. Instruction**: `li a5, 2` (Pseudo: `addi a5, zero, 2`)

**2. Breakdown**:

* Opcode: `0010011`
* funct3: `000`
* rd (a5): `01111`
* rs1 (zero): `00000`
* imm: `000000000010`

**3. Binary Representation**:
`000000000010 00000 000 01111 0010011` → `00200793`

---

### **12. Instruction**: `sub a4, s0, s2`

**2. Breakdown**:

* Opcode: `0110011`
* funct7: `0100000`
* funct3: `000`
* rd (a4): `01110`
* rs1 (s0): `01000`
* rs2 (s2): `10010`

**3. Binary Representation**:
`0100000 10010 01000 000 01110 0110011` → `41240533`

---

### **13. Instruction**: `slli a4, a4, 2`

**2. Breakdown**:

* Opcode: `0010011`
* funct3: `001`
* rd/rs1 (a4): `01110`
* shamt: `000000000010`

**3. Binary Representation**:
`000000000010 01110 001 01110 0010011` → `00271713`

---

### **14. Instruction**: `ld a1, 88(sp)`

**2. Breakdown**:

* Opcode: `0000011`
* funct3: `011`
* rd (a1): `01011`
* rs1 (sp): `00010`
* imm: `00000001011000`

**3. Binary Representation**:
`00000001011000 00010 011 01011 0000011` → `05813583`

---

### **15. Instruction**: `sh a5, -24(a0)`

**2. Breakdown**:

* Opcode: `0100011`
* funct3: `001`
* rs1 (a0): `01010`
* rs2 (a5): `01111`
* imm (-24): `111111001000` → split as `1111110` and `01000`

**3. Binary Representation**:
`1111110 01111 01010 001 01000 0100011` → `fe9797a3`

---




