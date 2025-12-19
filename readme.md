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




