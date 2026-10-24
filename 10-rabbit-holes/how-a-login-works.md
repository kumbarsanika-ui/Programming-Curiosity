# How does a login work?

A login is a sequence of checks and credential exchanges that lets an application recognize a user and decide what they can access. Details vary, but a secure design avoids storing passwords in plain text and checks permission on the server.

## 1. Account creation

When an account is created, the application validates the submitted information and stores a password verifier made with a password-hashing function and a unique salt. It should not store the raw password. See [Hashing](../07-security/hashing.md).

## 2. Sign-in

The user submits credentials over HTTPS. The server finds the account and verifies the submitted password using its stored verifier. It may also request a second factor, apply rate limits, or use other risk checks.

## 3. Session or token

After successful authentication, the application establishes a session. A browser might receive a cookie containing a protected session identifier; a service client might receive a token. Credentials should be transmitted and stored securely, have suitable lifetimes, and be invalidated when appropriate.

## 4. Authorization on later requests

The client sends its session credential with later requests. The server checks that the session is valid, identifies the account, and then evaluates whether that account is allowed to perform the requested action. Hiding a control in the user interface is not an authorization check.

## 5. Sign-out and recovery

Signing out should invalidate or expire the session as appropriate. Password reset must also be designed carefully: recovery links should be difficult to guess, time-limited, and single-use. Account recovery is part of account security, not an afterthought.

Authentication verifies identity; [authorization](../07-security/authorization.md) evaluates access. A login alone does not make every action safe or permitted.
