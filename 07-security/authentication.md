# Authentication

Authentication is the process of checking who or what is making a request. A person may prove control of an account with a password, a passkey, or a second factor. A service may authenticate using a certificate or a scoped token.

## Authentication factors

Factors are often grouped as something you know (a password), something you have (a security key or phone), or something you are (a biometric). Using independent factors can make account takeover harder, though the security depends on the implementation and recovery process.

## Passwords

Applications should not store passwords in plain text. They should store password hashes created with a password-specific, deliberately slow hashing function and a unique salt. When someone logs in, the system hashes the submitted password and checks it against the stored verifier. See [Hashing](./hashing.md).

## Sessions and tokens

After successful authentication, an application may create a session or issue a token so the user does not need to prove their identity on every request. These credentials must be protected, expire appropriately, and be revoked or rotated when necessary.

Authentication answers “who are you?” It does not answer what that identity is allowed to do; that is [authorization](./authorization.md).
