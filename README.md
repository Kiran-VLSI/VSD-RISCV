# VSDSquadron Research Internship 2025

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

Here is a simplified and single-file version of the README you requested:

```markdown
# Internship Setup Guide: Essential Tools Installation

## Task 1: Install Ubuntu 20.04 LTS on Oracle VirtualBox

### Step 1: Download and Install VirtualBox
1. **Download Oracle VM VirtualBox**: [Download VirtualBox](https://www.virtualbox.org/)
2. **Download Ubuntu 20.04 LTS ISO**: [Download Ubuntu 20.04 LTS](https://releases.ubuntu.com/20.04/)
3. **Install Ubuntu**: 
   - Create a new VM in VirtualBox, selecting Ubuntu 64-bit as the OS.
   - Allocate memory (RAM) and disk space.
   - Use the Ubuntu ISO as the installation disk and follow the on-screen installation instructions.

---

## Task 2: Install RISC-V GNU Toolchain

### What is RISC-V GNU Toolchain?

The **RISC-V GNU Toolchain** is a free and open-source compiler suite for C and C++. It supports the creation of assembly instructions and sequences for simulators and FPGA targets.

### Step-by-Step Installation

#### Step 1: Install Dependencies
Open a terminal and run the following command to install required packages:

```bash
sudo apt install git
```

#### Step 2: Clone the RISC-V Toolchain Repository
Clone the RISC-V toolchain from GitHub:

```bash
git clone https://github.com/riscv/riscv-gnu-toolchain
```

#### Step 3: Install Required Libraries
Install additional dependencies:

```bash
sudo apt-get install autoconf automake autotools-dev curl python3 python3-pip libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev ninja-build git cmake libglib2.0-dev libslirp-dev
```

#### Step 4: Set Up the Installation Directory
Create a directory for installing the RISC-V toolchain:

```bash
sudo mkdir /opt/riscv
```

#### Step 5: Configure the Toolchain
Navigate to the `riscv-gnu-toolchain` directory and run the configuration:

```bash
cd riscv-gnu-toolchain
./configure --prefix=/opt/riscv --with-arch=rv64i --with-abi=lp64 --enable-multilib
```

#### Step 6: Build the Toolchain
Build the toolchain with:

```bash
sudo make
```

This process might take a while depending on your system's resources.

#### Step 7: Update the PATH Variable
Add the toolchain to your PATH by modifying the `.bashrc` file:

```bash
gedit ~/.bashrc
```

Add the following line to the end of the file:

```bash
export PATH="$PATH:/opt/riscv/bin"
```

Save the file and close the editor. Then, apply the changes with:

```bash
source ~/.bashrc
```

#### Step 8: Verify Installation
To check if the installation was successful, run:

```bash
riscv64-unknown-elf-gcc --version
```

This should display the version of the RISC-V GCC compiler.

---

## Additional Tools Installation

### 1. GTKWave

GTKWave is a waveform viewer used for viewing simulation outputs.

```bash
sudo apt-get install gtkwave
```

### 2. Yosys

Yosys is an RTL synthesis tool.

```bash
sudo apt-get install yosys
```

### 3. iVerilog

iVerilog is a Verilog simulator.

```bash
sudo apt-get install iverilog
```

---

## Conclusion

You have now successfully installed all the essential tools required for the internship, including:
- **Ubuntu 20.04 LTS on VirtualBox**
- **RISC-V GNU Toolchain**
- **GTKWave**
- **Yosys**
- **iVerilog**

You are now ready to begin your work. If you encounter any issues, refer to the official documentation for each tool, or check for error messages in the terminal for further troubleshooting.
```

This file is a complete guide to installing the necessary tools in a single `README.md` file, with concise instructions and steps.
