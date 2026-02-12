# How Executables Work

Executable structure defines how code is loaded, mapped into memory, and executed. 
Understanding binary layout is essential for reverse engineering, exploit analysis, and defensive inspection.


## What Is an Executable?

An executable is a binary file containing instructions that the CPU can directly execute.

It consists of:

- Machine code (CPU instructions)
- Metadata (headers, symbol tables, relocation info)
- Structured regions for code and data

Executables are platform-dependent:
- CPU architecture (x86, x64, ARM)
- Operating system format (ELF on Linux, PE on Windows)

Security relevance:
Binary format determines how memory is arranged and how execution flow can be influenced.

## ELF vs PE Basics

Different operating systems define different executable formats.

### ELF (Executable and Linkable Format)
- Used in Linux/Unix systems.
- Designed for modularity and flexible linking.
- Clearly separates sections (linking view) and segments (runtime view).

### PE (Portable Executable)
- Used in Windows systems.
- Derived from COFF format.
- Includes detailed metadata for the Windows loader and DLL handling.

Both formats contain:
- Headers (structural metadata)
- Sections (logical organization of data)
- Relocation and import information

Security perspective:
Malware analysis and exploit techniques depend heavily on format knowledge.

## Sections and Segments

Executables are divided into logical regions.

Common sections:

- `.text` -> executable instructions
- `.data` -> initialized global variables
- `.bss` -> uninitialized global variables
- `.rdata` -> read-only data (constants, strings)
- `.plt` / `.got` (ELF) -> dynamic linking structures

Segments represent how sections are mapped into memory at runtime.

Why sections matter:

- Each region has specific memory permissions (R/W/X).
- Overflows often target writable regions.
- GOT/PLT manipulation enables function redirection attacks.

Security takeaway:
Memory layout influences exploit feasibility.


## Entry Point

The entry point specifies where execution begins.

Important distinction:

- `_start` -> actual entry defined by the linker.
- `main` -> user-defined function called by runtime.

Before `main` executes:
- Runtime initialization occurs.
- Stack and heap are prepared.
- Shared libraries may be resolved.

Security relevance:
Packed or malicious binaries may redirect execution before reaching main logic.

## Imports and Exports

Modern binaries rely on external libraries.

Concepts:

- Shared libraries (`.so`) on Linux
- DLLs on Windows
- Import Address Table (IAT) in PE files

During loading:
- External symbols are resolved.
- Function addresses are written into tables.

Security relevance:

- IAT hooking allows function interception.
- DLL hijacking abuses search order.
- Import analysis reveals behavioral clues.

Dependencies increase attack surface.

## Static vs Dynamic Linking

### Static Linking
- Library code embedded directly into the binary.
- Larger file size.
- Fewer runtime dependencies.

### Dynamic Linking
- Libraries loaded at runtime.
- Smaller binary size.
- Shared code across processes.

Security implications:

- Dynamic linking introduces risks (DLL hijacking, library replacement).
- Static linking reduces dependency-based attacks but increases patching complexity.

Tradeoff:
Flexibility vs isolation.

## Why Executable Structure Matters for Security

Binary layout directly impacts:

- Code injection techniques
- Control flow manipulation
- Reverse engineering difficulty
- Runtime hooking
- Binary tampering

Understanding executable internals is foundational for:

- Exploit development analysis
- Malware detection
- Binary integrity verification

Security takeaway:
Executable format defines how software interacts with the operating system and how it can be manipulated.
