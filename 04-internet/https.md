# HTTPS

HTTPS is HTTP carried over Transport Layer Security (TLS). It helps protect data traveling between a client and a server.

## What TLS provides

TLS can provide confidentiality, so observers on the network cannot ordinarily read the protected contents; integrity, so unauthorized changes can be detected; and server authentication, so the client can check that it is communicating with a server presenting a certificate valid for the requested domain.

During a TLS handshake, the client and server agree on cryptographic settings and establish keys for the connection. The details are handled by software such as a browser and server.

## What HTTPS does not guarantee

HTTPS does not prove that a website's claims are true, that its operator is ethical, or that the device is free of malware. It protects the connection to the domain being visited; it does not make every endpoint trustworthy.

Certificate warnings should not be casually ignored, because they can indicate a configuration problem or an unsafe connection. Websites should use current TLS configurations and renew certificates appropriately.

## The key idea

Use HTTPS to protect web traffic in transit. It complements, rather than replaces, secure application design, careful account handling, and [authentication](../07-security/authentication.md).
