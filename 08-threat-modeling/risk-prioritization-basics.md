# Risk Prioritization Basics

Not all risks are equal.

Security resources are limited.  
Time, budget, and engineering effort must be allocated wisely.

Risk is often evaluated as:

Risk = Likelihood × Impact

Likelihood = how probable the event is.  
Impact = how severe the damage would be.

High likelihood with low impact is different from  
low likelihood with catastrophic impact.

## 1. High Likelihood + High Impact

This is critical risk.

It represents:

- Easy to exploit
- Severe consequences
- High probability of being targeted

Must be fixed immediately.

Example:

- Public admin panel with weak authentication
- Internet-exposed database with no access control
- Hardcoded credentials in production

These risks combine exposure and damage potential.

They should be top priority.

## 2. Low Likelihood + High Impact

These are strategic risks.

They may be rare, but consequences are severe.

Example:

- Zero-day vulnerability in core dependency
- Cryptographic algorithm suddenly broken
- Critical infrastructure failure

These require:

- Monitoring
- Contingency planning
- Defense-in-depth controls

Even if unlikely, impact justifies attention.

## 3. High Likelihood + Low Impact

These issues occur frequently but cause limited damage.

Example:

- Minor UI input validation issue
- Small information disclosure with no sensitive data
- Repeated harmless scanning attempts

They may generate noise.

Still important to fix,  
but not at the expense of critical risks.

Prioritize based on overall business impact.

## 4. Low Likelihood + Low Impact

Lowest priority category.

These risks:

- Are difficult to exploit
- Cause minimal damage
- Often remain theoretical

They can be scheduled for later remediation.

Not every theoretical risk requires immediate action.


## 5. Risk Acceptance

Some risks are intentionally accepted.

Reasons may include:

- High remediation cost
- Technical constraints
- Business deadlines
- Low practical exploitation probability

Risk acceptance should be:

- Documented
- Reviewed periodically
- Approved by stakeholders

Security is risk management, not risk elimination.
