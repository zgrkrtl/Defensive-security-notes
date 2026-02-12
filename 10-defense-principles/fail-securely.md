# Fail Securely

When systems fail,
they should fail safely.

## 1. Secure Failure Behavior

Examples:
- Deny access on error
- Invalidate sessions on crash
- Roll back partial actions
- Avoid exposing stack traces

## 2. Common Unsafe Failures

- Access granted on error
- Debug mode exposed
- Partial authentication success
- Sensitive data in error messages

Failure is inevitable.

Unsafe failure turns bugs into vulnerabilities.
