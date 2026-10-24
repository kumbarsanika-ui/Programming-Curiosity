# Hashing

A cryptographic hash function transforms input data into a fixed-size output called a digest. The same input produces the same digest, but a well-designed cryptographic hash makes it impractical to reconstruct the original input or find a different input with the same digest.

## Uses

Hashes can help verify that a file has not changed, identify data, and build digital signatures. They are also part of password storage, but ordinary fast hashes such as SHA-256 are not suitable by themselves for storing passwords.

## Password hashing

Passwords are often short and guessable, so password storage needs extra defenses. Use a password-hashing algorithm such as Argon2id, scrypt, or bcrypt, with a unique random salt for each password and an appropriately configured work factor. A salt is not secret; it prevents identical passwords from having identical stored values and defeats precomputed lookup tables.

When verifying a login, use the password-hashing library's verification function rather than implementing the algorithm yourself. Never store or log the original password. See [Authentication](./authentication.md).

## Hashing is not encryption

A hash is intended to be one-way; encryption is designed to be reversed by someone with the appropriate key. If data must later be recovered, hashing is not a replacement for encryption. See [Encryption](./encryption.md).
