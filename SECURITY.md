# PasteGuard Security Policy

Security is central to PasteGuard.

PasteGuard is designed to reduce the risk of accidental exposure of secrets and sensitive data during copy-and-paste workflows.

If you discover a security issue, please report it responsibly.

---

# Supported Product

This security policy applies to:

- PasteGuard for Windows
- PasteGuard Free
- PasteGuard Pro
- PasteGuard Organization

It also applies to security issues involving:

- Secret detection
- Sensitive-data detection
- Protected Apps
- Trusted Apps
- Clipboard protection
- Sanitization
- Blocking
- Organization policy enforcement
- Local activity handling
- Licensing-related security behavior

---

# Reporting a Security Vulnerability

Please **do not disclose security vulnerabilities through a public GitHub Issue**.

Report security concerns privately to:

**hello@mindatwork.co.in**

Website:

https://mindatwork.co.in

---

# What to Include

A good security report should include:

- A clear description of the issue
- PasteGuard version
- Windows version
- PasteGuard edition
- Steps to reproduce
- Expected behavior
- Actual behavior
- Whether the issue affects Free, Pro, or Organization
- Whether Organization policies are enabled
- Relevant application names
- Relevant detector category
- Sanitized logs
- Sanitized screenshots
- Synthetic test data

---

# Never Include Real Secrets

Do not include real:

- Passwords
- API keys
- Access tokens
- Refresh tokens
- Session tokens
- Private keys
- Certificate passwords
- Connection strings
- Cloud credentials
- Database credentials
- Production URLs containing credentials
- Payment card numbers
- CVV / CVC values
- Bank account details
- IBANs
- Emirates IDs
- Passport numbers
- Customer data
- Employee data
- Other sensitive production information

Use synthetic test values instead.

---

# Example Synthetic Credential

Use something like:

```text id="xgzzra"
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

instead of a production API key.

---

# Example Synthetic Sensitive Data

Use synthetic values such as:

```json id="b7ysxz"
{
  "CardNumber": "4111111111111111",
  "ExpiryDate": "12/30",
  "CVV": "123",
  "IBAN": "GB82WEST12345698765432",
  "EmiratesId": "784-1987-1234567-1"
}
```

Never use real customer or personal information when reproducing a security issue.

---

# High-Value Security Reports

Examples of issues that should be reported privately include:

- Sensitive content bypasses protection unexpectedly
- Original secrets are pasted when sanitization should occur
- Protected Apps can be bypassed
- Trusted App restrictions can be bypassed
- Blocked App policies can be bypassed
- Organization-managed settings can be modified unexpectedly
- Detection exposes part of a secret
- Sanitization leaves sensitive data visible
- Raw secrets are written to logs unexpectedly
- Raw secrets appear in activity history
- A detector causes unintended exposure
- Sensitive data is transmitted remotely unexpectedly
- Policy enforcement can be disabled without authorization
- Licensing or entitlement controls can be bypassed in a security-relevant way

---

# Clipboard Protection Issues

Clipboard protection is a security-sensitive area.

Please report situations where:

```text id="8lx8r5"
Sensitive Clipboard Content
          ↓
Expected Protection
          ↓
Protection Bypassed
          ↓
Original Secret Exposed
```

Provide synthetic data and exact reproduction steps.

---

# Sanitization Issues

PasteGuard should avoid partial exposure of detected secrets.

For example, if:

```text id="oes8ms"
TOKEN=abcdefghijklmnopqrstuvwxyz123456
```

is detected, sanitization should not expose a sensitive suffix or prefix unintentionally.

Security reports should include:

- synthetic input
- actual sanitized output
- expected sanitized output
- detector involved

---

# Protected App Security

Report any unexpected behavior involving Protected Apps.

Examples include:

- protected destination receives original sensitive content
- app classification is bypassed
- protection is skipped unexpectedly
- application identity is incorrectly trusted

See:

**[Protected Apps](docs/protected-apps.md)**

---

# Trusted App Security

Trusted Apps intentionally allow approved workflows, so trust-boundary issues are important.

Report situations where:

- an untrusted application is treated as Trusted
- a different executable inherits Trusted status unexpectedly
- application identity can be spoofed
- organization-managed Trusted Apps can be altered unexpectedly
- trust settings behave differently from policy

See:

**[Trusted Apps](docs/trusted-apps.md)**

---

# Organization Policy Security

PasteGuard Organization may enforce centrally managed settings.

Report issues where:

- users can modify locked settings
- managed detector configuration can be bypassed
- pause restrictions can be bypassed
- Blocked Apps can receive sensitive content
- organization policy is ignored
- policy version or identity is incorrectly applied
- local settings unexpectedly override mandatory organization controls

See:

**[PasteGuard Organization](docs/organization.md)**

---

# Detection Security

PasteGuard supports 100+ detector types.

Detection issues may include:

- provider-specific credentials being missed
- partial secret matches
- overlapping detectors exposing data
- incorrect prioritization
- unsafe sanitization
- contextual detectors matching outside intended context

False positives and ordinary false negatives may be reported publicly using synthetic data.

However, if a detection issue can directly expose real sensitive content despite an active protection policy, report it privately.

---

# Sensitive Data Security

PasteGuard supports sensitive-data categories such as:

- payment card numbers
- CVV / CVC
- card expiry
- IBAN
- bank account numbers
- Emirates ID
- passport numbers
- optional email detection
- optional phone detection
- optional date-of-birth detection

If a sensitive-data detector can expose raw sensitive content unexpectedly, report it privately.

---

# Local-First Security Model

PasteGuard is designed so core detection and policy evaluation occur locally.

Conceptually:

```text id="xov1mb"
Clipboard
   ↓
Local Detection
   ↓
Local Policy Evaluation
   ↓
Allow / Sanitize / Block
   ↓
Destination
```

If you observe clipboard secrets being transmitted to an unexpected remote destination as part of core secret detection, report it privately.

---

# Logs and Diagnostics

PasteGuard logs should not intentionally include raw secrets.

Before sharing diagnostic logs:

1. inspect the log
2. remove real credentials
3. remove personal information
4. remove production identifiers where necessary
5. retain only the minimum information required to reproduce the issue

If PasteGuard itself writes raw secrets to logs unexpectedly, report it as a security issue.

---

# Activity History

PasteGuard is designed so raw detected secrets are not intentionally stored in activity history.

If raw sensitive values are found in activity history unexpectedly, report this privately.

---

# Responsible Disclosure

We ask security researchers and users to:

- avoid accessing data that does not belong to them
- avoid testing against other users or organizations without authorization
- avoid disrupting production systems
- use synthetic credentials where possible
- avoid publishing exploit details before the issue can be reviewed
- provide enough information to reproduce the issue safely

---

# Public vs Private Reports

## Public GitHub Issue

Appropriate for:

- documentation errors
- UI bugs without security impact
- detector requests
- false positives using synthetic data
- false negatives using synthetic data
- feature requests
- non-sensitive troubleshooting

## Private Security Report

Use private reporting for:

- protection bypasses
- trust-boundary issues
- policy-enforcement bypasses
- raw secret exposure
- unsafe logging of secrets
- unauthorized access
- remote transmission of clipboard secrets
- security-sensitive licensing bypasses
- vulnerabilities that could materially reduce protection

---

# Security Response

When a security report is received, the issue may be:

1. reviewed
2. reproduced using safe data
3. assessed for security impact
4. prioritized
5. fixed where appropriate
6. included in a future release
7. documented where disclosure is appropriate

Do not assume a vulnerability has been accepted or fixed until confirmed.

---

# Security Fixes

Security fixes may be delivered through PasteGuard updates distributed through Microsoft Store.

Users should keep PasteGuard updated to receive:

- security fixes
- detector improvements
- sanitization improvements
- application-policy fixes
- stability improvements

---

# Keep PasteGuard Updated

To maintain the best available protection:

- keep Windows updated
- keep PasteGuard updated
- review Protected Apps
- review Trusted Apps
- remove outdated trust entries
- review organization policies
- keep detector configuration appropriate for your environment

---

# Defense in Depth

PasteGuard should be treated as one layer of a broader security strategy.

PasteGuard does not replace:

- password managers
- secret-management platforms
- credential rotation
- endpoint security
- identity and access management
- least privilege
- source-code secret scanning
- DLP solutions
- endpoint management
- secure development practices
- security awareness training

A strong security model uses multiple layers.

---

# Secret Rotation

If a real credential has been exposed:

1. do not rely only on sanitization after the fact
2. revoke or rotate the credential
3. review access logs
4. investigate where the credential was exposed
5. update dependent systems
6. follow your organization's incident-response process

Treat exposed credentials as compromised according to your normal security procedures.

---

# Security Testing

When testing PasteGuard:

- use synthetic data
- test only systems you own or are authorized to test
- avoid production credentials
- avoid customer data
- avoid causing service disruption

Example safe test:

```text id="sm26gc"
GENERIC_API_KEY=test_abcdefghijklmnopqrstuvwxyz123456
```

---

# Detector Requests

New detector requests are welcome.

For normal detector requests, use a public GitHub issue with:

- provider name
- credential type
- public documentation
- synthetic example
- expected replacement

Never include a real credential.

---

# Security Contact

Security reports:

**hello@mindatwork.co.in**

Publisher:

**Mind At Work**

Website:

https://mindatwork.co.in

---

# Related Documentation

- **[Getting Started](docs/getting-started.md)**
- **[Detector Coverage](docs/detectors.md)**
- **[Protected Apps](docs/protected-apps.md)**
- **[Trusted Apps](docs/trusted-apps.md)**
- **[Free vs Pro vs Organization](docs/free-vs-pro.md)**
- **[PasteGuard Organization](docs/organization.md)**
- **[Privacy](PRIVACY.md)**
- **[FAQ](docs/faq.md)**

---

# PasteGuard

## Stop Secrets Before They Leak.

Security issues should be reported responsibly.

**Do not publish real secrets or sensitive vulnerability details in public GitHub issues.**

### Security Contact

**hello@mindatwork.co.in**