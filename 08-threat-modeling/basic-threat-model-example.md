# Basic Threat Model Example

## Scenario: Small Web Application

Components:

- User browser
- Web server
- Application backend
- Database

Users can:

- Register
- Login
- Upload profile picture
- View dashboard

Even a simple application has multiple trust boundaries and attack points.

## Step 1: Identify Assets

First, determine what needs protection.

Key assets:

- User credentials (passwords)
- Session tokens
- Stored profile pictures
- Database records
- Application source code
- Admin accounts

If an asset is compromised, what is the impact? Assets define what matters most.

## Step 2: Identify Entry Points

Entry points are where user input or external interaction occurs.

Examples:

- Login form
- Registration form
- File upload endpoint
- API endpoints
- HTTP headers
- Cookies

Every input field is a potential attack vector.

If data enters the system, it must be validated.

## Step 3: Identify Threats

- Brute force login attempts
- Credential stuffing
- SQL injection
- File upload abuse
- Session hijacking
- Cross-site scripting (XSS)

Threats represent potential actions against assets.

They are not weaknesses themselves.

## Step 4: Identify Vulnerabilities

Weaknesses that threats could exploit:

- No rate limiting on login
- Unsanitized user input
- No file type validation
- Files stored in executable directory
- Insecure session cookies
- Overly permissive access controls

## Step 5: Identify Attack Paths

An attack path shows how weaknesses connect.

Example attack path:

1. Attacker brute forces login
2. Gains access to user account
3. Uploads malicious file
4. Executes code or attempts privilege escalation
5. Accesses sensitive database records

Mapping attack paths helps:

- Visualize impact
- Prioritize fixes
- Understand chain reactions

Single weaknesses are dangerous. Chained weaknesses are critical.