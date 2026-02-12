# TLS and Encryption in Transit

TLS protects data while it travels over networks.

It provides:
- Confidentiality
- Integrity
- Authentication
<-CIA Triad->

## 1. Why Encryption in Transition Matters

Without encryption:
- Credentials can be captured
- Sessions can be hijacked
- Data can be modified

Plaintext protocols are unsafe on untrusted networks.

## 2. TLS Handshake

Steps:
- Client hello
- Server hello
- Certificate exchange
- Key agreement
- Secure session established

Session keys encrypt traffic afterward.

## 3. What TLS Protects

TLS encrypts:
- Application data
- Headers

But still exposes:
- IP addresses
- Port numbers
- Server name
- Traffic timing and size

Metadata remains visible.

## 4. Certificate Trust

TLS relies on trusted Certificate Authorities (CA).

If:
- Certificate is invalid
- Certificate is self-signed
- CA is compromised

It is a security exposure.

Encryption reduces interception risk,
but does not eliminate attack surface.
