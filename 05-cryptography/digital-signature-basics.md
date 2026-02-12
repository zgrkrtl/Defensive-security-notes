# Digital Signatures Basics

Digital signatures are about proving something,
not hiding something. It provides Integrity and Authenticity.

## How Signing Actually Works

Encryption is not signing.

Signing works as:

1. Take the data.
2. Hash it.
3. Encrypt the hash using the private key.
   -> This is the signature.

Now sent:
- Original data
- Signature

Verification process:

1. Receiver hashes the data again.
2. Receiver decrypts the signature using the public key.
3. Compare both hashes.

If they match:
- Data was not changed.
- It was signed by whoever owns the private key.

We sign the hash, not the full data.
It’s faster and standard practice.
