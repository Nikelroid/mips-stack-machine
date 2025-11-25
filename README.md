# MIPS Stack Machine

![Language](https://img.shields.io/badge/Language-MIPS%20Assembly-red?style=flat&logo=assembly)
![Architecture](https://imgshields.io/badge/Architecture-MIPS32-00599C?style=flat)
![Emulator](https://img.shields.io/badge/Run_With-MARS%20Simulator-yellowgreen?style=flat&logo=java)
![OS](https://img.shields.io/badge/OS-Platform%20Agnostic-lightgrey?style=flat)

### 1\. Repository Description

A custom stack machine implemented in MIPS Assembly, featuring arithmetic operations, stack manipulation (push/pop), printing, and persistence via file save/load.

### 2\. Repository Tags

MIPS Assembly Stack Machine Emulator RISC MARS SPIM Computer-Architecture System-Programming File-IO Menu-Driven

-----

## 3\. README.md Content

# MIPS Stack Machine

A menu-driven, custom stack machine emulator written entirely in **MIPS Assembly Language**. This project demonstrates fundamental concepts of computer architecture, system programming, and low-level stack management, including persistence through file I/O operations.

### Requirements and Used System

Since this project is written in MIPS Assembly, it must be executed in a compatible MIPS simulator, such as MARS or SPIM.

-----

### Description

This project implements a custom stack machine, often used to process instructions in **Reverse Polish Notation (RPN)**. It is designed to run on a MIPS simulator (like MARS) and offers a command-line menu interface for user interaction.

The program dynamically allocates the stack memory (heap) at startup, based on user input, and manages the stack pointer (`$t8`) to handle push and pop operations. Critical error handling is implemented for stack overflow, stack underflow, invalid user input, and integer arithmetic overflow.

-----

### Features

The stack machine supports the following functionalities via a command menu (0-7):

  * **Exit (0):** Terminates the program cleanly.
  * **Push (1):** Prompts the user for an integer and pushes it onto the stack. Checks for stack overflow.
  * **Pop (2):** Removes the top element from the stack, prints its value to the console, and updates the stack pointer. Checks for stack underflow (empty stack).
  * **Print (3):** Iterates through the stack and prints all stored elements, each on a new line.
  * **Add (4):** Pops the top two elements, performs an integer addition, and pushes the result back onto the stack. Includes MIPS-specific overflow detection.
  * **Multiply (5):** Pops the top two elements, performs an integer multiplication, and pushes the result back onto the stack. Includes MIPS-specific overflow detection using `mfhi` (checking high-order word).
  * **Dump (6) / Save:** Saves the current contents of the stack to a user-specified file. The file content includes the stack elements as strings, followed by a `*` character and the total allocated stack size, enabling accurate restoration.
  * **Load (7):** Loads a stack from a user-specified file. It validates that the loaded stack size matches the program's initial heap size before populating the current stack.

-----

### Installation

#### Prerequisites

To run this project, you need a MIPS Assembly emulator. The most common choice in educational settings is **MARS (MIPS Assembler and Runtime Simulator)**, which is recommended.

#### Setup Instructions

1.  **Download the Emulator:** Obtain the latest version of MARS or SPIM.
2.  **Open the Source File:** Launch the emulator and open the `q8.asm` file.
3.  **Assemble:** In the emulator, use the "Assemble" or equivalent command (often the F3 key in MARS).
4.  **Run:** Execute the assembled program (often the F5 key in MARS).

-----

### Usage

Upon running, the program will prompt you to define the stack size:

```
Enter heap size:
```

**Note:** The heap size you enter must be a **positive integer divisible by 4** (since MIPS words are 4 bytes).

After initialization, the main menu will be displayed:

```
0: Exit
1: Push
2: Pop
3: Print
4: Add
5: Multiply
6: Dump
7: Load
Please enter your choice:
```

Enter the number corresponding to the desired operation.

#### Example Session (Push and Add)

1.  Enter `1` (Push).
2.  *Please enter number:* `10`
    *Done\!*
3.  Enter `1` (Push).
4.  *Please enter number:* `5`
    *Done\!*
5.  Enter `4` (Add).
    *(The stack pops 5 and 10, adds them to get 15, and pushes 15 back)*
    *Done\!*
6.  Enter `3` (Print).
    *15*

#### File I/O (Dump/Load)

  * **Dump (6):** You will be prompted for a filename (e.g., `mystack`). The program automatically appends `.txt` (e.g., `mystack.txt`) and saves the stack contents.
  * **Load (7):** You will be prompted for the saved filename. The program will only load the stack if the stack size encoded in the file matches the current allocated heap size.

-----

### Contributing

Contributions are welcome\! If you find a bug or have an idea for an improvement, please follow these steps:

1.  **Report Issues:** Open an issue to discuss the bug or proposed feature.
2.  **Fork the Repository:** Create a fork of the project.
3.  **Create a Branch:** Create a dedicated branch for your feature or fix (e.g., `feature/new-operation` or `fix/overflow-bug`).
4.  **Submit a Pull Request (PR):** Submit a pull request with a clear description of your changes.

-----

### License

This project is released under the **MIT License**.


-----

### Contact/Support

For questions or support, please contact the repository owner or open an issue on GitHub.

-----

You can start learning the fundamentals of the MIPS instruction set and assembly language by watching [You Can Learn MIPS Assembly in 15 Minutes](https://www.youtube.com/watch?v=5AN4Fo0GiBI).

http://googleusercontent.com/youtube_content/0
