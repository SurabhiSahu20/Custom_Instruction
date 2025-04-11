# Custom_Instruction
# 🛠️ CDAssg - Mini Compiler for Custom Instruction `VDOT3_BIAS`

A mini compiler built using C++ that performs lexical analysis, parsing, intermediate code generation, assembly translation, and opcode generation for a **custom vector dot product instruction**.

---

## 📌 What is `VDOT3_BIAS`?

`VDOT3_BIAS` is a custom instruction that performs a 3D vector dot product followed by a bias addition. Mathematically:


result = (a1 * b1 + a2 * b2 + a3 * b3) + bias


It is implemented in C++ as:

```cpp
inline int VDOT3_BIAS(int a1, int a2, int a3,
                      int b1, int b2, int b3,
                      int bias) {
    return (a1 * b1 + a2 * b2 + a3 * b3) + bias;
}

🗂️ Project Structure
CDAssg/
├── include/
│   └── vdot3_bias.hpp         # Header for VDOT3_BIAS
├── src/
│   ├── main.cpp               # Compiler driver
│   ├── vdot3_bias.cpp         # VDOT3_BIAS implementation
│   └── mini_compiler.exe      # Output binary (Windows)
├── utils/
│   ├── tokeniser.cpp          # Tokeniser implementation
│   └── tokeniser.hpp          # Tokeniser header
├── input.txt                  # Input instruction file
├── opcode.txt                 # Output: generated opcode
└── README.md                  # Project documentation

🧪 Sample Input
📄 Place this in your input.txt file:

VDOT3_BIAS 1 2 3 4 5 6 7

⚙️ How to Build & Run
✅ Make sure you're in the root CDAssg/ directory.

🔧 Step 1: Compile

g++ src/main.cpp src/vdot3_bias.cpp utils/tokeniser.cpp -o src/mini_compiler

🚀 Step 2: Execute

cd src
./mini_compiler

🧾 Sample Output (Terminal)

Tokens:
[VDOT3_BIAS, 1, 2, 3, 4, 5, 6, 7]

Parse Tree:
VDOT3_BIAS(
    a1=1, a2=2, a3=3,
    b1=4, b2=5, b3=6,
    bias=7
)

Three Address Code (TAC):
t1 = a1 * b1
t2 = a2 * b2
t3 = a3 * b3
t4 = t1 + t2
t5 = t4 + t3
t6 = t5 + bias
result = t6

Assembly Code:
MUL R1, a1, b1
MUL R2, a2, b2
MUL R3, a3, b3
ADD R4, R1, R2
ADD R5, R4, R3
ADD R6, R5, bias
MOV result, R6

Result: 74

Opcode (hex): 10 01 02 03 04 05 06 07
Opcode (bin): 00010000 00000001 00000010 00000011 00000100 00000101 00000110 00000111
Opcode written to ../opcode.txt ✅

🧾 Sample Output File: opcode.txt

Opcode (hex): 10 01 02 03 04 05 06 07
Opcode (bin): 00010000 00000001 00000010 00000011 00000100 00000101 00000110 00000111

✨ Features
✅ Tokenisation (Lexical Analysis)

✅ Syntax Validation and Parse Tree Generation

✅ Three Address Code (TAC) Generation

✅ Assembly Code Generation

✅ Binary & Hexadecimal Opcode Generation

✅ File Output (opcode.txt)

👨‍💻 Author
Surabhi Sahu
📘 Compiler Design - Assignment
📅 Year: 2025





