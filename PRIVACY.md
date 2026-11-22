# PasteGuard Privacy

PasteGuard is designed around a simple privacy principle:

> **Sensitive clipboard content should be protected locally whenever possible.**

PasteGuard performs its core secret-detection, sensitive-data detection, policy evaluation, and sanitization locally on the Windows device.

---

# Local-First Processing

PasteGuard is built around local processing.

Core protection happens on the user's device.

Conceptually:

```text
Clipboard
   ↓
Local Detection
   ↓
Policy Evaluation
   ↓
Sanitize / Block / Allow
   ↓
Destination Application
```

Clipboard secrets do not need to be sent to:

- External AI services
- Remote secret scanners
- Cloud-based detection APIs

---

# Clipboard Content

PasteGuard may evaluate clipboard content in order to:

- detect supported secrets
- detect supported sensitive data
- identify applicable protection rules
- sanitize sensitive values
- block protected paste operations
- allow content for approved destinations

This processing is designed to happen locally.

---

# What PasteGuard Can Detect

PasteGuard can detect supported categories such as:

- API keys
- passwords
- access tokens
- cloud credentials
- database credentials
- private keys
- authentication tokens
- DevOps credentials
- payment information
- banking information
- identity information
- optional personal-data categories

For the public detector catalog, see:

**[Detector Coverage](docs/detectors.md)**

---

# Raw Secrets

PasteGuard is designed so raw detected secrets are not intentionally stored in activity history.

Examples of raw secrets include:

- passwords
- API keys
- access tokens
- private keys
- connection strings containing credentials
- card numbers
- bank details
- identity numbers

Protection-related metadata may be retained locally where required for product functionality.

---

# Activity Information

PasteGuard may maintain local activity information for supported protection events.

Depending on product version and configuration, activity information may include metadata such as:

- detection type
- protection action
- destination application
- event timestamp
- policy result

The product is designed to avoid intentionally storing raw detected secrets in activity history.

---

# Protected Apps

PasteGuard can evaluate whether the destination application is configured as a Protected App.

Protected App behavior may include:

- sanitization
- blocking
- policy-based evaluation

Destination application information used for this purpose is processed as part of the local protection workflow.

See:

**[Protected Apps](docs/protected-apps.md)**

---

# Trusted Apps

PasteGuard can also evaluate whether a destination is an explicitly approved Trusted App.

When policy permits, Trusted Apps may receive original clipboard content.

Trusted App evaluation is part of the local application-policy workflow.

See:

**[Trusted Apps](docs/trusted-apps.md)**

---

# Organization Policies

PasteGuard Organization may apply centrally managed policy settings.

Organization policies may define settings such as:

- enabled detectors
- Trusted Apps
- Protected Apps
- Blocked Apps
- pause restrictions
- protection behavior
- policy version
- organization-controlled settings

Policy evaluation is designed to occur locally on the managed Windows device.

See:

**[PasteGuard Organization](docs/organization.md)**

---

# Microsoft Store

PasteGuard is distributed through Microsoft Store.

Microsoft Store-related functionality may communicate with Microsoft services for purposes such as:

- application installation
- application updates
- licensing
- entitlement verification
- purchases
- billing

These interactions are separate from PasteGuard's local clipboard secret-detection workflow.

Clipboard secrets are not sent to Microsoft as part of PasteGuard's secret-detection functionality.

---

# Purchases and Entitlements

PasteGuard may rely on Microsoft Store services to determine whether a user has access to paid functionality such as:

- PasteGuard Pro
- PasteGuard Organization

Entitlement checks may require communication with Microsoft Store services.

These checks do not require raw clipboard secrets to be uploaded for detector processing.

---

# Internet Connectivity

PasteGuard's core detection logic is designed for local execution.

Some application functionality may require internet connectivity for:

- Microsoft Store licensing
- purchases
- entitlement verification
- application updates
- accessing external product or support resources

Core detector processing does not require clipboard secrets to be sent to a remote detection service.

---

# AI Processing

PasteGuard does not require remote AI processing for its core secret and sensitive-data detection workflow.

Clipboard content does not need to be submitted to an external AI model to determine whether supported sensitive data is present.

---

# Analytics

Any analytics or telemetry functionality, if introduced or enabled in a future PasteGuard version, should be documented separately and should not intentionally include raw clipboard secrets.

This document should be updated if privacy-relevant product behavior changes.

---

# Logs

Application logs should not intentionally contain raw secrets.

Users should nevertheless review logs before sharing them publicly.

Before posting logs to GitHub, support systems, or email:

- remove passwords
- remove API keys
- remove access tokens
- remove private keys
- remove connection strings containing credentials
- remove customer information
- remove payment information
- remove identity information

---

# Screenshots

Before sharing screenshots of PasteGuard or other applications, verify that they do not contain:

- real API keys
- passwords
- access tokens
- private keys
- customer data
- payment information
- banking information
- identity documents
- personal sensitive data

Use synthetic test data whenever possible.

---

# GitHub Issues

Do not post real sensitive information in public GitHub issues.

When reporting a bug, use:

- synthetic credentials
- redacted logs
- sanitized screenshots
- synthetic identity data
- synthetic payment data

Never post:

- production passwords
- production API keys
- real access tokens
- private keys
- certificate passwords
- real payment card numbers
- bank account details
- Emirates IDs
- passport numbers
- customer information

---

# Security Reports

Potential security vulnerabilities should not be reported with sensitive details through a public GitHub issue.

Report security concerns privately:

**hello@mindatwork.co.in**

See:

**[Security Policy](SECURITY.md)**

---

# Synthetic Test Data

PasteGuard documentation uses synthetic test values.

Examples such as:

```text
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

or:

```json
{
  "CardNumber": "4111111111111111",
  "IBAN": "GB82WEST12345698765432"
}
```

are intended only for demonstrations and testing.

Do not replace synthetic examples with real production data.

---

# Personal Data Detectors

PasteGuard can optionally support broader personal-data protection for supported categories such as:

- email addresses
- phone numbers
- dates of birth

Whether these detectors are enabled depends on user or organization configuration.

---

# Data Minimization

PasteGuard's privacy approach is based on minimizing the amount of sensitive information that needs to leave the user's device.

Where possible:

```text
Sensitive Data
      ↓
Processed Locally
      ↓
Only Protection Result Used
```

rather than:

```text
Sensitive Data
      ↓
Uploaded to Remote Service
      ↓
Remote Processing
```

---

# Security and Privacy Boundaries

PasteGuard is intended to reduce accidental clipboard exposure.

It should be used as one layer of a broader security strategy.

PasteGuard does not replace:

- endpoint security
- identity and access management
- secret rotation
- password managers
- DLP systems
- secure development practices
- least-privilege access
- endpoint management
- security awareness training

---

# User Responsibilities

Users should:

- configure Protected Apps carefully
- keep the Trusted Apps list small
- use synthetic credentials for testing
- avoid disabling protection unnecessarily
- review application updates
- keep PasteGuard updated
- report false positives and false negatives using sanitized data
- avoid sharing real secrets in support requests

---

# Organization Responsibilities

Organizations using PasteGuard should:

- configure policies according to business requirements
- define Trusted Apps carefully
- review Blocked Apps
- validate detector configuration
- test policies with synthetic data
- review policy changes
- ensure users understand safe handling of sensitive information

---

# Data Retention

PasteGuard is designed to minimize storage of sensitive clipboard data.

Raw detected secrets are not intentionally retained in activity history.

Non-secret local configuration or security-event metadata may be stored where necessary for product functionality.

The exact local storage implementation may evolve between product versions.

---

# Data Deletion

Users can remove PasteGuard from Windows using standard Windows application-management functionality.

Uninstall behavior and removal of local application data may depend on Windows and application-version behavior.

Organization-managed devices may also be subject to administrator-controlled retention or device-management policies.

---

# Third-Party Services

PasteGuard may link to or rely on external services for purposes such as:

- Microsoft Store distribution
- product website access
- support
- documentation

These third-party services operate under their own privacy policies.

PasteGuard's local clipboard-detection design does not require raw clipboard secrets to be sent to those services for core detector operation.

---

# Changes to This Privacy Information

PasteGuard may evolve over time.

If privacy-relevant behavior changes, this document should be updated to reflect the current product behavior.

Examples include future changes to:

- analytics
- telemetry
- organization management
- cloud services
- account functionality
- synchronization
- licensing

---

# Contact

For privacy questions:

**Mind At Work**

Website:

https://mindatwork.co.in

Email:

**hello@mindatwork.co.in**

---

# Related Documentation

- **[Getting Started](docs/getting-started.md)**
- **[Detector Coverage](docs/detectors.md)**
- **[Protected Apps](docs/protected-apps.md)**
- **[Trusted Apps](docs/trusted-apps.md)**
- **[Free vs Pro vs Organization](docs/free-vs-pro.md)**
- **[PasteGuard Organization](docs/organization.md)**
- **[FAQ](docs/faq.md)**
- **[Security Policy](SECURITY.md)**

---

# PasteGuard

## Privacy by Design

**Local-First Secret Detection**

**Local Policy Evaluation**

**No Remote AI Required for Core Detection**

**Raw Secrets Are Not Intentionally Stored in Activity History**

> **No secret leaves your computer.**

### Get PasteGuard for Windows

https://apps.microsoft.com/detail/9nl0497qc6zk