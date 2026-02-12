# Key Management and Trust

Good crypto is useless if keys are handled badly.
Most failures happen in key handling, not in algorithms.

## Key Generation

Keys come from randomness.

If randomness is weak -> keys become predictable.

Avoid using basic random functions or time-based seeds

Need cryptographic RNG.

Low entropy systems (VMs, embedded devices) can cause repeated keys.

## Key Storage

Private key leaking = game over.

Never:
- Hardcode keys in source
- Commit keys to Git

Better:
- Environment variables
- Secret managers / KMS
- HSM (hardware protection)
- Secure enclaves / TPM

Make key extraction difficult even if system is compromised.

## Key Rotation

Keys shouldn’t live forever.

If compromised:
- Damage window should be limited.

Short-lived certs > long-lived certs.
Rotate API keys.
Have a revocation plan.

Assume keys will leak eventually.

## Trust Models

Security depends on who you trust.

Centralized:
- CA model (browser trusts root CAs)

Web of trust:
- People sign each other’s keys (PGP)

Pre-shared key:
- Both sides already share secret

Core question:
Why do I trust this public key?

If trust assumption is wrong -> MITM possible.
