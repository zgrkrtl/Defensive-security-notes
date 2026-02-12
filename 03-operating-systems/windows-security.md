# Windows Security Basics

These are foundational concepts I need to understand before going deeper into Windows security, Active Directory attacks, or defensive monitoring.

## Windows Authentication Model

Windows authentication is identity-based and revolves around Security Identifiers, not usernames.  
Every user, group, and computer object is assigned a unique SID.

When a user logs in:
- The system validates credentials.
- An access token is generated.
- The token contains:
  - User SID
  - Group SIDs
  - Privileges

Important distinction:
- **Local accounts** → exist only on one machine.
- **Domain accounts** → stored in Active Directory and usable across domain-joined systems.

Security implication:
Authorization decisions are made based on SIDs inside the access token.


## Active Directory Concepts

Active Directory is a centralized identity and policy management system.

Core components:
- **Domain Controller** → authenticates users and stores directory database.
- **Trust relationships** → allow authentication across domains.
- **Group Policy** → centralized configuration enforcement.

Security perspective:
Active Directory is the primary attack surface in enterprise environments.
If the Domain Controller is compromised → the domain is effectively compromised.

---
## NTLM vs Kerberos

Two major authentication protocols in Windows environments.

### NTLM
- Challenge-response based.
- Uses password hashes.
- Does not provide mutual authentication.
- Vulnerable to Pass-the-Hash attacks.

### Kerberos
- Ticket-based authentication.
- Uses Ticket Granting Ticket and Service Tickets.
- Provides mutual authentication.
- More secure but complex.

Security note:
Modern environments should prefer Kerberos.
NTLM fallback often becomes a weak point.


## Windows Authorization

Authentication -> Who you are.  
Authorization -> What you can access.

Controlled using:
- **ACL** attached to objects.
- **DACL** → defines who is allowed or denied.
- **SACL** → defines what gets audited.

Each ACL contains:
- **ACEs** specifying permissions for specific SIDs.

Security implication:
Misconfigured ACLs are a common privilege escalation vector.


## Registry Overview

The Windows Registry stores configuration data.

Structure:
- Organized into hives (HKLM, HKCU, etc.)

Security relevance:
- Stores startup entries.
- Stores service configurations.
- Can contain credential-related artifacts.

Monitoring registry changes is important for detection engineering.


## Windows Processes and Services

Windows separates privileges using service accounts.

Important concepts:
- Services can run as SYSTEM, Network Service, or custom accounts.
- LSASS handles authentication and credential material (high-level understanding).

Security relevance:
Credential dumping tools often target LSASS.
Misconfigured service permissions can allow privilege escalation.


## Common Windows Attack Surface

Areas frequently abused:

- Exposed SMB services
- Weak service permissions
- Credential reuse across systems
- Misconfigured Group Policies
- NTLM fallback
- Overprivileged accounts

Defensive mindset:
Every authentication path and permission boundary should be assumed exploitable if misconfigured.
