# Routing and Basic Network Behavior

Routing determines where packets go.

Without routing, networks cannot communicate beyond their subnet.

## 1. Default Gateway

When a device sends traffic outside its subnet,
it forwards packets to the default gateway.

The gateway routes traffic to other networks.

If the gateway is compromised, traffic flow is compromised.

## 2. Subnetting Logic

Subnets divide networks into segments.

Example:
192.168.1.0/24

Subnetting helps:
- Organize networks
- Limit broadcast traffic
- Support segmentation

Poor subnet design increases lateral movement risk.

## 3. How Routing Affects Security

Routing rules define:
- Which networks can communicate
- Which paths traffic can take

Misconfigured routes may:
- Expose internal systems
- Bypass firewall segmentation
- Create unintended access paths

## 4. Traffic Visibility

Traffic between segments often passes through:

- Routers
- Firewalls
- Gateways

These points are ideal for:
- Monitoring
- Filtering
- Logging

Security depends on controlling network paths.
