# 🚀 Week 0 Report: Building the Digital Workbench

The inaugural week was focused on a critical first step: constructing a robust and reliable development environment. This involved provisioning a virtual machine and installing the core open-source toolchain required for digital VLSI design.

### Virtual Machine Specifications

An isolated Ubuntu environment was configured within VirtualBox to ensure stability and portability. The allocated resources are documented below.

| Parameter | Configuration |
| :--- | :--- |
| **Guest OS** | Ubuntu 24.04 LTS |
| **System Memory (RAM)** | 8 GB |
| **Processor Cores** | 4 vCPUs |
| **Storage (Virtual Disk)** | 50 GB (Dynamically Allocated) |

---

### EDA Toolchain Installation Log

The following section details the installation and verification of the essential components for our RTL design workflow.

#### 1. Yosys - Synthesis Engine

* **Function:** Yosys is the core synthesis tool that translates abstract Verilog RTL code into a concrete, optimized gate-level netlist.
* **Installation:**
    ```bash
    # Install dependencies
    sudo apt update && sudo apt install -y git build-essential clang bison flex libreadline-dev gawk tcl-dev libffi-dev graphviz xdot pkg-config python3 zlib1g-dev

    # Compile from source
    cd $HOME && git clone [https://github.com/YosysHQ/yosys.git](https://github.com/YosysHQ/yosys.git) && cd yosys
    make config-gcc && make && sudo make install
    ```
* **Verification Snapshot:**
    `yosys --version`
    

#### 2. Icarus Verilog - RTL Simulator

* **Function:** A trusted Verilog simulator for compiling HDL code and executing testbenches to verify design functionality.
* **Installation:**
    ```bash
    sudo apt install -y iverilog
    ```
* **Verification Snapshot:**
    `iverilog -V`
   

#### 3. GTKWave - Waveform Analyzer

* **Function:** An indispensable tool for graphically viewing and debugging digital waveforms (VCD files) produced during simulation.
* **Installation:**
    ```bash
    sudo apt install -y gtkwave
    ```
* **Verification Snapshot:**
    `gtkwave --version`
   

---

### Environment Status: Core Tools Ready

With the successful installation of the synthesis and simulation tools, the digital workbench is now operational. The system is prepared for the upcoming RTL design and verification tasks.

| Tool | Status | Primary Use |
| :--- | :--- | :--- |
| 🧠 **Yosys** | ✅ Complete | RTL Synthesis |
| 📟 **Iverilog** | ✅ Complete | Verilog Simulation |
| 📊 **GTKWave** | ✅ Complete | Waveform Viewing |
