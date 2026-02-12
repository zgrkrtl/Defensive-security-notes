# Basic Nmap Usage

Scan common ports on target
nmap [IP_ADDR]


Perform SYN-stealth scan
nmap -sS [IP_ADDR]


Detect service versions
nmap -sV [IP_ADDR]


Scan all ports
nmap -p- [IP_ADDR]


Attempt OS detection
nmap -O [IP_ADDR]


Aggressive scan (version + OS + scripts)
nmap -A [IP_ADDR]


Scan specific ports
nmap -p 22,80,443 [IP_ADDR]
