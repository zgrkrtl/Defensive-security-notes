# Ports and Services Exposure

Ports represent entry points to services.

Every listening port increases attack surface.

## 1. Well-Known vs Ephemeral Ports

Well-known ports 0–1023: 

22 (SSH)  
80 (HTTP)  
443 (HTTPS)

Ephemeral ports:
Temporary ports used for client connections.

Attackers focus on listening service ports, not ephemeral ones.

## 2. Binding Behavior

Service binding matters.

Binding to:
127.0.0.1

Accessible only locally.

Binding to:
0.0.0.0

Accessible from all interfaces. Exposing a service unintentionally often happens due to incorrect binding.

## 3. Public vs Internal Exposure

Internal service exposure:
Still risky due to lateral movement.

Public exposure: Immediate global attack surface.

Internet-facing services are constantly scanned.

## 4. Why Port Scanning Works

Attackers scan to discover:
- Open services
- Unexpected services
- Misconfigured services
- Outdated versions

If a port is open, it will eventually be discovered.

Minimize listening services.
