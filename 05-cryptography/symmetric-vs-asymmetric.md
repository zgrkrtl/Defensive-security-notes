# Symmetric vs Asymmetric Cryptography

There are two main approaches in cryptography.

They solve different parts of the problem.


## Symmetric Cryptography

One key.
Same key encrypts and decrypts.

If I encrypt with key X,
you must also have X to decrypt.

This approach is very fast. Good for encrypting large amounts of data.(AES, ChaCha20)

Main issue:
How do we securely share the key in the first place?

If someone intercepts the key,
encryption is useless.

## Asymmetric Cryptography

Uses a key pair:
- Public key (can be shared)
- Private key (must stay secret)

What is encrypted with one
can only be decrypted with the other.

Main benefits:
- Secure key exchange
- Digital signatures
- Identity verification

RSA, ECC

Much slower than symmetric encryption.

Not ideal for encrypting large files directly.

## Hybrid Model

Modern systems combine both.

Typical flow:
1. Use asymmetric crypto to securely exchange a symmetric key.
2. Use that symmetric key for the rest of the communication.

So:

Asymmetric -> setup phase  
Symmetric -> data phase  

This gives both security and performance.

## TLS

When you open an HTTPS website:

1. Client connects.
2. Server sends certificate (proves identity).
3. Key exchange happens (asymmetric).
4. Both sides derive a shared session key.
5. All further communication uses symmetric encryption.

TLS uses:
- Asymmetric crypto -> authentication + key exchange
- Symmetric crypto -> actual data encryption
- Hashing -> integrity checks
