# Siemens S7-1200 / S7-1500 Modbus RTU Multi-Node Manager Library

An industrial-grade, bug-free, and highly optimized Modbus RTU Master solution for Siemens PLCs written in SCL and LAD (TIA Portal V16 to V21).

Developed by **Mahdi Sheikhi**.

---

## 📌 Overview & Description

The **Siemens S7-1200 / S7-1500 Modbus RTU Multi-Node Manager Library** is a production-ready communication framework for TIA Portal (V16 through V21). Managing Modbus RTU communication with multiple slaves (VFDs, energy meters, digital controllers) often leads to messy code, timeout conflicts, and compiler warnings. This library resolves those challenges by introducing a dynamic request-queue engine alongside specialized function blocks tailored for different data structures and hardware generations.

---

## 📥 Library Downloads

| TIA Portal Version | Hardware Gen | Universal Engine (All Types) | DirectINT Engine (Int / DInt Only) | Status |
| :--- | :--- | :--- | :--- | :--- |
| **TIA Portal V16** | G1 (Standard) | [Download Universal](./Libraries/V16/ModbusLibrary_Universal.zal16) | [Download INT](./Libraries/V16/ModbusLibrary_INT_.zal16) | ✅ Available |
| **TIA Portal V17** | G1 (Standard) | [Download Universal](./Libraries/V17/ModbusLibrary_Universal.zal17) | [Download INT](./Libraries/V17/ModbusLibrary_INT_.zal17) | 🔄 Coming Soon |
| **TIA Portal V18** | G1 (Standard) | [Download Universal](./Libraries/V18/ModbusLibrary_Universal.zal18) | [Download INT](./Libraries/V18/ModbusLibrary_INT_.zal18) | 🔄 Coming Soon |
| **TIA Portal V19** | G1 (Standard) | [Download Universal](./Libraries/V19/ModbusLibrary_Universal.zal19) | [Download INT](./Libraries/V19/ModbusLibrary_INT_.zal19) | 🔄 Coming Soon |
| **TIA Portal V20** | G1 (Standard) | [Download Universal](./Libraries/V20/ModbusLibrary_Universal.zal20) | [Download INT](./Libraries/V20/ModbusLibrary_INT_.zal20) | ✅ Available |
| **TIA V21 (G1)** | G1 (Standard) | [Download Universal G1](./Libraries/V21/G1/ModbusLibrary_Universal_G1.zal21) | [Download INT G1](./Libraries/V21/G1/ModbusLibrary_INT_G1.zal21) | ✅ Available |
| **TIA V21 (G2)** | G2 (Generation 2) | [Download Universal G2](./Libraries/V21/G2/ModbusLibrary_Universal_G2.zal21) | [Download INT G2](./Libraries/V21/G2/ModbusLibrary_INT_G2.zal21) | ✅ Available |

---

## 🌟 Key Features

* **Multi-Node & Multi-Request Engine:** Dynamic UDT array structure to handle multiple slaves seamlessly over a single RS-485 bus.
* **Dual-Engine Architecture:**
  * **Universal FB:** Raw Word/DWord exchange. Supports all types (`Real`, `DInt`, `Int`) via explicit conversion.
  * **DirectINT FB:** Native `INT`/`DINT` support with automatic 16-bit negative sign extension (`INT_TO_DINT(WORD_TO_INT(...))`).
* **Full S7-1200 G2 Support:** Dedicated compilation variants for both legacy S7-1200 (G1) and the latest S7-1200 Generation 2 (G2) controllers.
* **Zero Compiler Warnings:** Built using SCL Slice Access (`.%W0`, `.%W1`).
* **Word Swapping:** Built-in dynamic byte/word swapping for VFDs and energy meters.

---

## 📝 Usage Notes

> **Universal Block:**  
> Uses Word format for data exchange (supports all data types). Convert data to Word/DWord before sending or after receiving using the included converter blocks.

> **DirectINT Block:**  
> Supports Integer (`Int`/`DInt`) data types only. Floating-point (`Real`) data is not supported.
