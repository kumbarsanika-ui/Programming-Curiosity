# Security: challenge answers

## Questions 71–80: Security curiosity

### 71. How does a website know who you are after login?

The server verifies the credentials during login and creates a session or issues a token. The browser sends that credential with later requests; the server validates it and associates the request with an account. The credential should be protected, expire appropriately, and be revocable.

### 72. Where is your password stored?

In a well-designed service, the password itself is not stored. The service stores a salted password hash created with a password-specific algorithm such as Argon2id, scrypt, or bcrypt. The verifier is stored in a protected database; access to it must still be restricted.

### 73. Why shouldn’t passwords be stored as plain text?

If the database is exposed, plain-text passwords immediately reveal users' credentials, including passwords reused on other sites. A unique salt and deliberately slow password-hashing function make large-scale guessing more expensive and prevent simple precomputed lookups. Passwords should never be logged either.

### 74. What is encryption?

Encryption transforms readable data into ciphertext using a key. Someone with the appropriate key can decrypt it. Symmetric encryption uses a shared secret; public-key systems use related public and private keys for tasks such as authentication and key establishment.

### 75. What is hashing?

A cryptographic hash maps input data to a fixed-size digest and is designed to be difficult to reverse or collide. Hashes help verify data and support signatures. Passwords require specialized slow password-hashing algorithms; a fast general-purpose hash alone is inadequate.

### 76. What happens if someone changes an API request?

The server must treat every request as untrusted. It should validate input, authenticate the caller, check authorization for the specific resource and action, and enforce business rules. HTTPS detects in-transit tampering but cannot stop a user from editing a request before sending it.

### 77. What is CORS?

Cross-Origin Resource Sharing is a browser mechanism that lets a server state which web origins may read certain cross-origin responses. Browsers enforce the server's CORS response headers. CORS is not authentication or authorization and does not prevent non-browser clients from sending requests.

### 78. How does a server know whether you are authorized?

It validates the caller's session or token to establish an identity, then evaluates permissions for the requested action and resource. Checks should be server-side on every sensitive operation and should include ownership or scope where relevant. Authentication alone does not grant access.

### 79. What is a token?

A token is a credential or data structure used to represent claims or permissions. Bearer tokens grant access to whoever possesses them, so they must be protected in transit and storage, scoped, and given suitable lifetimes. A token's format does not make it trustworthy unless it is properly validated.

### 80. How can one careless line of code expose millions of users?

A mistake in access control, query construction, secret handling, logging, or configuration can expose data across many accounts. Shared software and automated deployment amplify the impact. Layered defenses include code review, least privilege, parameterized queries, automated tests, monitoring, and a practiced incident-response plan.

## Follow the trail

Read [authentication](./authentication.md), [authorization](./authorization.md), [hashing](./hashing.md), and [encryption](./encryption.md). The [login walkthrough](../10-rabbit-holes/how-a-login-works.md) connects these ideas.
