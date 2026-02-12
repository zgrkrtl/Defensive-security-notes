# Security Is About Tradeoffs

Security is not about maximizing protection at any cost.

Security is about making informed tradeoffs under constraints regarding systems' strong&weak.

Every security decision affects:
- Usability
- Performance
- Cost
- Operational complexity

# 1. Usability vs Security

Stronger protocols changes systems in a ways you don't want.

Examples:
- Multi-factor authentication increases login time.
- Strict password rules increase user frustration.
- Session timeouts improve safety but reduce convenience.

User might ignore some security protocols because its faster not to.

Security that users avoid is ineffective.

Good security design minimizes friction while preserving protection.


# 2. Performance vs Verification

More verification means more computation.

Examples:
- Deep packet inspection increases latency.
- Strong encryption increases CPU usage.
- Extensive logging increases storage and processing cost.

Over-securing a system can degrade availability.

If user can't use it there is no point of security.


# 3. Cost vs Resilience

Redundancy improves availability, but increases cost.

Examples:
- Multi-region cloud deployments
- Backup infrastructure
- High-availability clustering
- Continuous monitoring systems

Resilience is expensive.


# 4. Complexity vs Control

Adding security layers can increase system complexity.

Which can lead to more exploits.

Complex systems:
- Are harder to reason about
- Introduce configuration mistakes
- Increase attack surface

Overengineering security can create new vulnerabilities.

Simplicity is an advantage for some systems.

# 5. Centralization vs Decentralization

Centralized systems:
- Easier to monitor
- Easier to manage
- But create single points of failure

Decentralized systems:
- Reduce single failure risk
- But increase coordination complexity

Security architecture must consider structural risk.

