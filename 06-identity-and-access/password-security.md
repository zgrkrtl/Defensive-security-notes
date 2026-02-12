# Password Security

Passwords are everywhere.
They are also one of the weakest links.

Their security depends more on implementation than on the idea itself.

## Plaintext Storage = Total Failure

If passwords are stored in plaintext:
- A database breach exposes everything instantly
- Attackers gain access to other services (reuse problem)

There is no partial damage here.
Plaintext storage = full compromise.

Passwords must never be stored directly.

## Hashing

Passwords are stored as hashes, not as raw values.

Required properties:
- One-way (cannot reverse to original password)
- Computationally expensive
- Resistant to brute-force attacks

Designed-for-passwords algorithms:
- bcrypt
- Argon2
- scrypt

Fast hashes (MD5, SHA-1, SHA-256 alone) are unsafe for passwords.
Speed helps attackers.

Password hashing should be intentionally slow.

## Salting

Salt = unique random value per user.

Hash = hash(password + salt)

Why?
- Prevent rainbow tables
- Prevent identical hashes for identical passwords
- Force attackers to crack each password separately

Salts must be unique and are not a secret.

## Brute Force Reality

Attackers:
- Use GPUs
- Use distributed cracking rigs
- Use leaked databases
- Use credential stuffing automation

Defense is layered:
- Strong hashing algorithm
- High work factor
- Rate limiting
- MFA
- Account lockout controls

Hashing slows attackers.
It does not make cracking impossible.

## Password Reuse

Even perfect hashing cannot stop:

- Users reusing the same password elsewhere

If another service is breached:
Credential stuffing begins.

This is a human behavior problem,
not just a cryptographic one.

Passwords fail quietly.
Most systems are compromised long before noticed.