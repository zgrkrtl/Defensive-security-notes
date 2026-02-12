# Authentication vs Authorization

Authentication → who are you  
Authorization → what can you do  

Mixing them up causes real security issues.

## Authentication

Prove identity.

Common methods:
- Password
- MFA / OTP
- Tokens (JWT, session cookies)
- Certificates
- Biometrics

Authentication only answers:
"Is this really you?"

It does NOT automatically mean:
"You can access everything."

You can be authenticated and still not authorized.

## Authorization

Happens after authentication.

Now the system asks:
"What is this identity allowed to access?"

Examples:
- Can user read this file?
- Can this API key access this endpoint?
- Can this process open this port?

Authorization is policy enforcement.

Authentication = identity established  
Authorization = access decision made

## Access Control Models

RBAC:
Access based on roles.
- Admin
- User
- Auditor
Simple, common in enterprise systems.

ABAC:
Access based on attributes.
- User department
- Time of day
- Resource sensitivity
- IP address

ABAC is more flexible and more complex.

## Broken Authorization

Auth can be perfect.
System can still be insecure.

Common issues:
- IDOR (changing object IDs in URLs)
- Privilege escalation
- Over-permissioned service accounts

Most real-world breaches are authorization failures,
not authentication failures.
