# Encryption

Encryption transforms readable information into ciphertext using a key, so that only someone with the appropriate key can recover the original information. It is used to protect data in transit and data stored on devices or servers.

## Symmetric encryption

Symmetric encryption uses the same secret key to encrypt and decrypt. It can be efficient for large amounts of data, but the key must be shared and stored securely.

## Public-key cryptography

Public-key cryptography uses a related public and private key. The public key can be shared; the private key must be protected. These systems can support authentication, digital signatures, and key exchange. Secure network protocols such as TLS combine cryptographic techniques to establish a protected connection efficiently.

## Key management matters

Strong algorithms do not help if keys are exposed, reused incorrectly, or lost. Use well-reviewed libraries and platform services, keep secrets out of source code, restrict access, rotate keys according to a plan, and make backups when losing a key would mean losing data.

Encryption differs from hashing: encrypted data is meant to be decrypted with a key, while a cryptographic hash is intended as a one-way digest. See [HTTPS](../04-internet/https.md) and [Hashing](./hashing.md).
