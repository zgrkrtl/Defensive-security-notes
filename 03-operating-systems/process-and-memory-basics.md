# Process and Memory Basics

Understanding processes and memory management is essential for analyzing vulnerabilities, exploit techniques, and modern defense mechanisms.


## What Is a Process?

A process is a running instance of a program.

Key distinctions:
- A **program** is a static file on disk.
- A **process** is the active execution of that program in memory.

Each process has:
- A unique **Process ID (PID)**.
- Its own virtual address space.
- Allocated system resources (handles, threads, memory).

Modern operating systems enforce **process isolation**, meaning one process cannot directly access another process’s memory.

The CPU switches between processes using **context switching**, saving and restoring execution state.

Security relevance:
Breaking process isolation often leads to privilege escalation or code execution.


## Virtual Memory

Each process operates within its own **virtual address space**.

Key concepts:
- Virtual addresses are mapped to physical memory.
- The OS manages this mapping via paging.
- Memory is divided into pages.

Two important regions:
- **User space** → accessible by applications.
- **Kernel space** → reserved for the operating system.

Security relevance:
Memory isolation prevents processes from interfering with each other or the kernel.


## Stack vs Heap

Memory inside a process is organized into regions.

### Stack
- Stores function calls and local variables.
- Organized into stack frames.
- Grows and shrinks automatically.
- Short-lived memory.

### Heap
- Used for dynamic memory allocation.
- Managed manually (in C/C++) or by a garbage collector.
- Longer lifetime.

Security relevance:
Stack overflows and heap corruption are common exploitation vectors.

## Memory Permissions

Memory pages have permission flags:
- Read (R)
- Write (W)
- Execute (X)

Modern systems enforce:
- **NX bit (Non-Executable memory)** → prevents execution of data regions.

Executable stacks are dangerous because:
- Injected shellcode can be executed directly.

Security principle:
Data should not be executable.

## Why Memory Corruption Matters

Memory corruption occurs when a program:
- Writes outside allocated bounds (buffer overflow).
- Uses memory after it is freed (use-after-free).
- Dereferences invalid pointers.

Impact:
- Crash (Denial of Service)
- Information disclosure
- Arbitrary code execution

Memory corruption is a primary root cause of critical vulnerabilities.

## Modern Memory Protections

Operating systems implement mitigations:

- **ASLR** → Randomizes memory layout.
- **DEP** → Prevents execution of non-executable memory.
- **Stack canaries** → Detect stack corruption before function return.
- **Control Flow Integrity** → Restricts unexpected control transfers.

These do not eliminate bugs but make exploitation harder.

## Why Memory Safety Is a Security Problem

Languages like C and C++ allow:
- Manual memory management.
- Direct pointer arithmetic.

This increases risk of:
- Out-of-bounds access
- Use-after-free
- Double free

Memory-safe languages reduce these classes of vulnerabilities by enforcing safety guarantees at compile time.

Security takeaway:
Memory safety is one of the largest root causes of software vulnerabilities.
