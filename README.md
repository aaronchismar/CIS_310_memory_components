# CIS_310_memory_components

1. Instruction Register (IR)
Design Choices:
A 4-bit register is used to hold the instruction fetched from memory before it is executed.
It can receive data from multiple sources (such as DRAM).
A multiplexer (MUX) is used to manage input sources, ensuring that the correct data is loaded into the register.
The instruction register is designed to store instructions temporarily before execution.
Tri-state buffers or control gates manage the data flow from DRAM into the instruction register.
Control Signals:
Load (LD): Controls when to load data into the instruction register.
Output Enable (OE): Manages when the contents of the instruction register should be sent to other



Test Results

General Purpose Register

<img width="941" alt="Screenshot 2025-03-14 at 10 05 05 PM" src="https://github.com/user-attachments/assets/5b95e6ab-6069-4708-9ab7-9f332cc6e155" />

Program Counter

<img width="882" alt="Screenshot 2025-03-14 at 10 08 03 PM" src="https://github.com/user-attachments/assets/257cbe45-4022-4f70-a297-616b3e7dca70" />

Instruction Register

<img width="893" alt="Screenshot 2025-03-14 at 10 08 51 PM" src="https://github.com/user-attachments/assets/eb484a9a-e350-4847-b24f-94ce04eef28d" />

DRAM Module 

<img width="925" alt="Screenshot 2025-03-14 at 10 18 36 PM" src="https://github.com/user-attachments/assets/ea640215-2ed2-4dc4-a357-352d8ceeb431" />

