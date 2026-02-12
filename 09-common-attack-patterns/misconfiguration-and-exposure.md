# Misconfiguration and Exposure

Many breaches are not advanced exploits.They are simple misconfigurations.

Security often fails due to neglect.

## 1. Default Credentials

- admin / admin
- root / password

Often left unchanged in:
- Routers
- Admin panels
- Databases
- Dev environments

## 2. Exposed Services

- Open ports
- Public databases
- Debug endpoints
- Admin dashboards accessible from internet

Anything exposed becomes part of the attack surface.

## 3. Cloud Storage Misconfiguration

- Public S3 buckets
- Open object storage
- Misconfigured IAM roles

Leads to data leakage.

## 4. Debug and Development Settings

- Stack traces exposed
- Verbose error messages
- Development mode enabled
- Hardcoded API keys

Information disclosure helps attackers.

## 5. Overly Permissive CORS

Allowing:
Access-Control-Allow-Origin: *

May allow cross-origin abuse.

Misconfiguration is dangerous because
it requires no sophisticated exploitation.
