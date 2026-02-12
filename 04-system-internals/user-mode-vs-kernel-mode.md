# User Mode vs Kernel Mode

Modern operating systems enforce privilege separation between application code and the operating system core.

## Privilege Rings

Most CPUs implement privilege levels (ring model).

- Ring 0 -> highest privilege (kernel mode)
- Ring 3 -> lowest privilege (user mode)

Applications run in Ring 3.  
The kernel runs in Ring 0.

The separation exists to prevent user applications from:
- Accessing hardware directly
- Modifying kernel memory
- Executing privileged CPU instructions

Transitions between rings happen through controlled mechanisms (e.g., system calls, interrupts).

## Kernel Responsibilities

The kernel manages core system functions:

- Virtual memory management
- Process and thread scheduling
- File systems
- Network stack
- Device and hardware access
- Inter-process communication

All hardware interaction goes through the kernel.

User applications request these operations indirectly.

## Why Kernel Compromise Is Critical

If code executes in kernel mode:

- All memory can be accessed.
- All processes can be modified.
- Security mechanisms can be disabled.
- Privilege checks can be bypassed.

Kernel-level compromise typically means full system compromise.

User-mode protections (ASLR, DEP, sandboxing) become irrelevant once kernel control is achieved.

## Attack Surface at Kernel Level

Kernel attack surface includes:

- Device drivers
- System call interface
- IOCTL handlers
- Interrupt handling mechanisms
- Kernel modules / loadable extensions

Drivers are a common weak point due to:
- High complexity
- Direct hardware interaction
- Elevated privileges

Bugs in kernel components often lead to privilege escalation or full system takeover.
