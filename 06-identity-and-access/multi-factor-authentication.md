# Multi-Factor Authentication (MFA)

MFA requires more than one independent proof of identity.

Not two passwords -> Two different categories.

Factor types:
- Something you know (password, PIN)
- Something you have (phone, hardware token)
- Something you are (biometrics)

If one factor fails, the account should still be protected.

## Common MFA Methods

TOTP apps
- Authenticators
- Time-based codes
- Offline generation

Hardware tokens
- Strong phishing resistance
- Cryptographic challenge-response
- Preferred for high-security environments

SMS codes
- Better than nothing
- Vulnerable to SIM swapping
- Vulnerable to SS7 interception

Push notifications
- Convenient
- Vulnerable to MFA fatigue attacks

Not all MFA methods provide equal security.

## What MFA Actually Protects Against

MFA reduces impact of:
- Password leaks
- Credential stuffing
- Brute-force attacks
- Database breaches

It does NOT automatically protect against:
- Real-time phishing proxies
- Session hijacking
- Malware on victim device

Security depends on implementation quality.

## Operational Weak Points

Common mistakes:
- Allowing MFA reset with weak identity checks
- Backup codes stored insecurely
- SMS as fallback without limits
- No rate limiting on OTP attempts

MFA is only as strong as its weakest recovery path.

## Security Impact

MFA does not make compromise impossible.

It increases:
- Attacker effort
- Required sophistication
- Cost of attack

That cost difference is often enough.

Authentication should not rely on a single secret.
