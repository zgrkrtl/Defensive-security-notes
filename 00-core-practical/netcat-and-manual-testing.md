# Netcat Manual Testing

Connect to TCP service
nc [IP_ADDR] 80

Connect to specific port
nc [IP_ADDR] [PORT]

Start listener on port
nc -lvp [PORT]

Transfer file to remote host
nc [IP_ADDR] [PORT] < file.txt

Receive file on listening host
nc -lvp [PORT] > file.txt
