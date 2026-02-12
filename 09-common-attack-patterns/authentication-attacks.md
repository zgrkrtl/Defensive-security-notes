# Authentication Attacks

Authentication attacks target the login mechanism.

The goal is to gain valid access without authorization.

## 1. Brute Force

Trying many passwords against a single account.

Works when:
- No rate limiting
- Weak passwords
- No account lockout

Defense:
- Rate limiting
- Account lockout
- MFA

## 2. Credential Stuffing

Using leaked username/password combinations from other breaches.

Why it works:
- Users reuse passwords
- No breach detection
- No MFA

This attack is automated at scale.

## 3. Password Spraying

Trying one common password against many accounts.

Example:
Spring2025!

Avoids account lockout by spreading attempts.

## 4. Session Attacks

### Session Fixation
Attacker forces victim to use a known session ID.

### Session Hijacking
Stealing session tokens via:
- XSS
- Network sniffing
- Insecure cookies

If session tokens are stolen, authentication is bypassed.

Authentication is not secure just because passwords are hashed.

The surrounding controls matter.
