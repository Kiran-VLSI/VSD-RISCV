Here's a refined and complete version of your `README.md` file for the **VSDSquadron Research Internship 2025**:

```markdown
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

```bash
sudo apt-get install gtkwave
```

### Yosys

Yosys is an open-source RTL synthesis tool.

```bash
sudo apt-get install yosys
```

### iVerilog

iVerilog is a Verilog simulator used for compiling and simulating Verilog designs.

```bash
sudo apt-get install iverilog
```

---

## Conclusion

You have successfully set up the essential tools for your internship:

- **Ubuntu 20.04 LTS on VirtualBox**
- **RISC-V GNU Toolchain**
- **GTKWave**
- **Yosys**
- **iVerilog**

These tools are critical for your tasks involving RISC-V architecture, simulation, and synthesis. If you encounter any issues, refer to the official documentation of each tool or consult your mentor for guidance.

---

## License

This setup guide is released under the MIT License. You are free to modify and distribute it as needed.

```

### Key Points:
- Structured into sections for readability and clarity.
- Details on setting up Ubuntu, RISC-V toolchain, and additional tools like GTKWave, Yosys, and iVerilog for a complete development environment.
