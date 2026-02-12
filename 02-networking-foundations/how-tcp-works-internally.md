# How TCP Works Internally

TCP is a connection-oriented protocol: guarantees reliable, ordered delivery.

## 1. 3-Way Handshake

Step 1:
Client -> SYN

Step 2:
Server -> SYN-ACK

Step 3:
Client -> ACK

Connection established.

This process:
- Synchronizes sequence numbers
- Confirms both sides are reachable

## 2. Sequence Numbers

Each byte in TCP stream has a sequence number.

Purpose:
- Ensure correct order
- Detect lost packets
- Prevent duplication

Incorrect sequence handling can enable:
- Session hijacking
- Packet injection (in some scenarios)

## 3. TCP State Machine Basics

TCP states include:

- LISTEN
- SYN-SENT
- SYN-RECEIVED
- ESTABLISHED
- FIN-WAIT
- TIME-WAIT
- CLOSED

Understanding states helps detect:
- SYN flood attacks
- Half-open connections
- Abnormal behavior

TCP is not just transport.

It defines connection logic attackers can abuse.
