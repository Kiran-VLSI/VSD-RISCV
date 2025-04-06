Here's a detailed breakdown for **Task 1**, which involves installing essential tools for your internship, including **Ubuntu on VirtualBox**, **RISC-V GNU Toolchain**, **GTKWave**, **Yosys**, and **iVerilog Simulator**:

---

# Task 1: Install Essential Tools for the Internship

This task involves setting up your environment with the required software tools. These tools are essential for working with **RISC-V architecture**, **VLSI design**, **simulation**, and **synthesis**.

### Tools to Install:

1. **Ubuntu 20.04 LTS on VirtualBox**
2. **RISC-V GNU Toolchain**
3. **GTKWave**
4. **Yosys**
5. **iVerilog Simulator**

---

### Step 1: Install Ubuntu 20.04 LTS on Oracle VM VirtualBox

Before installing the toolchain and other tools, you need to set up **Ubuntu 20.04 LTS** inside a **Virtual Machine** using **Oracle VirtualBox**.

1. **Download Oracle VirtualBox**:  
   Visit the official [Oracle VirtualBox download page](https://www.virtualbox.org/) and download the installer for your system (Windows/macOS/Linux).

2. **Download Ubuntu 20.04 LTS ISO**:  
   Go to the [Ubuntu official download page](https://releases.ubuntu.com/20.04/) and download the ISO file for **Ubuntu 20.04 LTS**.

3. **Create a New Virtual Machine**:
   - Open **Oracle VM VirtualBox** and click **New**.
   - Choose **Ubuntu (64-bit)** as the OS type.
   - Set up **2 GB of memory** and **20 GB of virtual hard disk** (or more).
   - Start the VM and choose the downloaded Ubuntu **ISO** as the boot medium.

4. **Install Ubuntu**:
   Follow the on-screen instructions to complete the installation of Ubuntu. Once finished, you will have a fully functional Ubuntu 20.04 LTS virtual machine.

---

### Step 2: Install RISC-V GNU Toolchain

The **RISC-V GNU Toolchain** is a critical tool for working with the **RISC-V architecture**, providing compilers and utilities for programming in **C** and **C++** for RISC-V.

#### Steps to install:

1. **Open a terminal** in Ubuntu.

2. **Clone the repository**:

   Clone the **RISC-V GNU Toolchain** GitHub repository using the following command:

   ```bash
   git clone https://github.com/riscv/riscv-gnu-toolchain.git
   ```

3. **Install dependencies**:

   Install the required build dependencies for the toolchain:

   ```bash
   sudo apt-get install autoconf automake autotools-dev curl python3 python3-pip libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev ninja-build git cmake libglib2.0-dev libslirp-dev
   ```

4. **Create directory for RISC-V toolchain**:

   Create a directory to install the toolchain (e.g., `/opt/riscv`):

   ```bash
   sudo mkdir /opt/riscv
   ```

5. **Configure the toolchain**:

   Go to the `riscv-gnu-toolchain` directory and run the configuration script:

   ```bash
   cd riscv-gnu-toolchain
   ./configure --prefix=/opt/riscv --with-arch=rv64i --with-abi=lp64 --enable-multilib
   ```

6. **Build the toolchain**:

   After configuration, build the toolchain:

   ```bash
   sudo make
   ```

7. **Add the toolchain to PATH**:

   Add the `riscv-gnu-toolchain` binaries to your PATH:

   ```bash
   gedit ~/.bashrc
   ```

   Add the following line at the end:

   ```bash
   export PATH="$PATH:/opt/riscv/bin"
   ```

   Save the file and apply the changes:

   ```bash
   source ~/.bashrc
   ```

8. **Verify the installation**:

   To check if the installation was successful, run:

   ```bash
   riscv64-unknown-elf-gcc --version
   ```

   If installed correctly, it will show the version of the RISC-V GCC compiler.

---

### Step 3: Install GTKWave (Waveform Viewer)

**GTKWave** is a waveform viewer used for viewing simulation results (such as from **iVerilog** or **Yosys**). 

1. Install GTKWave with the following command:

   ```bash
   sudo apt-get install gtkwave
   ```

   Once installed, you can open it from the terminal by typing:

   ```bash
   gtkwave
   ```

---

### Step 4: Install Yosys (RTL Synthesis Tool)

**Yosys** is an open-source synthesis tool that converts RTL designs into a netlist, ready for simulation or FPGA synthesis.

1. Install **Yosys**:

   ```bash
   sudo apt-get install yosys
   ```

2. Verify installation by running:

   ```bash
   yosys --version
   ```

---

### Step 5: Install iVerilog Simulator

**iVerilog** is a Verilog simulator used for simulating Verilog designs.

1. Install **iVerilog** with the following command:

   ```bash
   sudo apt-get install iverilog
   ```

2. Verify installation by running:

   ```bash
   iverilog -v
   ```

---

### Conclusion

Once all the above tools are installed, you will have a complete environment set up for your internship. The tools will help you with **RISC-V development**, **simulation**, and **synthesis**, which are essential tasks for your internship and VLSI-related work.

#### Tools Installed:
1. **Ubuntu 20.04 LTS** – A Linux-based OS.
2. **RISC-V GNU Toolchain** – For compiling and building RISC-V code.
3. **GTKWave** – For viewing simulation results.
4. **Yosys** – For synthesizing RTL designs.
5. **iVerilog** – For Verilog simulation.

---

This guide ensures that you have all the necessary tools installed and configured properly for your tasks related to RISC-V architecture and VLSI simulation and synthesis.
