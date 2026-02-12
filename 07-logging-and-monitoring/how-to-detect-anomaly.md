# How to Detect Anomalies (Basics)

Detection is about identifying deviations from normal behavior.

Security monitoring is not about looking for “anything strange.”  
It is about comparing activity against what is expected.

Without understanding normal behavior,  
everything looks suspicious.

## 1. Baseline

A baseline represents normal system activity over time.

You cannot detect anomalies without first defining “normal.”

Examples of baselines:

- Typical login times for users
- Normal geographic login locations
- Average daily traffic volume
- Expected API request frequency
- Standard CPU and memory usage
- Normal admin activity patterns

Baselines can be:

- Static (manually defined thresholds)
- Dynamic (learned over time)

An anomaly is deviation from the established baseline.

No baseline means no meaningful anomaly detection.

## 2. Types of Anomalies

- Login from unusual country or IP range
- Excessive failed login attempts
- Successful login after many failures
- Unexpected privilege escalation
- Large outbound data transfers
- Access to sensitive data at unusual times
- Process spawning unusual child processes
- Service communicating with unknown external hosts

An anomaly does NOT automatically mean compromise.

It means actions should be investigated.

## 3. Indicators of Compromise

IOCs are observable signs of potential intrusion.

They are concrete artifacts linked to known attacks.

- Known malicious IP addresses
- Suspicious file hashes
- Known command-and-control domains
- Unexpected registry modifications
- New unknown services running
- Modified system files

IOCs are reactive. They detect:

- Known malware
- Known attack infrastructure
- Previously documented attack patterns


Limitation: If the attack is new and unknown,  
there may be no matching IOC.

## 4. Behavioral Detection vs Signature Detection

There are two main detection approaches.

Signature-based detection: (ex: Detects known malware hash)

- Matches known attack patterns
- Uses predefined rules or hash matches
- Effective for known threats
- Fast and precise

Weakness:
- Cannot detect new or modified attacks

Behavior-based detection: (ex: Detects unusual process injecting into another process)

- Focuses on abnormal activity
- Detects deviations from baseline
- Can detect unknown attacks
- More adaptive

Behavioral detection is more flexible  
but may generate more false positives.

Modern systems combine both.

## 5. False Positives and False Negatives

Detection systems must balance sensitivity.

False positive:
- Benign activity flagged as malicious

False negative:
- Malicious activity not detected

Too many alerts:

- Analyst fatigue
- Important alerts ignored
- Reduced trust in monitoring

Too few alerts:

- Attacks go unnoticed
- Delayed response
- Increased damage

Effective monitoring:

- Reduces noise
- Preserves signal
- Continuously tunes thresholds
- Improves over time
