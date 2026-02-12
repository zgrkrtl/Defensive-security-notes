# Common Protocols from Security View

Protocols define communication rules. Each protocol creates a specific attack surface.

## 1. DNS Abuse

DNS translates domain names to IP addresses.

Abuse examples:
- DNS spoofing
- Cache poisoning
- Data exfiltration via DNS tunneling
- Domain generation malwares

DNS is often trusted. That trust can be exploited.

## 2. HTTP Attack Surface

HTTP is stateless and text-based.

Common risks:
- Injection attacks
- Authentication bypass
- Session hijacking
- Header manipulation
- Insecure cookies

Most web attacks target HTTP logic.

## 3. SMTP Abuse

SMTP handles email transfer.

Risks:
- Phishing
- Email spoofing
- Spam relays
- Malware delivery

Weak SPF/DKIM/DMARC increases abuse risk.

## 4. SMB Risks

SMB is used for file sharing (mostly Windows).

Common issues:
- Credential theft
- Lateral movement
- EternalBlue-type exploits
- Misconfigured shares

SMB exposure internally increases attacker mobility.
