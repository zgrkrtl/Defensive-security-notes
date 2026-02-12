# Common Cryptography Mistakes

Crypto usually fails in implementation, not math.

## Using Broken Algorithms

- MD5 for passwords
- SHA1 for signatures
- Custom “home-made” crypto

If algorithm is deprecated, don’t use it.
There is no “but it’s internal only”.

## Rolling Your Own Crypto

Designing your own cipher = bad idea.

Even small mistakes break security completely.

Use well-reviewed libraries.
Do not implement AES yourself.

## No Salting for Passwords

Hash only -> bad.

Without salt:
- Same passwords -> same hash
- Rainbow tables work

Correct:
hash(password + unique_salt)


## Using Fast Hashes for Passwords

SHA256 is fast.
Fast = good for attackers.

Use slow hash:
- bcrypt
- Argon2
- scrypt

To make brute force expensive!

## Hardcoding Keys

Keys in source code -> leak sooner or later.

Especially in:
- Mobile apps
- Git repos
- Client-side JS

Assume attackers can read your code.

## Reusing Keys Everywhere

Same key for:
- Encryption
- Signing
- Multiple environments

Bad separation.

Compromise in one place -> compromise everywhere.


## No Authentication (Encryption Only)

Encrypting without authentication
-> vulnerable to tampering.

Need:
Authenticated encryption (AES-GCM, ChaCha20-Poly1305)

Encryption alone is not integrity.

## Not Verifying Certificates Properly

Skipping TLS verification
or accepting all certificates

Common in dev code.
Extremely dangerous in prod.

## Weak Randomness

Using:
- predictable seeds
- timestamps
- non-crypto RNG

Keys must come from cryptographic randomness.

## Ignoring Key Rotation

Long-lived keys increase damage window.

Have revocation and rotation strategy.

## Storing Private Keys Unprotected

Plaintext private keys on disk.
No passphrase.
No HSM.

If attacker gets private key:
security is failed.

