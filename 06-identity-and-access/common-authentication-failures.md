# Common Authentication Failures

## 1. Weak Password Policies

Allowing weak passwords increases risk.

Examples of weak policies:

- Very short minimum length
- No complexity requirements
- Allowing common passwords
- No rate limiting on login attempts

Bad examples:
123456  
password  
qwerty  

Weak passwords = easy brute force success.

Authentication strength depends heavily on password quality.

## 2. No Rate Limiting

If login attempts are unlimited:

- Attackers can try thousands of passwords
- Automated brute force becomes practical
- Credential stuffing becomes effective

Credential stuffing = using leaked password databases on other sites.

To Fix:

- Limit login attempts
- Add temporary lockout
- Use exponential backoff
- Monitor suspicious activity

Unlimited attempts = online brute force vulnerability.

## 3. Insecure Password Storage

Passwords must NEVER be stored in plaintext.

- Storing raw passwords in database
- Using reversible encryption
- Using outdated hashing (MD5, SHA1)

If database leaks -> all accounts are compromised.

Good practice:

- Use strong hashing algorithms (bcrypt, Argon2, PBKDF2)
- Use salting
- Use proper cost factor

Password hashing protects stored credentials.

## 4. Missing MFA

Single-factor authentication is password only.

If password is:

- Leaked
- Reused
- Phished
- Guessed

Account is compromised.

MFA adds a second factor:

- password
- OTP, phone, hardware key
- biometrics

Without MFA, password compromise means full account compromise.

## 5. Authentication Bypass Logic Errors

Sometimes authentication fails due to logic mistakes.

Examples:

- Improper input validation
- Skipping checks in certain API routes
- Trusting client-side validation
- Broken conditional statements

Example vulnerability:

If (authenticated == true)  
But variable can be manipulated -> bypass possible.

Authentication must always be enforced server-side.

## 6. User Enumeration

Authentication responses reveal too much information.

Bad example:

"User does not exist"  
"Incorrect password"

This allows attackers to:

- Identify valid usernames
- Target specific accounts
- Improve brute force efficiency

Better response:

"Invalid credentials"

Generic errors reduce information leakage.

## 7. Broken Account Lockout Mechanisms

If lockout logic is flawed:

- Attackers can bypass limits
- Attackers can lock out legitimate users (DoS)

Authentication systems must balance:

Security  
Availability  
User experience  

Improper lockout handling creates new attack vectors.

## 8. Trusting Client-Side Authentication

Client-side checks can be bypassed.

Examples:

- Hidden form fields
- JavaScript-only validation
- Frontend-only access controls

Attackers can:

- Modify requests
- Use intercepting proxies
- Send direct API calls

Authentication must always be validated on the server.
