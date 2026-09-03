# Static Analysis with Cutter

## 📌 Overview

This project documents my hands-on exploration of **Cutter**, an open-source reverse engineering platform, for performing static analysis of executable files.

For this project, I created a simple C program and compiled it into a **64-bit ELF executable**. I then analyzed the executable using Cutter to understand its internal structure and explore different reverse engineering features.

The analysis covers file information, strings, imports, functions, entry point, disassembly, graph view, decompilation, and cross-references.
<img width="1009" height="808" alt="cutter interface" src="https://github.com/user-attachments/assets/9477bd82-b10a-45f6-8ec7-fd5feeb64837" />


---

## 🎯 Objectives

- Understand ELF executable files
- Learn the basics of static binary analysis
- Explore executable file information
- Identify strings within a binary
- Analyze imported functions
- Identify functions and the program entry point
- Understand assembly instructions
- Visualize program control flow
- Explore decompiled C-like code
- Understand cross-references (Xrefs)
- Gain practical experience with Cutter

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| Kali Linux | Analysis environment |
| Cutter | Reverse engineering and binary analysis |
| GCC | C program compilation |
| C | Sample program |
| ELF | Executable file format |
| Linux Terminal | Command-line analysis |
| SHA-256 | File identification |

---

## 🧪 Sample Program

A simple C program was created for the analysis.

```c
#include <stdio.h>

int main() {
    printf("Hello World\n");
    return 0;
}
```

The program was compiled using GCC:

```bash
gcc main.c -o sarra
```

This created the executable:

```text
sarra
```

The file type was verified using:

```bash
file sarra
```

Example output:

```text
ELF 64-bit LSB executable, x86-64
```

---

## 🔐 SHA-256 Hash

The SHA-256 hash of the executable was calculated using:

```bash
sha256sum sarra
```

The hash provides a unique identifier for the analyzed file and can be used to verify file integrity.

---

# 🔍 Analysis Using Cutter

## 1. File Information

Cutter was used to examine information about the executable, including:

- File name
- File format
- Architecture
- Bitness
- File size
- Compiler information
- Security properties
- Entry point
- Checksums


---

## 2. Strings Analysis

The Strings window was used to identify readable strings stored inside the executable.

For example:

```text
Hello World
```

Strings can provide useful information about the contents and functionality of an executable.



---

## 3. Import Analysis

The Imports section was examined to identify functions imported from external libraries.

For example:

```text
printf
```

Imported functions can help understand which library functionality an executable uses.


---

## 4. Function Analysis

Cutter's Functions window was used to identify functions recognized during binary analysis.

Important functions include:

```text
main
entry0
```



---

## 5. Entry Point Analysis

The executable's entry point was examined to understand where program execution begins.



---

## 6. Disassembly

The `main` function was opened in the Disassembly view.

The disassembly represents the machine instructions generated from the original C program.

Example instruction types include:

```text
push
mov
lea
call
pop
ret
```

---

## 7. Graph View

Graph View was used to visualize the control flow of a function.

The graph represents:

- Basic blocks
- Branches
- Calls
- Execution paths
- Function flow


---

## 8. Decompiler

The Decompiler was used to display a higher-level C-like representation of the analyzed function.

This helps understand the relationship between the original source code and the compiled machine instructions.

```text
C Source Code
      ↓
Compiled Executable
      ↓
Assembly / Disassembly
      ↓
C-like Decompiled Code
```

---

## 9. Cross-References (Xrefs)

Cross-references were explored to determine where a particular function, string, or address is referenced within the executable.

For example:

```text
"Hello World"
       ↓
     printf()
       ↓
      main()
```
---

# 📚 Concepts Learned

Through this project, I gained practical exposure to:

- Reverse Engineering
- Static Binary Analysis
- ELF File Structure
- Executable Analysis
- Strings Analysis
- Import Analysis
- Function Analysis
- Entry Point Analysis
- Assembly Language
- Disassembly
- Control Flow Analysis
- Graph-Based Analysis
- Decompilation
- Cross-Reference Analysis
- SHA-256 File Identification
- Linux Binary Analysis

---

# 🚀 Applications of Cutter

Cutter can be used for:

- Reverse engineering
- Software analysis
- Static binary analysis
- Security research
- Vulnerability research
- Executable analysis
- CTF challenges
- Digital forensics
- Assembly language learning
- Understanding compiled applications
- Analyzing unknown executables in an isolated laboratory environment

---


# 📖 References

- [Cutter Documentation](https://cutter.re/docs/)
- [Cutter Features](https://cutter.re/docs/user-docs/features.html)

---

