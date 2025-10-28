# 8-bit ALU in VHDL (Behavioral Modeling)

This project implements an **8-bit Arithmetic Logic Unit (ALU)** using **behavioral modeling** in VHDL. The ALU supports a wide range of arithmetic and logical operations and is fully testable through simulation in **Xilinx ISE Design Suite**.

---

## 🔧 Project Overview

- **Design Name**: `bit_8_alu_be`
- **Modeling Style**: Behavioral
- **Language**: VHDL
- **Tool**: Xilinx ISE Design Suite
- **Project Type**: Combinational Logic ALU

---

## 🎯 Features

The ALU performs the following 8 operations based on a 3-bit control input (`inp`):

| `inp` | Operation   | Description               |
|-------|-------------|---------------------------|
| `000` | `A + B`     | Addition                  |
| `001` | `A - B`     | Subtraction               |
| `010` | `A >> 1`    | Logical Right Shift by 1  |
| `011` | `A << 1`    | Logical Left Shift by 1   |
| `100` | `A XOR B`   | Bitwise XOR               |
| `101` | `NOT A`     | Bitwise NOT of A          |
| `110` | `A AND B`   | Bitwise AND               |
| `111` | `A OR B`    | Bitwise OR                |

---

## 🧩 File Structure

| File Name        | Description                        |
|------------------|------------------------------------|
| `bit_8_alu_be.vhd` | ALU module written in behavioral VHDL |
| `alu_tb.vhd`     | Testbench for validating ALU behavior |

---

## 🔍 How It Works

- Inputs:
  - `a`, `b`: 8-bit operands
  - `inp`: 3-bit control signal to select the ALU operation
- Output:
  - `y`: 8-bit result of the selected operation

The logic is implemented using a **VHDL process block**, making decisions based on the `inp` value to compute the result on output `y`.

---

## 🛠️ How to Simulate (Xilinx ISE)

1. Create a new project in Xilinx ISE.
2. Add the following files:
   - `bit_8_alu_be.vhd`
   - `alu_tb.vhd`
3. Set `alu_tb` as the **top-level module**.
4. Click **"Simulate Behavioral Model"**.
5. Observe the waveform output for each operation based on control input.

---

## 🧪 Testbench Behavior

The testbench (`alu_tb.vhd`) stimulates the ALU with the following:

- Operands:
  - `a = 00001111`
  - `b = 00000111`
- Sequentially applies `inp` values from `"000"` to `"111"` every 10 ns.
- Outputs are stored in `y`.

This confirms correct functioning of all supported ALU operations.

---

## 🖥️ Sample Simulation Output (Conceptual)

| inp | Operation | Expected `y` Output (for a = 0F, b = 07) |
|-----|-----------|-------------------------------------------|
| 000 | A + B     | `00010110` (0F + 07 = 16)                |
| 001 | A - B     | `00001000` (0F - 07 = 08)                |
| 010 | A >> 1    | `00000111` (0F >> 1 = 07)                |
| 011 | A << 1    | `00011110` (0F << 1 = 1E)                |
| 100 | A XOR B   | `00001000`                               |
| 101 | NOT A     | `11110000`                               |
| 110 | A AND B   | `00000111`                               |
| 111 | A OR B    | `00001111`                               |

*Note: Values are in binary/hex format as per VHDL interpretation.*
