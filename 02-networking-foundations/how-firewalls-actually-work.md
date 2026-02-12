# How Firewalls Actually Work

Firewalls control traffic based on rules.

They inspect packets and decide: Allow or deny.

## 1. Stateless Firewalls

Evaluate each packet independently.

Decision based on:
- Source IP
- Destination IP
- Port
- Protocol

No awareness of connection state. Simpler but limited.

## 2. Stateful Firewalls

Track connection states.

They remember:
- Established sessions
- Related traffic

Example:
Allow incoming packet only if it matches existing connection.

More secure than stateless filtering.

## 3. Packet Filtering Logic

Rules are evaluated in order.

Common fields:
- Source address
- Destination address
- Port
- Protocol
- Direction

Rule misordering can create unintended access.

## 4. NAT Implications

NAT translates private IPs to public IP.

Effects:
- Hides internal structure
- Reduces direct exposure
- Breaks end-to-end visibility

NAT is not a security control by itself, but it changes attack surface visibility.
