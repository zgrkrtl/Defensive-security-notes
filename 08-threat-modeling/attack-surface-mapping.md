# Attack Surface Mapping

Attack surface is the total set of entry points into a system.

Every exposed service, endpoint, or interface increases potential risk.

The larger the attack surface,  
the harder the system is to secure.

Security improves when exposure decreases.

## 1. External Attack Surface

The external attack surface includes anything reachable from the internet.

Examples:

- Public web applications
- Open ports
- Public APIs
- Login panels
- Cloud storage endpoints
- Email servers
- VPN gateways

Anything accessible from the internet increases exposure.

Internet-facing systems are constantly scanned.

Attackers look for:

- Misconfigurations
- Outdated software
- Weak authentication
- Exposed admin interfaces

External exposure should be minimized and monitored continuously.

## 2. Internal Attack Surface

Internal systems are not automatically safe.

If an attacker gains initial access,  
internal weaknesses become critical.

Examples:

- Admin panels
- Internal APIs
- Shared drives
- Database access
- Flat network architecture
- Lateral movement paths
- Over-privileged accounts

Internal attack surface determines how far an attacker can move.

Strong internal segmentation limits damage.

## 3. Hidden Attack Surface

Some risks are not obvious.

Hidden or forgotten assets create blind spots.

Examples:

- Debug endpoints left enabled
- Forgotten subdomains
- Test environments exposed to the internet
- Old API versions
- Backup servers
- Default credentials
- Shadow IT systems

Shadow assets are common risk sources.

If it exists and is reachable, it is part of the attack surface.

## 4. Reducing Attack Surface

Reducing exposure lowers risk before detection is even required.

- Disable unused services
- Close unnecessary ports
- Remove legacy endpoints
- Decommission unused servers
- Apply least privilege
- Segment networks
- Restrict admin access
- Enforce strong authentication

Less exposure = fewer opportunities.

Minimizing attack surface is proactive security.