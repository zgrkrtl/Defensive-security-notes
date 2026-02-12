# What Happens When You Run a Program

Running a program triggers several OS mechanisms: loading the binary, mapping memory, creating the process, initializing runtime, and enforcing privilege boundaries.

## The Role of the Loader

When execution starts, the OS loader prepares the binary:

- Parses executable headers (ELF / PE).
- Maps sections into virtual memory.
- Resolves dynamic imports (shared libraries / DLLs).
- Applies relocations if required.
- Sets the instruction pointer to the entry point.

Only after this setup does execution transfer to the program.

## Memory Mapping

The executable is mapped into a new virtual address space.

Typical layout:

- Code segment (`.text`) -> executable (RX).
- Data segment (`.data`, `.bss`) -> writable (RW).
- Heap -> dynamic allocations.
- Stack -> function calls and local variables.

Each region has specific memory permissions (R/W/X).  
Modern systems enforce non-executable data regions.

## Process Creation

Process creation differs across systems.

Linux:
- `fork()` duplicates the current process.
- `exec()` replaces its memory with a new program image.

Windows:
- `CreateProcess()` initializes a new process directly.

During creation:
- A PID is assigned.
- A new address space is created.
- Security context (credentials / token) is attached.
- Handles or descriptors may be inherited.

Resource inheritance can introduce unintended privilege interactions.

---

## Runtime Initialization

Before `main()` runs:

- The C runtime (CRT) initializes.
- Global constructors execute.
- Environment variables are prepared.
- Standard I/O and heap structures are set up.

`main()` is not the true beginning of execution.

---

## System Calls

User-mode programs cannot perform privileged operations directly.

To access system resources (files, memory, network, processes), a system call is made:

- CPU switches from user mode to kernel mode.
- Kernel validates and executes the request.
- Control returns to user mode.

This transition enforces a privilege boundary.

---

## User Mode vs Kernel Mode

Operating systems separate privilege levels:

- User Mode → restricted execution.
- Kernel Mode → full system privileges.

The CPU enforces this separation.

Kernel-level vulnerabilities impact the entire system.  
User-mode vulnerabilities are typically confined to the process context.

---

## Where Security Boundaries Exist

Security boundaries during execution include:

- Process memory isolation.
- User vs kernel mode separation.
- Access tokens and credential enforcement.
- File descriptor and handle restrictions.
- Memory permission enforcement (R/W/X).

Program execution is a chain of controlled transitions across these boundaries.
