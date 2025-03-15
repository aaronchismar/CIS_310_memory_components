# CIS_310_memory_components

1. Instruction Register (IR)
Design Choices:

4-bit register is used to hold the instruction fetched from memory before it is executed.
It can receive data from multiple sources (such as DRAM).

Multiplexer (MUX) is used to manage input sources, ensuring that the correct data is loaded into the register.
The instruction register is designed to store instructions temporarily before execution.

Three State buffers or control gates manage the data flow from DRAM into the instruction register.


Control Signals:

Load (LD): Controls when to load data into the instruction register.

Output Enable (OE): Manages when the contents of the instruction register should be sent to other



2. Program Counter (PC)
Design Choices:

4-bit Program Counter: 
A 4-bit register is used to store the current instruction address.
Increment Mechanism: The program counter increments automatically by adding 1 using a 4-bit adder circuit. The input to the adder consists of the current PC value and a constant binary 0001.

Multiplexer (MUX): A multiplexer is used to control whether the program counter should be loaded with a manually entered address (during a jump) or automatically incremented for sequential execution of instructions. The MUX allows selection between the incremented value (PC + 1) or the manually loaded value.

Control Signals:

CTRL (Control): This signal directs whether the PC should increment or load a new value. When CTRL = 0, the PC loads a new value. when CTRL = 1, it increments.

Clock (CLK): The program counter updates its value on the rising edge of the clock, either by incrementing or loading a new value depending on the control signal.

Reset (RST): The reset signal clears the program counter, setting it to 0000, which is used to initialize the execution from the start of the memory.

Adder: A 4-bit adder component is used to add 1 to the current PC value, providing the next instruction address during sequential execution.



3. General Purpose Register (GPR)
Design Choices:

Use of 4-bit registers: Each register stores a 4-bit value, providing a simple and efficient way to hold temporary data.

Multiplexing for register selection: A demultiplexer directs the control signals to the appropriate register based on the address input.

Register-based storage instead of DRAM: Unlike DRAM, which uses capacitors and requires refresh cycles, registers provide faster and more stable storage using flip-flops or latches.

AND gates for control logic: Logical AND gates ensure that only the selected register is enabled for writing.

Shared output BUS: The circuit uses a common bus for reading data, reducing the number of required connections and simplifying the design.
Control Signals:

CTRL (Control): Determines when data can be written into a specific register.

Input: Represents the data being stored into the selected register.

CLK (Clock): Synchronizes data storage operations and ensures that registers update only on the clock's rising edge.
Address: Selects the target register for reading or writing operations.

Output BUS: Provides a shared communication line for reading stored values from the selected register.


4. DRAM Module
   Design Choices:
   
4-bit wide, 16-address DRAM: The DRAM module is designed to store data and instructions, with 4-bit data words and a 16-address space. This makes it capable of storing both operands and instructions.

Addressable Memory: The memory can be accessed using the Address bus, which allows specific memory locations to be selected for read or write operations.

Multiplexer (MUX): A multiplexer controls which component provides input to the DRAM (for example, whether the input is coming from the program counter, registers, or another source).

Control Signals:

Several control signals are integrated to handle the different modes of operation (reading, writing, and selection).

Data Flow: The DRAM is connected to the Program Counter (for fetching instructions) and the Instruction Register (for storing fetched instructions). The DRAM also interfaces with general-purpose registers to store or retrieve operand values.





   

Test Results

General Purpose Register

<img width="941" alt="Screenshot 2025-03-14 at 10 05 05 PM" src="https://github.com/user-attachments/assets/5b95e6ab-6069-4708-9ab7-9f332cc6e155" />

Program Counter

<img width="882" alt="Screenshot 2025-03-14 at 10 08 03 PM" src="https://github.com/user-attachments/assets/257cbe45-4022-4f70-a297-616b3e7dca70" />

Instruction Register

<img width="893" alt="Screenshot 2025-03-14 at 10 08 51 PM" src="https://github.com/user-attachments/assets/eb484a9a-e350-4847-b24f-94ce04eef28d" />

DRAM Module 

<img width="925" alt="Screenshot 2025-03-14 at 10 18 36 PM" src="https://github.com/user-attachments/assets/ea640215-2ed2-4dc4-a357-352d8ceeb431" />

