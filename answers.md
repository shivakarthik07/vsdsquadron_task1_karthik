# Understanding Check – Task-1

## 1. Where is the RISC-V program located in the repository?
The fundamental RISC-V program is located in the `samples` directory of the reference RISC-V repository.

---

## 2. How is the program compiled and loaded into memory?
The program is compiled using the RISC-V cross-compiler `riscv64-unknown-elf-gcc`, which produces a RISC-V ELF binary.  
This binary is then loaded into memory and executed using a RISC-V simulator such as QEMU or Spike.

---

## 3. How does the RISC-V core access memory and memory-mapped IO?
The RISC-V core accesses memory using load and store instructions.  
Peripherals are accessed through memory-mapped IO, where specific address ranges correspond to hardware registers.

---

## 4. Where would a new FPGA IP block logically integrate in this system?
A new FPGA IP block would integrate as a memory-mapped peripheral connected to the system bus, allowing the RISC-V core to communicate with it using standard load/store operations.
