## Defense in Depth and Resilience

No single security control is sufficient for whole systems.

Security must assume failure and prepare for it from every angles.


## 1. Defense in Depth

Defense in depth -> using multiple independent layers of protection.

If one layer fails, others remain.

- Firewall + application validation
- Encryption + access control
- MFA + behavioral monitoring
- Network segmentation + endpoint protection

Security should not rely on a single mechanism.

Layered defenses increase attacker cost and detection probability.

## 2. Assume Breach

Modern security assumes that initial compromise is possible.


The question is "What happens after they get in? What should be done in that case?"

This mindset changes architecture decisions:
- Limit privilege
- Segment networks
- Monitor internal activity
- Log everything important

## 3. Least Privilege

Every user, service, and system should have only the access necessary to function.

Excessive permissions:
- Increase blast radius
- Enable privilege escalation
- Simplify lateral movement

## 4. Detection Over Prevention

Strong security programs invest in:
- Logging
- Alerting
- Behavioral analysis
- Incident response readiness

Time to detection matters.

The faster an intrusion is detected,
the lower the impact.

## 5. Containment and Recovery

Resilient systems are designed to:
- Limit damage
- Recover quickly
- Preserve forensic evidence
- Maintain core operations

Resilience includes:
- Backups
- Redundancy
- Incident playbooks
- Disaster recovery planning

Security is not just about stopping attacks.
It is about surviving them.

