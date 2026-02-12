# OS Hardening and Attack Surface

Operating system security depends not only on built-in protections but also on configuration discipline. 
Most successful compromises exploit unnecessary exposure rather than unknown zero-day vulnerabilities.

---

## What Is Attack Surface?

Attack surface refers to the total number of possible entry points an attacker can interact with.

Common components include:

- Open network services
- Running background processes
- Installed software packages
- Exposed ports
- Enabled features
- Accessible APIs

Each additional service or exposed component increases potential risk.

Security principle:
If a service is not required, it should not be running.

Reducing attack surface lowers the probability of exploitation.

---

## Hardening Principles

Hardening is the process of minimizing exposure and enforcing secure configuration.

Core practices:

- Remove or disable unnecessary services.
- Uninstall unused software.
- Apply security patches regularly.
- Disable or rename default credentials.
- Restrict administrative privileges.
- Enforce least privilege.

Hardening focuses on prevention rather than detection.

Security takeaway:
The safest code is code that is never reachable.

## Logging and Monitoring

Hardening reduces exposure, but visibility is required for detection.

Important logging areas:

- Authentication attempts
- Privilege escalation events
- Process creation and termination
- Service modifications
- Configuration changes

Logs must be:
- Protected from tampering
- Centrally aggregated (in enterprise environments)
- Regularly reviewed or monitored automatically

Security principle:
If activity is not logged, it cannot be detected.

## Secure Configuration vs Default Configuration

Default configurations prioritize usability, not security.

Common risks in default setups:

- Open services enabled by default
- Broad permissions
- Default passwords
- Unrestricted network access

Secure configuration requires deliberate adjustment of:
- Access controls
- Service exposure
- Firewall rules
- Authentication mechanisms

Security takeaway:
Secure systems are intentionally configured, not accidentally secure.
