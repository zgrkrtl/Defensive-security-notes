# Denial of Service

Denial of Service (DoS) aims to make a system unavailable.

The goal is not to steal data,
but to exhaust resources.

## 1. Resource Exhaustion

Systems have limited:
- CPU
- Memory
- Disk I/O
- Network bandwidth
- Thread pools
- Database connections

Attackers attempt to overload these limits.

## 2. Application-Level DoS

Examples:
- Expensive database queries
- Large file uploads
- Infinite loops
- Regex backtracking attacks

These can be triggered with minimal traffic.

## 3. Distributed Denial of Service (DDoS)

Multiple machines send traffic simultaneously.

Harder to block due to distributed nature.

## 4. Basic Defenses

- Rate limiting
- Timeouts
- Input size limits
- Caching
- Load balancing
- Circuit breakers

Availability is part of security.
