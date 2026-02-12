# Dynamic Linking and Runtime Behavior

Modern programs often rely on external libraries that are loaded at runtime instead of embedding all code statically.

## Shared Libraries

Shared libraries allow multiple programs to reuse common functionality.

Linux:
- `.so` files
- `dlopen()` for runtime loading

Windows:
- `.dll` files
- `LoadLibrary()` for runtime loading

At runtime:
- The loader resolves external symbols.
- Function addresses are written into internal tables.
- Calls to external functions are redirected through these resolved addresses.

Dynamic loading can also occur explicitly during execution (not only at startup).

## Procedure Linkage Table (PLT)

(ELF)

The PLT is used for indirect function calls to dynamically linked libraries.

- Initial call goes through PLT stub.
- Resolver determines actual function address.
- Address is stored for future calls.

This allows lazy binding (resolve on first use).

## Global Offset Table (GOT)

(ELF)

The GOT stores resolved addresses of external functions and global variables.

- After resolution, GOT entries point to real function addresses.
- PLT entries reference the GOT.

If GOT entries are writable, they become potential targets for redirection attacks.

## DLL Hijacking (Conceptual)

On Windows, if a program loads a DLL without specifying a full path:

- The OS searches for the DLL using a defined search order.
- If an attacker places a malicious DLL earlier in the search path,
  it may be loaded instead of the legitimate one.

This leads to execution of attacker-controlled code within the program’s context.

## Library Search Order Issues

Both Linux and Windows rely on search paths for shared libraries.

Examples:

- Current working directory
- System directories
- Environment variables

Improper search path handling can allow:
- Library replacement
- Preloading attacks
- Execution hijacking

## Why Dynamic Linking Is a Security Concern

Dynamic linking introduces:

- External dependencies
- Runtime symbol resolution
- Indirect control flow

Risks include:

- Function pointer redirection
- Import table manipulation
- DLL hijacking
- LD_PRELOAD abuse (Linux)

The executable’s behavior depends partly on external libraries and loader decisions.
