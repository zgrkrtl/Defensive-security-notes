# Privilege Escalation

Privilege escalation is when an attacker gains higher permissions than initially granted.

It is often the second stage of an attack, not the first.

## 1. Vertical Privilege Escalation

Gaining higher-level permissions.

Examples:
- user -> admin
- Web app user → System account
- Service account → Root

Common causes:
- Misconfigured sudo
- Weak service permissions
- Unpatched kernel vulnerabilities
- Setuid binaries

## 2. Horizontal Privilege Escalation

Accessing resources of another user with the same privilege level.

Examples:
- Viewing another user's data
- Changing another user’s settings
- Accessing other accounts via ID manipulation

Often caused by:
- Broken access control
- Missing authorization checks

## 3. Why It Matters

Initial access is rarely the goal.

Attackers escalate privileges to:
- Disable logging
- Access sensitive data
- Move laterally
- Maintain persistence
- Take full system control

Privilege boundaries are security boundaries.
When they fail, containment fails.
