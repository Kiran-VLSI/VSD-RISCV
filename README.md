 ### VSDSquadron Research Internship 2025

## Overview

The **VSDSquadron Research Internship 2025** focuses on **RISC-V architecture** and **open-source VLSI design**. The program provides hands-on experience in **chip design** using industry-standard open-source tools. The internship is led by **Kunal Ghosh Sir** and aims to bridge the gap between academia and industry in **VLSI and RISC-V**.

## Internship Details
- **Intern:** CHANDRAKIRAN G  
- **College:** St. Joseph's Institute Of Technology  
- **Email:** [gchandrakiran97@gmail.com](mailto:gchandrakiran97@gmail.com)  
- **GitHub Profile:** [Kiran-VLSI](https://github.com/Kiran-VLSI)  
- **LinkedIn Profile:** [Chandrakiran G](https://www.linkedin.com/in/chandrakiran-g-409816257)  

# Task 1: Tool Installation

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
# Task 2: Task is to identify instruction type of all the given instructions with its exact 32 bits instruction code in the desired instruction type format

WHAT IS RISC-V?
RISC-V is an open-source instruction set architecture (ISA) that allows developers to develop processors for specific applications.
RISC-V is based on reduced instruction set computer principles and is the fifth generation of processors built on this concept.
RISC-V can also be understood as an alternative processor technology which is free and open, meaning that it does not require you to purchase the license of RISC-V to use it.
INSTRUCTIONS FORMAT IN RISC-V

The instructions format of a processor is the way in which machine language instructions are structured and organized for a processor to execute. It is made up of series of 0s and 1s, each containing information about the location and operation of data.
There are 6 instruction formats in RISC-V:

R-format
I-format
S-format
B-format
U-format
J-format
![326074466-f8e6fd22-79c5-4f6c-b59f-2b38fdb62c0e](https://github.com/user-attachments/assets/f2e7d18a-ccf6-470c-b3d5-8f26c8f1daa1)

## 📘 About RISC-V

**RISC-V** (Reduced Instruction Set Computer - Five) is a free, open-source Instruction Set Architecture (ISA) designed for simplicity, modularity, and scalability. It supports a wide range of applications — from embedded systems to high-performance computing — and is ideal for academic research, industry, and open hardware projects.

---

## 📦 Instruction Format Overview

Each instruction in RISC-V (RV32I) is **32 bits long** and conforms to one of six formats:

| Format | Description                      | Used For                                  | Registers       | Immediate Type |
|--------|----------------------------------|-------------------------------------------|------------------|----------------|
| R-type | Register operations              | Arithmetic, logic, and shift operations   | rd, rs1, rs2     | No immediate   |
| I-type | Immediate operations             | ALU operations with immediates, loads, JALR | rd, rs1        | 12-bit         |
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
# Task 3: Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler

C Language based LAB
We have to follow the given steps to compile any .c file in our machine:

Open the bash terminal and locate to the directory where you want to create your file. Then run the following command:

gedit sum_1ton.c

This will open the editor and allows you to write into the file that you have created. You have to write the C code of printing the sum of n numbers. Once you are done with your code, press Ctrl + S to save your file, and then press Ctrl + W to close the editor.

To the C code on your terminal, run the following command:

gcc sum_1ton.c
./a.out
C Code compiled on gcc Compiler
![Spike Simulation](https://github.com/user-attachments/assets/01325b74-8081-404c-9136-2d82e8b0e80d)

RISCV based LAB
We have to do the same compilation of our code but this time using RISCV gcc compiler. Follow the given steps:

Open the terminal and run the given command:

cat sum_1ton.c
cat Command

Using the cat command, the entire C code will be displayed on the terminal. Now run the following command to compile the code in riscv64 gcc compiler:
![Objdump in -O1](https://github.com/user-attachments/assets/8f7c3105-c6f5-47b9-bf82-0ede2d0980a1)

riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum_1ton.o sum_1ton.c
Open a new terminal and run the given command:

riscv64-unknown-elf-objdump -d sum_1ton.o
Objdump using -O1 format

The Assembly Language code of our C code will be displayed on the terminal. Type /main to locate the main section of our code.
Descriptions of the keyword used in above command
-mabi=lp64: This option specifies the ABI (Application Binary Interface) to use lp64, which is for 64-bit integer, long and pointer size. This ABI is used for 64-bit RISCV architecture.
-march=rv64i: This option specifies the architecture that we use, which is rv64i, indicates the 64-bit RISCV base integer instruction set. This also confirms the targeting of 64-bit architecture.
riscv-objdump: A tool for disassembling RISC-V binaries, providing insights into the code structure and helping in debugging.
-Ofast: The option -Ofast in the command riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c is a compiler optimization flag used with the GNU Compiler Collection (GCC). This flag is used to instruct the compiler to optimize the generated code for maximum speed. The use of -Ofast is typically chosen for applications where execution speed is critical and where deviations from standard behavior are acceptable. However, it's important to test thoroughly, as this level of optimization can introduce subtle bugs, especially in complex calculations or when strict compliance with external standards is required.
-O1: This options is an optimization level that tells the compiler to optimize the generated code but without greatly increasing compilation time. -O1 aims to reduce code size and execution time while keeping the compilation process relatively quick.
Other common options are as follows:

-O0: No optimization, the default level if no -O option is specified.
-O2: More aggressive optimizations that might increase compilation time but typically provide faster and sometimes smaller code.
-O3: Maximizes optimization more aggressively than -O2.
-Os: Optimizes code for size. It enables all -O2 optimizations that do not typically increase code size.
Here, the term more aggressive optimization in the context of compilers like GCC refers to a deeper and more complex set of transformations applied to the code in order to improve its performance and possibly reduce its size. The compiler uses more complex techniques that aims to generate faster executing code or code that occupies less memory. However, these optimizations typically increase the compilation time and can sometimes introduce bugs, making it harder to debug.

# Task - 5:By making use of RISCV Core: Verilog Netlist and Testbench, perform an experiment of Functional Simulation and observe the waveforms

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
![image](https://github.com/user-attachments/assets/8c7fa91c-7cf4-477a-94e3-ec6db1a39001)

# Instruction 5:XOR r10, r1, r4
![image](https://github.com/user-attachments/assets/b577c87d-a145-4742-ad68-f108a577223e)

# Instruction 6: SLT R11, R2, R4
![image](https://github.com/user-attachments/assets/a7c0ad83-7126-4189-8d40-dc7ce7162ae7)

# Instruction 7: ADDI R12, R4, 5
![ISA-6](https://github.com/user-attachments/assets/3e4d3828-5a35-45ff-becf-f79f0eb6b771)

# Instruction 8: SW R3, R1, 2
![image](https://github.com/user-attachments/assets/589b4bbc-c6b7-4fe9-a5e1-a5aa57ed71cc)

# Instruction 9: LW R13, R1, 2
![image](https://github.com/user-attachments/assets/7424fe1a-54c5-4163-b286-4783a5f0a5b0)

# Instruction 10: BEQ R0, R0, 15
![image](https://github.com/user-attachments/assets/787b48e3-b891-4b82-b2d7-0fe97e515e9e)

# Task 5: Final Task of this internship is to implement any digital circuits using VSDSquadron Mini and check whether the building and uploading of C program file on RISCV processor works
# 🚪 Smart Door Automation using CH32V003 RISC-V SoC

## 📌 Overview

The **Smart Door Automation** project demonstrates the integration of an **IR sensor** and **servo motor** with the **CH32V003 RISC-V microcontroller** to create a fully automated door system. This system detects the presence of a person using an infrared sensor and opens or closes the door accordingly using a servo motor, controlled by PWM signals from the RISC-V processor. It eliminates the need for manual intervention and offers a smart, secure, and energy-efficient access solution.

---

## 🔧 Components Required

| Component          | Quantity |
|--------------------|----------|
| CH32V003 Development Board | 1 |
| IR Sensor          | 1 |
| Servo Motor (SG90) | 1 |
| Breadboard         | 1 |
| Jumper Wires       | As needed |
| Power Supply (3.3V–5V) | 1 |

---

## 🔌 Circuit Connections

### 🔲 IR Sensor to CH32V003
| IR Sensor Pin | CH32V003 Pin |
|---------------|--------------|
| VCC           | VIN (3.3V/5V) |
| OUT           | D3           |
| GND           | GND          |

### 🔄 Servo Motor to CH32V003
| Servo Pin     | CH32V003 Pin |
|---------------|--------------|
| VCC (Red)     | VIN (5V)     |
| PWM (Yellow)  | D2           |
| GND (Brown)   | GND          |

---

## 🧠 How It Works

1. The **IR sensor** detects the presence of an object (e.g., a person approaching).
2. Its **digital output** goes high/low and is read by the CH32V003 through **GPIO D3**.
3. The CH32V003 generates a **PWM signal** on **D2** to control the **servo motor**.
4. The servo rotates to **open** the door when the object is detected and **closes** after a short delay.

---
## Circuit Diagram:

![WhatsApp Image 2025-06-29 at 15 33 53_e142889d](https://github.com/user-attachments/assets/a6a7b007-8483-4420-a318-2dd74f8659ee)



## 🖥️ Programming Guide

1. **Include necessary headers:**
   ```c
   #include "ch32v00x.h"
   #include "debug.h"

2. Configure GPIOs:

Set D3 as input (for IR sensor)

Set D2 as PWM output (for Servo control)

3. Generate PWM:
Use a timer (e.g., TIM2) to generate a PWM signal with the correct duty cycle to rotate the servo to desired angles.

Logic Example:

c

if(GPIO_ReadInputDataBit(GPIOA, GPIO_Pin_3)) {

    // Object detected
    setServoAngle(90); // Open door

} else {

    setServoAngle(0); // Close door
}
# How to Program?
# Implementation of Smart Door using IR sensor and servo motor
// main.c
```c
#include "ch32v00x.h"
#include "debug.h"

/* PWM Output Mode Definition */
#define PWM_MODE1 0
#define PWM_MODE2 1

/* PWM Output Mode Selection */
#define PWM_MODE PWM_MODE2

// Initialize Timer1 Channel 1 (PD2) for PWM output
void TIM1_PWMOut_Init(uint16_t arr, uint16_t psc, uint16_t ccp)
{
    GPIO_InitTypeDef GPIO_InitStructure = {0};
    TIM_OCInitTypeDef TIM_OCInitStructure = {0};
    TIM_TimeBaseInitTypeDef TIM_TimeBaseInitStructure = {0};

    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE);

    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_2;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_AF_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_10MHz;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    RCC_APB2PeriphClockCmd(RCC_APB2Periph_TIM1, ENABLE);

    TIM_TimeBaseInitStructure.TIM_Period = arr;
    TIM_TimeBaseInitStructure.TIM_Prescaler = psc;
    TIM_TimeBaseInitStructure.TIM_ClockDivision = TIM_CKD_DIV1;
    TIM_TimeBaseInitStructure.TIM_CounterMode = TIM_CounterMode_Up;
    TIM_TimeBaseInit(TIM1, &TIM_TimeBaseInitStructure);

#if (PWM_MODE == PWM_MODE1)
    TIM_OCInitStructure.TIM_OCMode = TIM_OCMode_PWM1;
#elif (PWM_MODE == PWM_MODE2)
    TIM_OCInitStructure.TIM_OCMode = TIM_OCMode_PWM2;
#endif

    TIM_OCInitStructure.TIM_OutputState = TIM_OutputState_Enable;
    TIM_OCInitStructure.TIM_Pulse = ccp;
    TIM_OCInitStructure.TIM_OCPolarity = TIM_OCPolarity_High;
    TIM_OC1Init(TIM1, &TIM_OCInitStructure);

    TIM_CtrlPWMOutputs(TIM1, ENABLE);
    TIM_OC1PreloadConfig(TIM1, TIM_OCPreload_Disable);
    TIM_ARRPreloadConfig(TIM1, ENABLE);
    TIM_Cmd(TIM1, ENABLE);
}

// GPIO Configuration for IR input (PD3) and LED output (PD6)
void GPIO_Config(void)
{
    GPIO_InitTypeDef GPIO_InitStructure = {0};
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE);

    // IR Sensor input (PD3)
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_3;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // LED output (PD6)
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_6;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOD, &GPIO_InitStructure);
}

// Main program
int main(void)
{
    uint8_t GPIOInputStatus = 0;

    NVIC_PriorityGroupConfig(NVIC_PriorityGroup_2);
    SystemCoreClockUpdate();
    Delay_Init();
    GPIO_Config();

    while (1)
    {
        GPIOInputStatus = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_3);

        if (GPIOInputStatus == 0)
        {
            GPIO_WriteBit(GPIOD, GPIO_Pin_6, SET);    // Turn ON LED
            TIM1_PWMOut_Init(100, 480 - 1, 10);        // 10% duty cycle
        }
        else
        {
            GPIO_WriteBit(GPIOD, GPIO_Pin_6, RESET);  // Turn OFF LED
            TIM1_PWMOut_Init(100, 480 - 1, 95);        // 95% duty cycle
        }

        Delay_Ms(100);
    }
}

// Interrupt Handlers
void NMI_Handler(void) {}
void HardFault_Handler(void) { while (1); }

```
# Electrical Characteristics
1. Component	Voltage Range	Interface
2. CH32V003 MCU	1.8V – 3.6V	GPIO, PWM
3. IR Sensor	3.3V / 5V	Digital OUT
4. Servo Motor	4.8V – 6V	PWM control

# Application Video
https://github.com/user-attachments/assets/25d2b402-13ba-4860-865c-f68dde87ee96

## Applications
1. Smart Home Automation
2. Office Entry Systems
3. Contactless Public Access Control
4. DIY Robotics & IoT Projects


---

