# Microprocessor Project

## Overview
This project focuses on designing and implementing a simple microprocessor, often referred to as a "brainless CPU." The development process involves digital logic design, circuit simulation, and Verilog-based implementation. The project is structured into multiple stages, each focusing on different components that contribute to the overall functionality of the microprocessor.

## Project Highlights
- **Digital Logic Mastery**: Implemented fundamental logic components, including adders, multiplexers, and registers.
- **Verilog Implementation**: Designed and simulated hardware logic using Verilog.
- **ROM-based Controller**: Created a finite-state machine (FSM) to control the CPU.
- **Memory and Instruction Set**: Implemented RAM, ROM, and an instruction set for program execution.
- **Interactive Debugging**: Utilized GTKWave for waveform analysis and debugging.

## Project Structure
### **1. Laying the Foundation**
- Built a **4-bit incrementor** for the Program Counter (PC) using half and full adders.
- Verified functionality using waveform analysis.

### **2. Flow and Function**
- Designed a **4-bit 2-to-1 multiplexer** for controlled data flow.
- Developed an **Arithmetic Logic Unit (ALU)** supporting operations such as:
  - Addition
  - Subtraction
  - Logical operations (NOT, NEG, AND)
- Integrated these components into a functioning processing unit.

### **3. Storage and Instructions**
- Implemented a **4-bit accumulator** for storing temporary results.
- Created a **Program Counter (PC)** to track instruction execution.
- Integrated **16-word 4-bit RAM** for storing both instructions and data.
- Preloaded instructions using a **ram_vals.hex** file.

### **4. Building the Complete Microprocessor**
- Defined an **instruction set** and programmed basic operations.
- Developed a **Memory Address Generator (MAG)** for efficient instruction fetching.
- Designed a **ROM-based controller** to handle instruction execution via finite state logic.
- The microprocessor executes instructions by:
  - Fetching opcodes from ROM.
  - Using a control unit to generate appropriate signals.
  - Performing arithmetic/logical operations based on the instruction set.

## Key Components
### **Hardware Modules**
- **Arithmetic Logic Unit (ALU)**
- **Registers and Counters** (Program Counter, Accumulator, Memory Address Register)
- **Multiplexers and Decoders**
- **Instruction ROM & Program RAM**
- **Finite-State Machine Controller**
- **Memory Address Generator**

### **Instruction Set**
- **LOAD ACC**: Loads a value into the accumulator.
- **ADD ACC**: Adds a value to the accumulator.
- **STOP**: Halts execution.
- **AND**: Performs a bitwise AND between the accumulator and an operand.
- **ZERO**: Resets the accumulator to zero.
- **SUB**: Subtracts a value from the accumulator using two’s complement.
- **STORE ACC**: Stores the accumulator’s value into memory.

## Simulation and Testing
- **Digital Simulation**: Used the **Digital** logic simulator to design and test the circuits.
- **Verilog Simulation**: Exported the design to **Verilog** and tested it using **GTKWave**.
- **Waveform Analysis**: Verified execution using waveform outputs.

## Getting Started
### **Prerequisites**
- **Digital**: Install the **Digital** schematic entry tool.
- **Verilog & Icarus Verilog**: Install Icarus Verilog for HDL simulation.
- **GTKWave**: Install GTKWave for waveform visualization.

### **Running the Simulation**
#### **Digital Simulation**
1. Open the project in **Digital**.
2. Load the circuit files.
3. Run the simulation and verify output waveforms.

#### **Verilog Simulation**
1. Compile the Verilog files:
   ```sh
   iverilog -o microprocessor.exe microprocessor.v micro_top.v micro_stim.v
   ```
2. Run the compiled executable:
   - On Mac:
     ```sh
     ./microprocessor.exe
     ```
   - On Windows:
     ```sh
     vvp microprocessor.exe
     ```
3. View the simulation results using **GTKWave**.

## File Structure
```
/Microprocessor
│── alu.dig                # Arithmetic Logic Unit design
│── brainless.dig          # Core CPU without control logic
│── controller.dig         # ROM-based finite-state machine
│── four_bit_adder.dig     # 4-bit adder circuit
│── four_bit_mux.dig       # 4-bit multiplexer
│── incrementer.dig        # Incrementer for program counter
│── program_ram.dig        # RAM module
│── microprocessor.v       # Verilog implementation
│── micro_top.v            # Top-level Verilog module
│── micro_stim.v           # Testbench for simulation
│── ram_vals.hex           # Program memory contents (Hex)
│── rom_vals.hex           # ROM contents for instruction decoding
│── README.md              # Project documentation
```

## Future Enhancements
- Expanding the **instruction set** for additional operations.
- Implementing **branching and conditional logic**.
- Adding support for **more complex programs** in memory.

## Acknowledgments
This project is inspired by digital design principles and microprocessor architecture concepts. Special thanks to the tools and frameworks that made this project possible.

