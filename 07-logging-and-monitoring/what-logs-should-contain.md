# What Logs Should Contain

Logs are only useful if they are structured, complete, and meaningful.

Logging is not about storing everything.  
It is about storing what matters for detection and investigation.

Poor logging creates blind spots.  
No logs = no visibility.

## 1. Logging Principles

Every log entry should answer basic questions:

- What happened?
- When did it happen?
- Where did it happen?
- Who was involved?
- Was it successful?

Logs should include:

- Timestamp (accurate and time-synchronized)
- Source (host, service, application)
- Event type
- Outcome (success/failure)
- Context (IP address, user ID, process ID, session ID)

Timestamps must be synchronized (NTP).  
Unsynchronized clocks break investigations.

Without context, logs are just noise.

Structured logs are easier to search and analyze.

## 2. Authentication Logs

Authentication events are high-value signals.

Track:

- Successful logins
- Failed login attempts
- Account lockouts
- Password reset requests
- Password change events
- Privilege changes
- MFA successes and failures
- Suspicious login locations

Multiple failed logins -> possible brute force.  
Successful login after many failures -> possible account takeover.  
Password reset abuse -> social engineering attempt.

Authentication logs are critical for detecting identity-based attacks.

## 3. Network Logs

Network activity reveals movement and communication patterns.

- Incoming and outgoing connections
- Source and destination IP addresses
- Ports and protocols used
- DNS queries
- Blocked firewall attempts
- Unusual traffic spikes
- Connections to unknown external servers

Network logs help identify:

- Port scanning
- Lateral movement
- Command & Control traffic
- Data exfiltration
- Policy violations

Without network visibility, attackers move silently.

## 4. Application Logs

Application logs provide business-level visibility.

- User actions (create, delete, update)
- Access to sensitive data
- Authorization failures
- Role or permission changes
- API usage patterns
- Errors and exceptions
- Unexpected input behavior

Application logs often expose:

- Business logic abuse
- Privilege escalation
- API abuse
- Injection attempts

Security issues often appear here first.

## 5. Integrity of Logs

Logs are evidence.

They must be:

- Protected from modification
- Write-protected where possible
- Centralized (SIEM / log server)
- Backed up
- Retained according to policy

Log integrity is as important as log content.
