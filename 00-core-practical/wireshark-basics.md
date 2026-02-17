# Wireshark Basics (tshark CLI)

install wireshark

->sudo apt-get install wireshark -y
->sudo wireshark

CLI Equivalent Using tshark

Capture traffic on interface
tshark -i [INTERFACE]

Capture traffic from specific IP
tshark -i [INTERFACE] -f "host [IP_ADDR]"

Filter TCP traffic
tshark -i [INTERFACE] -f "tcp"

Filter HTTP traffic
tshark -i [INTERFACE] -Y "http"

Filter by port
tshark -i [INTERFACE] -f "port 443"

Read from saved capture file
tshark -r [FILE].pcap
