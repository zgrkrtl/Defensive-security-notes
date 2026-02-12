# OSI vs TCP/IP Model

Both OSI and TCP/IP models describe how network communication works.

They are conceptual frameworks, not literal implementations.

## 1. OSI Model (7 Layers)

1. Physical
2. Data Link
3. Network
4. Transport
5. Session
6. Presentation
7. Application

OSI is more detailed and theoretical.

## 2. TCP/IP Model (4 Layers)

1. Network Access
2. Internet
3. Transport
4. Application

TCP/IP reflects how the Internet actually works.

## 3. Practical Comparison

OSI is useful for:
- Structured thinking
- Troubleshooting
- Teaching

TCP/IP is useful for:
- Real-world protocol mapping
- Understanding actual traffic

Example:
HTTP -> Application layer  
TCP -> Transport layer  
IP -> Internet layer  


## 4. Which Layers Matter Most in Defense

From a security perspective:

Transport layer:
- TCP behavior
- Port exposure
- Connection control

Network layer:
- IP routing
- Firewall rules
- Segmentation

Application layer:
- Most attacks happen here
- Input validation
- Authentication logic

Lower layers matter, but most modern attacks target upper layers.
