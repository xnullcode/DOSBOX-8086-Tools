# 8086 Assembly Language Development Kit

A curated collection of classic MS-DOS tools for writing, assembling, linking, and debugging Intel 8086 Assembly Language programs. This environment provides everything you need to start programming for the x86 16-bit architecture, commonly used in computer organization and assembly language courses.

Note: These are native 16-bit MS-DOS binaries. They cannot run directly on modern 64-bit operating systems (Windows 10/11, macOS, Linux). You must use an emulator like DOSBox or MS-DOS Player to execute them.

---

## Included Tools

### Assemblers & Linker
*   **MASM.EXE (Microsoft Macro Assembler):** Translates your human-readable assembly source files (.ASM) into machine code object files (.OBJ).
*   **TASM.EXE (Turbo Assembler):** Borland's high-speed alternative to MASM. Functions similarly but supports different macro structures and optimized configurations.
*   **LINK.EXE:** The linker utility. Combines one or more .OBJ` files together to generate a final executable (.EXE).

### Format Converters
*   **EXE2BIN.EXE:** Converts an .EXE file into a flat, raw binary file (typically .COM). Ideal for programs constrained to a single 64KB memory segment.
*   **BIN2HEX.EXE:** Converts raw binary code into Intel Hexadecimal ASCII format, usually required for burning code directly onto physical EPROM chips.

### Editors & Debuggers
*   **EDIT.COM:** The classic full-screen MS-DOS text editor used to write and modify your .ASM source code directly inside the environment.
*   **DEBUG.EXE:** A minimalist, command-line debugger to inspect memory, modify registers, and step through instruction sets line-by-line.
*   **TD.EXE (Turbo Debugger):** Borland's advanced graphical debugger. Features full-screen windows to easily track the CPU stack, memory segments, and registers (AX, BX, CX, DX) simultaneously.

---

## Quick Start Guide (Using DOSBox)

### 1. Prerequisites
Download and install DOSBox for your operating system.

### 2. Setting Up Your Workspace
1. Create a local folder on your computer (e.g., C:\8086).
2. Clone this repository or copy all files from this directory straight into that folder.
3. Create your assembly source file inside the same folder (e.g., hello.asm).

### 3. Mounting the Drive in DOSBox
Open DOSBox and run the following commands to mount your local folder and access the tools:

```assembly
mount c c:\8086
c:
```

### 4. Assembling and Linking (Example Workflow)

To compile a basic program using TASM, run the following sequence in DOSBox:

```bash
# 1. Assemble the source code into an object file
tasm hello.asm

# 2. Link the object file into an executable program
link hello.obj

# 3. Run your program
hello.exe
```

*If you prefer using MASM, simply swap tasm hello.asm with masm hello.asm.*

### 5. Debugging Your Code
To step through your execution flow visually using Turbo Debugger:

```bash
td hello.exe
```

---

## Quick Tips
*   **EDIT.COM Interface:** If your mouse cursor isn't working inside EDIT.COM or TD.EXE, press Ctrl + F10 in DOSBox to lock your mouse to the emulator window.
*   **Case Insensitivity:** MS-DOS commands and tool arguments are completely case-insensitive (tasm code.asm works exactly the same as TASM CODE.ASM).
