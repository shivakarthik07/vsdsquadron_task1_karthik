# Task-1: Environment Setup and RISC-V Reference Bring-Upstep
## Step 1: Cloud Development Environment Setup 

### Task Completed
- Forked the reference RISC-V repository
- Launched a cloud-based development environment
- Verified that the environment built and opened successfully without errors
- Validated the availability of required tools and confirmed environment readiness

## Step 2: Verify RISC-V Reference Flow

### Task Completed
- Followed repository README instructions
- Compiled the fundamental RISC-V program
- Executed the program successfully
- Verified correct console output with no build or runtime errors

### Commands Used
```bash
cd samples
gcc sum1ton.c
./a.out
riscv64-unknown-elf-gcc -o sum1ton.o sum1ton.c
qemu-riscv64 sum1ton.o
```
### images
-<img width="1359" height="293" alt="riscv program execution" src="https://github.com/user-attachments/assets/b1ad8ee9-ecd8-4486-8c42-e8986daee8b0" />

## Step 3: Verify VSDFPGALABS 

### Task Completed
- Cloned the FPGA labs repository successfully
- Navigated to the lab directory
- Reviewed the available lab structure
- Verified repository accessibility and readiness for simulation-based labs

### Commands Used
```bash
git clone https://github.com/vsdip/vsdfpga_labs.git
cd vsdfpga_labs
ls
```
###images
<img width="1735" height="1058" alt="fpga labs check" src="https://github.com/user-attachments/assets/a0aafbbe-ca14-4d88-baba-b8ff494014cf" />
## Step 4: Modify Program Variable and Execute RISC-V Program
### Task Completed
- Accessed the sample RISC-V C program
- Modified the constant/variable value in the program
- Recompiled the program after modification
- Executed the updated program
- Verified that the output reflected the updated variable value
  ### Commands Used
```bash
cd samples
gedit sum1ton.c &
gcc sum1ton.c
./a.out
riscv64-unknown-elf-gcc -o sum1ton.o sum1ton.c
spike pk sum1ton.o
git clone https://github.com/vsdip/vsdfpga_labs.git
cd vsdfpga_labs
ls
```
### images
<img width="1229" height="665" alt="edited variable" src="https://github.com/user-attachments/assets/d73345d4-62e9-48c8-8ba8-bfdbe20a5647" />

## Step 5: PRINTING ASCII file

### Task completed
- Clone the lab repository
- Navigate to the firmware directory
- Generate BRAM hex file
- Compile C code for RISC-V (manual build)
- Run the program on Spike (RISC-V simulator)
### commands used
```bash
 git clone https://github.com/vsdip/vsdfpga_labs.git
 cd vsdfpga_labs/basicRISCV/Firmware
 make riscv_logo.bram.hex
 riscv64-unknown-elf-gcc -o riscv_logo.o riscv_logo.c
 spike pk riscv_logo.o
```
### images
<img width="904" height="855" alt="Screenshot 2025-12-20 210623" src="https://github.com/user-attachments/assets/53945ee6-77dd-4a6f-8c16-cd1fe0b09f7f" />
<img width="934" height="850" alt="Screenshot 2025-12-20 210611" src="https://github.com/user-attachments/assets/5a8700c3-d8cd-4504-b1f1-34d58634838e" />

## Step 6: INSTALLING LOCAL MACHINE(ubuntu22.04.05)
### Requirements to install virtual box
- RAM: 8 GB
- CPU: 2 cores
- Storage: 70 GB
### 1.Install Virtual Box from here
https://www.virtualbox.org/wiki/Downloads
### 2.Install ubuntu 22.04.05 from here
https://releases.ubuntu.com/jammy/
### Commands used
```bash
sudo apt update
sudo apt upgrade -y
```
### 3. Developement tools from docker file
### 1. Core Development Tools Installation
- Why These Tools : Required to compile firmware Needed for Makefile-based builds Used across all further steps
### Tools Installed
- git – version control
- gcc, g++ – C/C++ compilers
- make – build automation
- build-essential – core build package
- curl, wget – download utilities
- vim – editor
### Commands used
```bash
sudo apt install -y 
git curl wget vim 
build-essential gcc g++ make 
pkg-config
```
### 2. Build System Utilities 
- Why These Tools : Required by Spike and RISC-V ecosystem Used to generate portable build systems
### Tools Installed
- autoconf
- automake
- autotools-dev
- libtool
- pkg-config
### Commands used
```bash
sudo apt install -y 
autoconf automake autotools-dev libtool
```
### 3. Compiler & Parser Dependencies
- Why These Tools : Used in compiler front-ends required by GNU and RISC-V toolchains
### Tools Installed
- bison
- flex
- gawk
- gperf
- patchutils
- texinfo
### Commands used
```bash
sudo apt install -y 
bison flex gawk gperf 
patchutils texinfo
```
### 4. Math & Compression Libraries
- Why These Tools : Used internally by GCC and Spike ensure correct arithmetic operations
### Libraries Installed
- libgmp-dev
- libmpfr-dev
- libmpc-dev
- zlib1g-dev
- libexpat1-dev
### Commands used
```bash
sudo apt install -y 
libmpc-dev libmpfr-dev libgmp-dev 
zlib1g-dev libexpat1-dev
```
### 5. Device Tree & Hardware Support
- Why These Tools : Used in hardware configuration required for embedded system flows
### Tools Installed
- device-tree-compiler
- libfdt-dev
### Commands used
```bash
sudo apt install -y 
device-tree-compiler libfdt-dev
```
### 6. Installation of Simulation, Scripting, and RISC-V Execution Tools
### 1. Verilog Simulation Tools
- Icarus Verilog (iverilog) – Verilog compiler and simulator
- GTKWave (gtkwave) – Waveform viewer for debugging RTL simulations
- Used for : Compiling Verilog RTL,Viewing .vcd waveform files
### 2. Scripting & Automation Tools
- Python 3 (python3)
- Python package manager (pip3)
- Used for:Automation scripts,Build and preprocessing utilities in FPGA workflows
### 3. RISC-V Toolchain
- RISC-V GNU Compiler (gcc-riscv64-unknown-elf)
- Used for:Cross-compiling C programs for RISC-V architecture,Generating ELF binaries for simulation and hardware use.
### 4. RISC-V ISA Simulation Tools
- Spike – Official RISC-V ISA simulator
- Proxy Kernel (riscv-pk) – Runtime support for Spike
- Used for:Supporting Spike execution,Enabling GUI-based tools like GTKWave
  ### Commands used
```bash
sudo apt install -y 
iverilog gtkwave 
python3 python3-pip 
gcc-riscv64-unknown-elf 
spike riscv-pk 
libboost-regex-dev libboost-system-dev 
libx11-dev libxext-dev libxrender-dev 
libxpm-dev libxaw7-dev libcairo2-dev 
libfontconfig1-dev 
libreadline-dev libncurses-dev tcsh
```
### Verify tool installation
```bash
git --version
gcc --version
make --version
autoconf --version
automake --version
pkg-config --version
iverilog -V
gtkwave --version
python3 --version
pip3 --version
riscv64-unknown-elf-gcc --version
spike --version
```
### 7. Clone required repositories
```bash
git clone https://github.com/vsdip/vsd-riscv2.git
git clone https://github.com/vsdip/vsdfpga_labs.git
``` 
### 8. Sum1ton.c implementation
### use these commands
```bash
riscv64-unknown-elf-gcc -O2 -march=rv64imac -mabi=lp64 \
-o sum.elf sum.c
spike pk sum.elf
```
### 9. implementing logo(use qemu)(Note:spike is not supported in ubuntu)
### use these commands
```bash
cd vsdfpga_labs/basicRISCV/Firmware
riscv64-unknown-elf-gcc -O2 -march=rv64imac -mabi=lp64 \
-o riscv_logo.elf riscv_logo.c
qemu-riscv64 riscv_logo.elf
```




