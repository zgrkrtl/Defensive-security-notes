# Hashing vs Encryption

Hashing and encryption both transform data, but they are designed for different purposes.

The key difference:
- Hashing is one-way.
- Encryption is reversible.

They are not interchangeable.

## 1. One-Way vs Reversible

Hashing:

A hash function takes input and produces a fixed-length output.

Important properties:
- You cannot "undo" a hash.
- There is no key.
- The same input always produces the same output.

Example:
If you hash the word "password", you always get the same hash value.
But from the hash alone, you should not be able to reconstruct "password".

Encryption:

Encryption transforms data using a key.
With the correct key, the original data can be restored.

Example:
Encrypted message -> decrypt with key -> original message.

So:

Hashing = transform and forget original  
Encryption = transform and recover later  


## 2. Where Hashing Is Used

### Password Storage

When a user creates a password:

- The system hashes the password.
- Only the hash is stored in the database.

When logging in:
- The entered password is hashed again.
- The new hash is compared to the stored one.

The system never needs to know the original password again.

Salting:
A random value (salt) is added before hashing.
This prevents attackers from using precomputed hash tables.

Fast hashes like MD5 are dangerous for passwords because:
- Attackers can test billions of guesses per second.

Secure systems use slow algorithms (bcrypt, Argon2) to make brute force expensive.


### Data Integrity

If you download a file and the website provides a hash:

- You compute the hash of the downloaded file.
- If it matches, the file was not modified.

If even one bit changes, the hash changes significantly.

### Message Authentication

A hash combined with a secret key.

Used when:
- You want to ensure a message was not modified
- And confirm it came from someone who knows the secret key

## 3. Properties of Secure Hash Functions

A secure hash function should:

- Always produce the same output for the same input
- Make it impossible to recover the original input
- Make it extremely hard to find two different inputs with the same hash
- Change output drastically if input changes slightly

## 4. Why Hashing Is Not Encryption

Hashing:
- No key
- No way back

Encryption:
- Requires key
- Designed to reverse

If you need the original data again -> use encryption.
If you only need to verify it -> use hashing.
