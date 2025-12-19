# Task-1: Environment Setup and RISC-V Reference Bring-Up

---

## Step 1: Cloud Development Environment Setup (Mandatory)

### Task Completed
- Forked the reference RISC-V repository
- Launched a cloud-based development environment
- Verified that the environment built and opened successfully without errors

### Commands Used
_No commands required. The environment was built automatically._

### Evidence
![Cloud Environment Ready](images/step1_cloud_setup.png)

---

## Step 2: Verify RISC-V Reference Flow (Mandatory)

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
