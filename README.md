# IC-Tester
# Universal Quad Logic Gate IC Tester

## 📌 Project Overview
This project implements a **universal digital IC tester** capable of verifying the correct functionality of **quad logic gate ICs** (ICs containing four identical logic gates).  
The tester automatically applies predefined input combinations to the IC under test and compares the actual outputs with expected outputs using a digital comparator. Based on the comparison result, the system provides a clear visual indication using LEDs.

This design is hardware-based and does **not require any microcontroller**, making it simple, reliable, and suitable for educational and laboratory use.

---

## 🎯 Features
- Tests **any quad logic gate IC** (AND, OR, NAND, NOR, XOR, XNOR, etc.)
- Uses **multiplexers** to generate fixed test input patterns
- Uses a **4-bit magnitude comparator** for output verification
- **Simultaneous testing** of all four internal gates
- Visual indication using **Green (PASS)** and **Red (FAIL)** LEDs
- Easily extendable to test other logic families

---

## 🧩 ICs Used
- **74LS153** – Dual 4×1 Multiplexer  
- **74HC86 / 7408 / 7432 / 7400 / 7402** – IC Under Test (any quad logic gate)  
- **7485** – 4-bit Magnitude Comparator  
- LEDs, resistors, power supply (+5V)

---

## ⚙️ Working Principle

### 1️⃣ Input Pattern Generation
Two multiplexers generate predefined logic input combinations:

- **MUX 1 output (Y1)** inputs: `0 0 1 0`
- **MUX 2 output (Y2)** inputs: `0 1 0 1`

All logic `0` inputs are connected to **GND** and logic `1` inputs are connected to **VCC**.  
Common select lines ensure synchronized input combinations.

---

### 2️⃣ IC Under Test
- The IC under test contains **four identical logic gates**.
- Each gate receives:
  - Input A = Y1
  - Input B = Y2
- Outputs are:



---

### 3️⃣ Expected Output Configuration
The expected 4-bit output depends on the **type of logic gate** being tested.  
These expected values are manually applied to the second input of the comparator.

| Logic Gate | Expected Output (Z1 Z2 Z3 Z4) |
|----------  |-------------------------------|
|   AND      |           0000                |
|    OR      |           0111                |
|   NAND     |           1111                |
|   NOR      |           1000                |
|   XOR      |           0110                |
|  XNOR      |           1001                |

---

### 4️⃣ Output Comparison & Indication
- A **7485 comparator** compares:
- Actual output (Z1–Z4)
- Expected output (configured manually)
- If outputs match:
- 🟢 **Green LED ON** → IC is **working correctly**
- If outputs do not match:
- 🔴 **Red LED ON** → IC is **faulty**

---

## 🧪 Simulation
The complete circuit is simulated using **Proteus Design Suite**, verifying correct operation for different logic gate ICs.  
Simulation files and schematic diagrams are included in this repository.


---

## 🚀 Applications
- Digital electronics laboratory testing
- Educational demonstrations
- Quick verification of logic ICs
- Mini-project for engineering students

---

## 📖 Conclusion
This project demonstrates an efficient and reusable approach to testing quad logic gate ICs using basic digital components. The modular design allows easy adaptation for different logic functions, making it a practical and educational digital electronics project.

---

