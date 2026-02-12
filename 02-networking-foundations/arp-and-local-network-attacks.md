# ARP and Local Network Attacks

ARP (Address Resolution Protocol) maps IP addresses to MAC addresses.

It operates inside local networks. ARP has no authentication.

## 1. How ARP Works

Device asks:
"Who has 192.168.1.1?"

Router replies with its MAC address.

The sender stores this in its ARP cache.

Communication continues at Layer 2.

## 2. ARP Spoofing / Poisoning

Attacker sends fake ARP replies:

"I am 192.168.1.1"

Victim updates ARP cache with attacker’s MAC.

Traffic is redirected through attacker.

## 3. Man-in-the-Middle (MITM)

With ARP poisoning, attacker can:

- Intercept traffic
- Modify traffic
- Capture credentials (if unencrypted)
- Inject malicious responses

Encryption (HTTPS) reduces impact,
but metadata remains visible.

## 4. Why Switched Networks Are Not Fully Secure

Switches isolate traffic by MAC.

But ARP spoofing:
- Manipulates MAC mapping
- Bypasses simple isolation

Internal networks often assume trust.
That trust can be abused.
