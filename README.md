# 🧠 8-Bit CPU Design & Simulation in Logisim Evolution  
**Course:** Digital Electronics (25BCE516)  
**Author:** Shlesha Modi  
**Institution:** Nirma University  
**Tool:** Logisim Evolution  

---

## 📝 Overview
This project demonstrates the design and simulation of a simple **8-bit CPU** built entirely in **Logisim Evolution**.  
It performs a complete **Fetch–Decode–Execute** cycle, showcasing how fundamental digital components form a working processor.

The CPU operates using a **Von-Neumann architecture**, with a shared 8-bit data and instruction bus.  
It includes core components like:
- **Program Counter (PC)**
- **Instruction Register (IR)**
- **Read-Only Memory (ROM)**
- **Register File (R0, R1)**
- **Arithmetic Logic Unit (ALU)**
- **Control Unit (CU)**

---

## ⚙️ Features
✅ Executes predefined instructions stored in ROM  
✅ Supports basic arithmetic and logic operations  
✅ Fully modular sub-circuit design  
✅ Real-time simulation of fetch, decode, and execute stages  
✅ Displays outputs on hex indicators for clarity  

---

## 🧩 CPU Specifications
| Component | Function |
|------------|-----------|
| **Program Counter (PC)** | Stores and increments address of next instruction |
| **Instruction Register (IR)** | Holds fetched instruction |
| **ROM** | Stores program (machine code) |
| **Registers (R0, R1)** | Temporary storage for operands and results |
| **ALU** | Performs arithmetic and logic operations |
| **Control Unit (CU)** | Generates control signals for all modules |

**Data Bus Width:** 8 bits  
**Address Bus Width:** 8 bits  
**Instruction Width:** 8 bits (4-bit opcode + 4-bit operand)

---

## 🧮 Supported Instructions
| Opcode | Mnemonic | Description |
|--------|-----------|-------------|
| `10h` | `LOAD R0` | Load data into R0 |
| `21h` | `LOAD R1` | Load data into R1 |
| `33h` | `ADD` | R0 ← R0 + R1 |
| `24h` | `SUB` | R0 ← R0 − R1 |
| `44h` | `AND` | R0 ← R0 & R1 |
| `25h` | `OR` | R0 ← R0 ∨ R1 |
| `55h` | `XOR` | R0 ← R0 ⊕ R1 |
| `26h` | `NAND` | R0 ← ¬(R0 & R1) |
| `66h` | `SHL` | R0 ← R0 << 1 |
| `27h` | `SHR` | R0 ← R0 >> 1 |
| `77h` | `MOV` | R0 ← R1 |
| `F0h` | `HALT` | Stop execution |

---

## 🚀 How It Works
1. **Instruction Fetch:**  
   Program Counter (PC) sends address to ROM → ROM outputs instruction → stored in IR.  
2. **Decode:**  
   Control Unit decodes opcode → generates control signals.  
3. **Execute:**  
   ALU or Registers perform the operation → result stored in R0.  
4. **Increment PC:**  
   PC advances to next instruction → cycle repeats until `HALT`.  

---

## 💾 Example Program (Stored in ROM)
| Address | Hex | Mnemonic | Description |
|----------|-----|-----------|-------------|
| 00 | 10 | LOAD R0 | Load data into R0 |
| 01 | 21 | LOAD R1 | Load data into R1 |
| 02 | 33 | ADD | Add R0 + R1 |
| 03 | 24 | SUB | Subtract R1 from R0 |
| 04 | 44 | AND | Bitwise AND |
| 05 | F0 | HALT | Stop execution |

---

## 🧠 ALU Operations
| ALUop | Operation | Symbolic Form |
|-------|------------|---------------|
| 000 | ADD | A + B |
| 001 | SUB | A − B |
| 010 | AND | A ∧ B |
| 011 | OR | A ∨ B |
| 100 | XOR | A ⊕ B |
| 101 | NAND | ¬(A ∧ B) |
| 110 | SHL | A << 1 |
| 111 | SHR | A >> 1 |

**Flags Generated:**  
- **Carry (C):** Overflow or borrow detection  
- **Zero (Z):** Set when result = 0  
- **Sign (S):** Copy of MSB of result  

---

## 🧭 Future Scope
🔹 Add Data Memory (RAM) for LOAD/STORE operations  
🔹 Implement Conditional Jumps (based on flags)  
🔹 Introduce Interrupts and Stack Pointer  
🔹 Add Pipelining for better performance  
🔹 Interface I/O devices (7-segment display, LEDs)  

---

## ⚠️ Limitations
❌ No RAM (ROM-only execution)  
❌ Single Bus architecture — limited throughput  
❌ No conditional branching  
❌ Hardwired Control Unit — not easily extendable  

---

## 📸 Demo
Full CPU Layout
> <img width="1588" height="579" alt="image" src="https://github.com/user-attachments/assets/1b190b9d-9eff-44b1-aa4d-3f270f82ab0d" />

Program Counter in Action
> <img width="546" height="156" alt="image" src="https://github.com/user-attachments/assets/0f3da154-7b4e-4507-ac81-bc69bdd58d72" />

ALU operation Example
> <img width="1203" height="563" alt="image" src="https://github.com/user-attachments/assets/1768155f-abb6-4f13-aa1c-578277959922" />
> <img width="221" height="256" alt="image" src="https://github.com/user-attachments/assets/dd4d47b2-7bb9-4a8f-868c-31259d7c3889" />

Instruction Fetch Unit
> <img width="957" height="197" alt="image" src="https://github.com/user-attachments/assets/aec8ea9a-1ed1-47f5-b1e3-a38dca6c4685" />

HALT instruction LED
> <img width="1596" height="567" alt="image" src="https://github.com/user-attachments/assets/ba6d5a99-17be-46db-a788-b3c26d8f0c61" />


---

## 🧑‍💻 How to Run
1. Download and install **Logisim Evolution**  
   [https://github.com/reds-heig/logisim-evolution](https://github.com/reds-heig/logisim-evolution)
2. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/8bit-cpu-logisim.git
3. Open 8bit_cpu.circ in Logisim Evolution.
4. Press Clock Tick to simulate instruction execution step-by-step.

---

## 🏁 Conclusion
This project successfully demonstrates the complete design of a functional 8-bit CPU using Logisim Evolution, integrating all the essential components of a processor.
It provides hands-on insight into digital design principles, instruction execution, and control signal generation — bridging theory with practical implementation.

---

## ⭐ Show your support
If you found this project helpful, please star ⭐ the repository on GitHub!
