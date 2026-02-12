# Detection vs Prevention

Security often focuses on blocking attacks before they succeed.

But no system prevents everything.  
Controls can fail.  
Configurations can be wrong.  
Humans make mistakes.

Modern security assumes that prevention will eventually fail.

## 1. Prevention

Prevention aims to stop attacks before damage occurs.

Examples:

- Firewalls filtering traffic
- Access control restricting permissions
- Input validation blocking injections
- Secure configurations
- Strong authentication mechanisms

Prevention reduces attack surface.

However, it cannot guarantee complete protection.

Zero-day vulnerabilities, misconfigurations, and insider threats can bypass preventive controls.

## 2. Detection

Detection focuses on identifying attacks that bypass prevention.

Examples:

- Logging suspicious activity
- Monitoring system behavior
- Alerting on abnormal events
- Behavioral analysis
- Intrusion detection systems (IDS)

Detection answers:

"What slipped through?"

It provides visibility into ongoing or completed attacks.

## 3. Why Detection Matters

If prevention fails silently, attackers gain time.

Time allows:

- Lateral movement
- Privilege escalation
- Data exfiltration
- Persistence

Detection reduces dwell time.

Dwell time = how long an attacker remains undetected.

Shorter dwell time = less damage.