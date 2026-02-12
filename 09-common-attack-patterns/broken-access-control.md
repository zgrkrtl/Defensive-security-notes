# Broken Access Control

Access control defines what authenticated users are allowed to do.

Broken access control is when these rules are not properly enforced.

It is one of the most common real-world vulnerabilities.

## 1. IDOR (Insecure Direct Object Reference)

Example:

/api/user?id=123

If changing the ID to 124 gives access to another user’s data,
authorization is missing.

Authentication exists.
Authorization fails.

## 2. Missing Authorization Checks

Frontend hides admin button,
but backend does not verify role.

Attackers can directly call the endpoint.

Security must be enforced server-side.

## 3. Role Manipulation

If roles are stored in:
- JWT without validation
- Client-side storage
- Easily modified fields

Attackers may escalate privileges.

## 4. Forced Browsing

Accessing endpoints not linked in UI:
- /admin
- /backup
- /internal

Hidden does not mean protected.

Access control must be:

- Explicit
- Verified on every request
- Based on least privilege
