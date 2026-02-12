# Authentication and Authorization

Authentication and authorization are core pillars of system security. 
Confusing or improperly implementing them often leads to critical vulnerabilities.


## Authentication vs Authorization

Authentication answers:
→ Who are you?

Authorization answers:
→ What are you allowed to do?

Authentication verifies identity using credentials such as:
- Passwords
- Cryptographic keys
- Tokens
- Biometrics

Authorization determines permissions after identity is established.

Security principle:
Authentication without proper authorization enforcement still results in insecure systems.

## Access Control Models

Different systems implement different authorization models.

### DAC (Discretionary Access Control)

- Resource owners define access permissions.
- Common in traditional Unix and Windows systems.
- Flexible but prone to misconfiguration.

Risk:
Users can unintentionally grant excessive permissions.


### MAC (Mandatory Access Control)

- Central authority enforces strict policies.
- Users cannot override permissions.
- Used in high-security environments (e.g., SELinux, military systems).

Security benefit:
Stronger isolation guarantees.

### RBAC (Role-Based Access Control)

- Permissions assigned to roles.
- Users assigned to roles.
- Simplifies management in large organizations.

Example:
"Administrator", "Auditor", "User" roles.

Risk:
Role explosion or overly broad roles weaken security.

### ABAC (Attribute-Based Access Control)

- Decisions based on attributes (user, resource, environment).
- Fine-grained and dynamic.
- Common in modern cloud systems.

Example attributes:
- User department
- Device type
- Time of access

Security benefit:
Highly granular policy enforcement.

## Tokens and Sessions

After authentication, systems issue tokens or sessions to maintain identity state.

Common mechanisms:
- Session identifiers (stored in cookies)
- JWTs (JSON Web Tokens)
- Kerberos tickets

Important properties:
- Expiration time
- Integrity protection (signatures)
- Revocation mechanisms

Security risk:
Session hijacking or token forgery can bypass authentication.

## Why Broken Authorization Is Critical

Broken authorization often has higher impact than broken authentication.

Common issues:

- Privilege escalation  
  → User gains higher permissions than intended.

- Insecure Direct Object References (IDOR)  
  → Access to objects without proper authorization checks.

Example:
Changing a user ID in a URL to access another user's data.

Security takeaway:
Authorization checks must be enforced server-side for every request.
