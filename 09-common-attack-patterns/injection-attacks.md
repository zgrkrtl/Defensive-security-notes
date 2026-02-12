# Injection Attacks

Injection occurs when untrusted input is interpreted as code or commands.

It happens when data and instructions are not properly separated.

## 1. SQL Injection Concept

If user input is directly embedded into a query:

SELECT * FROM users WHERE name = 'USER_INPUT';

An attacker may inject:

' OR '1'='1

Result:
Query logic changes.

Causes:
- String concatenation
- No parameterized queries
- Lack of input validation

Impact:
- Data leakage
- Authentication bypass
- Data modification
- Database takeover

## 2. Command Injection

Occurs when user input is executed by the system shell.

Example:
system("ping " + user_input);

If input is:
8.8.8.8; rm -rf /

The attacker injects additional commands.

Impact:
- Remote code execution
- Full system compromise

## 3. Root Cause

- Mixing code and data
- Trusting user input
- Lack of strict validation
- Improper escaping

Injection is a design failure,
not just an input validation issue.
