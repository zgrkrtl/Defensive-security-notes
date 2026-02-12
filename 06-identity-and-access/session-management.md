# Session Management Basics

Authentication proves identity once.  
Sessions keep that identity active.

HTTP is stateless.  
Every request is independent.  

Sessions simulate state between requests.

Without sessions, the server would forget the user after each request.


## 1. Session Tokens

After successful login:

- Server generates a random session ID
- Stores it server-side linked to the authenticated user
- Sends it to the client

The browser automatically includes this token in every request.

Server logic:

"Is this session ID valid?"  
"Is it linked to an authenticated user?"  

If yes -> request is treated as authenticated.  
If no -> request is rejected or redirected to login.

The password is no longer needed after login.

If attacker steals the token they don’t need the password.

Session token is temporary proof of authentication.

It represents the user’s identity for the duration of the session.

## 2. What Makes a Secure Session Token

A secure session token must be:

- Long
- Random
- Cryptographically generated
- Unpredictable
- Unique per login

weak&bad session token example:
user123-session

weak&bad because:
- Predictable
- Low entropy
- Guessable

Good session token example:
f8a91c4e7b0d5e2f9a7c8b1d4e6f3a2

High entropy = harder to brute-force.  
Predictable tokens = account takeover risk.

If attackers can guess valid session IDs, they can bypass authentication entirely.


## 3. Cookie Security Flags

Session tokens are usually stored in cookies.

Cookies must be configured securely.

Important flags:

Secure  
- Cookie sent only over HTTPS  
- Prevents interception over HTTP  
- Protects against network sniffing (like MITM)

HttpOnly  
- Not accessible via JavaScript  
- Helps protect against XSS stealing the token  
- Prevents `document.cookie` access  

SameSite  
- Restricts cross-site sending of cookies  
- Helps reduce CSRF risk  
- Values: Strict / Lax / None  

Missing these flags increases attack surface.

Session security is not only about the token 
it’s also about how the browser handles it.

## 4. Session Expiration

Sessions should expire.

They should not be permanent.

Best practices:

- Short idle timeout -> expires after inactivity
- Absolute timeout -> max lifetime
- Regenerate session ID after login
- Regenerate after privilege escalation
- Invalidate session on logout

If a session token is stolen,  
shorter lifetime means smaller damage window.

Long-lived sessions = longer compromise window.

## 5. Session Fixation

Session fixation happens when the session ID does NOT change after login.

Attack flow:

1. Attacker obtains or sets a known session ID.
2. Victim logs in using that session.
3. Server does NOT generate a new session ID.
4. Attacker reuses that known session ID.

Now attacker has authenticated access.

Always generate a new session ID after successful login.

Never trust session IDs provided via URL parameters.

## 6. Session Hijacking

Session hijacking means stealing a valid session token.

If attacker obtains the session token via:

- XSS
- Network sniffing
- Malware
- Browser compromise
- Physical access

They can impersonate the user immediately.

No password or MFA required.  

The system fully trusts the session token.

Authentication = proving identity once  
Session = maintaining that identity  

Strong authentication + weak session handling = broken security.

Session tokens are as sensitive as passwords.
