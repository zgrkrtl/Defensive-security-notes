# Assets, Threats, and Vulnerabilities

Threat modeling starts with understanding what needs protection.

Security is not about protecting everything equally.  
It is about protecting what matters most.

Resources are limited.  
Prioritization is necessary.

## 1. Asset Identification

An asset is anything valuable to the system or organization.

Assets can be:

- Data
- Systems
- Services
- Infrastructure
- People
- Reputation

Examples:

- User credentials
- Personal data
- Financial records
- Source code
- API keys
- Database contents
- Admin accounts
- Cloud infrastructure access
- Brand reputation

If you do not identify assets, you cannot protect them.

Unidentified assets are unprotected assets.

## 2. Asset Classification

Not all assets have equal value or impact.

Some data exposure is minor.  
Some exposure is catastrophic.

- What happens if this is leaked? (Confidentiality)
- What happens if this is modified? (Integrity)
- What happens if this becomes unavailable? (Availability)

This is the CIA triad:

- Confidentiality
- Integrity
- Availability

High-impact assets require stronger controls.

Security decisions should match asset value.

## 3. Threats

A threat is something that can cause harm to an asset.

Threats can be:

- External attackers
- Malicious insiders
- Curious employees
- Automated bots
- Competitors
- Human error
- Natural disasters
- Misconfigurations

Threats are actors or events capable of causing damage.

A threat alone does not cause harm.  
It needs a weakness to exploit.

## 4. Vulnerabilities

A vulnerability is a weakness that can be exploited by a threat.

Examples:

- Weak password policy
- Unpatched software
- Lack of input validation
- Overly permissive access control
- Hardcoded credentials
- Missing logging
- Exposed admin interfaces
