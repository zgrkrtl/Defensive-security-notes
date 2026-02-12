# Insecure Deserialization

Deserialization converts data back into objects.

If untrusted data is deserialized without validation,
it can lead to code execution or logic abuse.

## 1. What Happens During Deserialization

Application receives serialized object:

- JSON
- XML
- Binary format

It reconstructs internal objects in memory.

If attacker controls this input, they may control object behavior.

## 2. Why It Is Dangerous

Some objects:
- Execute code on creation
- Trigger system calls
- Load classes dynamically

Attackers may:
- Execute arbitrary code
- Modify application logic
- Escalate privileges

## 3. Typical Root Causes

- Trusting serialized user input
- Using unsafe deserialization libraries
- No integrity verification

## 4. Prevention

- Avoid deserializing untrusted data
- Use strict schemas
- Apply integrity checks
- Prefer safer data formats

Deserialization is powerful.

When combined with untrusted input, it becomes a remote execution risk.
