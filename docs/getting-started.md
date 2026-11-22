# Getting Started with PasteGuard

PasteGuard is a local-first clipboard security utility for Windows that helps prevent accidental exposure of secrets and sensitive data during copy and paste.

This guide walks through installation, initial setup, Protected Apps, Trusted Apps, detector configuration, testing, and common usage.

---

# 1. Install PasteGuard

PasteGuard is distributed through the Microsoft Store.

## Microsoft Store

Product ID:

```text
9NL0497QC6ZK
```

Install PasteGuard:

https://apps.microsoft.com/detail/9nl0497qc6zk

Current pricing, billing options, and availability are displayed by Microsoft Store and may vary by market.

---

# 2. Launch PasteGuard

After installation:

1. Open PasteGuard from the Windows Start menu.
2. Allow the application to finish initial setup.
3. Open the main PasteGuard window.
4. Review your current protection status.
5. Configure the applications and detectors appropriate for your workflow.

PasteGuard can continue running in the background through the Windows system tray.

---

# 3. Understand the PasteGuard Workflow

PasteGuard protects the copy-and-paste workflow before sensitive content reaches an unintended destination.

Typical flow:

```text
Copy
  ↓
PasteGuard Detects Sensitive Content
  ↓
Destination Application Evaluated
  ↓
Policy Applied
  ↓
Sanitize / Block / Allow
  ↓
Paste
```

The goal is to prevent sensitive clipboard information from reaching the wrong application.

---

# 4. Protected Apps

Protected Apps are applications where PasteGuard should apply clipboard protection.

Examples may include:

- Browsers
- AI assistants
- Chat applications
- Microsoft Teams
- Email clients
- Support portals
- Ticketing systems
- External web applications
- Other applications selected by the user

## Example

A clipboard value contains:

```text
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

When pasted into a protected destination, PasteGuard can sanitize the value:

```text
OPENAI_API_KEY=<OPENAI_API_KEY>
```

Depending on your protection mode and policy, PasteGuard may sanitize or block sensitive content.

---

# 5. Configure Protected Apps

To configure Protected Apps:

1. Open PasteGuard.
2. Navigate to the application protection settings.
3. Add the Windows applications you want PasteGuard to protect.
4. Confirm that protection is enabled.
5. Test using synthetic credentials only.

The exact applications you protect depend on your workflow.

Common examples:

```text
Browser
AI Assistant
Microsoft Teams
Email Client
Support Portal
Ticketing Application
Chat Application
```

---

# 6. Trusted Apps

Trusted Apps are approved applications that may receive the original clipboard content without sanitization when explicitly allowed.

Examples may include:

- Visual Studio
- VS Code
- Approved internal development tools
- Approved enterprise applications
- Other trusted applications selected by the user

Trusted Apps help prevent security controls from unnecessarily disrupting approved workflows.

---

# 7. Protected Apps vs Trusted Apps

## Protected App

```text
Sensitive Clipboard Content
          ↓
      PasteGuard
          ↓
       Sanitize
          ↓
    Safe Placeholder
```

## Trusted App

```text
Sensitive Clipboard Content
          ↓
      PasteGuard
          ↓
         Allow
          ↓
    Original Content
```

Use Trusted Apps only for applications you explicitly trust.

In managed environments, Trusted App behavior may also be controlled by organization policy.

---

# 8. Detector Configuration

PasteGuard supports **100+ secret and sensitive-data detectors**.

Detector categories include:

- AI
- Cloud
- Source Control
- Databases
- DevOps & Infrastructure
- Package Registries
- Messaging
- Monitoring & Observability
- SaaS
- Email Services
- Authentication
- Keys & Certificates
- Identity
- Generic Secrets
- Payment Information
- Banking Information
- Identity Information
- Optional Personal Data Protection

For the full catalog, see:

**[Detector Coverage](detectors.md)**

---

# 9. PasteGuard Free

PasteGuard Free is a permanent free edition.

It is not a time-limited trial.

PasteGuard Free includes core clipboard protection and 12 essential detectors:

- Passwords
- Private keys
- Generic API keys
- Generic secrets
- Bearer tokens
- JSON Web Tokens
- Basic Authentication credentials
- Connection strings
- AWS credentials
- Azure secrets
- GitHub tokens
- OpenAI API keys

Free functionality does not expire.

---

# 10. PasteGuard Pro

PasteGuard Pro unlocks the broader detector catalog.

Pro includes:

- 100+ detector coverage
- Advanced AI credential detection
- Cloud credential detection
- Database credential detection
- DevOps and infrastructure detection
- Source-control detection
- SaaS credential detection
- Authentication protection
- Payment information detection
- Banking information detection
- Identity information detection
- Advanced sensitive-data protection
- Configurable detector selection

PasteGuard Pro is an optional paid upgrade.

It is not a time-limited trial.

---

# 11. PasteGuard Organization

PasteGuard Organization is designed for businesses, teams, enterprises, and managed Windows environments.

Organization includes the broader detector coverage available with Pro plus centrally managed security controls.

Depending on administrator configuration, Organization features can include:

- Organization-managed detector configuration
- Trusted App policies
- Blocked App policies
- Centrally controlled protection settings
- Pause restrictions
- Enforced detector configuration
- Organization policy identification
- Policy versioning
- Prevention of changes to organization-controlled settings

Organization functionality requires an appropriate entitlement and administrator configuration.

---

# 12. Sensitive Data Protection

PasteGuard can protect more than API keys and developer credentials.

Supported sensitive-data examples include:

## Payment

- Payment card numbers
- CVV
- CVC
- Card expiry

## Banking

- IBAN
- Bank account numbers

## Identity

- Emirates ID
- Passport numbers

## Optional Personal Data

- Email addresses
- Phone numbers
- Dates of birth

---

# 13. Testing PasteGuard Safely

Always use synthetic data when testing PasteGuard.

Never test the application by copying real production secrets.

## Synthetic API Key Example

```text
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

Expected sanitized result:

```text
OPENAI_API_KEY=<OPENAI_API_KEY>
```

---

# 14. Synthetic Payment Example

Use a synthetic payment-card test value:

```json
{
  "CardNumber": "4111111111111111",
  "ExpiryDate": "12/30",
  "CVV": "123"
}
```

Expected result:

```json
{
  "CardNumber": "<CARD_NUMBER>",
  "ExpiryDate": "<CARD_EXPIRY>",
  "CVV": "<CVV>"
}
```

---

# 15. Synthetic Banking Example

Input:

```json
{
  "IBAN": "GB82WEST12345698765432",
  "AccountNumber": "1234567890123456"
}
```

Expected:

```json
{
  "IBAN": "<IBAN>",
  "AccountNumber": "<BANK_ACCOUNT_NUMBER>"
}
```

---

# 16. Synthetic Identity Example

Input:

```json
{
  "EmiratesId": "784-1987-1234567-1",
  "PassportNumber": "N1234567"
}
```

Expected:

```json
{
  "EmiratesId": "<EMIRATES_ID>",
  "PassportNumber": "<PASSPORT_NUMBER>"
}
```

All examples in this repository are synthetic and intended for testing only.

---

# 17. Protection Modes

Depending on settings and policy, PasteGuard can:

- Detect
- Sanitize
- Block
- Allow

Your active protection mode determines how PasteGuard responds when sensitive clipboard content is detected.

---

# 18. Secure Paste

Secure Paste provides a controlled way to paste clipboard content through PasteGuard protection.

When using Secure Paste:

```text
Clipboard
   ↓
PasteGuard
   ↓
Detection
   ↓
Policy Evaluation
   ↓
Sanitized / Allowed Content
   ↓
Destination
```

This can help ensure sensitive content is evaluated before it reaches the destination application.

---

# 19. Pause and Resume Protection

PasteGuard supports pause and resume controls where allowed.

In personal environments, users may be able to temporarily pause protection.

In organization-managed environments, pause functionality may be restricted by administrator policy.

Only pause protection when you understand the security impact.

---

# 20. System Tray

PasteGuard can run in the Windows system tray.

The tray experience can provide quick access to actions such as:

- Opening PasteGuard
- Viewing protection status
- Pausing or resuming protection
- Accessing settings
- Exiting the application

Available actions may vary based on active policy.

---

# 21. Activity History

PasteGuard can maintain local activity information for supported protection events.

PasteGuard is designed so raw detected secrets are not intentionally stored in activity history.

Activity information may include security-relevant metadata such as:

- Detection type
- Protection action
- Destination application
- Event time
- Policy result

Sensitive raw clipboard values should not be intentionally retained as activity-history content.

---

# 22. Local-First Processing

PasteGuard is designed around local processing.

Secret detection, sensitive-data detection, policy evaluation, and sanitization happen locally on the Windows device.

Clipboard secrets do not need to be uploaded to:

- External AI services
- Remote secret scanners
- Cloud detection APIs

Core detection flow:

```text
Clipboard
   ↓
Local Detection
   ↓
Local Policy Evaluation
   ↓
Sanitize / Block / Allow
   ↓
Destination
```

> **No secret leaves your computer.**

Microsoft Store licensing, purchases, entitlement verification, and updates may communicate with Microsoft services.

Clipboard secrets are not sent to Microsoft as part of PasteGuard's secret-detection functionality.

---

# 23. Recommended Initial Setup

For a typical developer workflow:

## Protected Apps

Consider protecting:

- Browsers
- AI applications
- Microsoft Teams
- Email applications
- Support portals
- Ticketing systems
- External websites

## Trusted Apps

Consider trusting only applications you explicitly approve, such as:

- Visual Studio
- VS Code
- Internal development tools

## Detectors

Start with the recommended detector configuration for your edition.

Enable additional detectors based on the credentials and data you regularly handle.

---

# 24. Example Developer Workflow

A developer copies:

```text
DATABASE_URL=postgresql://admin:VeryStrongPassword123@db.example.com/app
```

The developer then switches to a protected chat application.

PasteGuard detects the database credential.

Instead of sending the original secret, PasteGuard can paste a sanitized value such as:

```text
DATABASE_URL=<POSTGRESQL_CREDENTIAL>
```

The original secret remains protected.

---

# 25. Example Trusted Workflow

A developer copies a synthetic API credential and pastes it into an explicitly trusted development application.

If the application is allowed by the active policy:

```text
Clipboard Secret
      ↓
PasteGuard
      ↓
Trusted Destination
      ↓
Original Content Allowed
```

Trusted Apps should be configured carefully.

---

# 26. Troubleshooting

## PasteGuard Does Not Detect a Test Value

Check:

1. The relevant detector is enabled.
2. Your PasteGuard edition includes the detector.
3. An organization policy is not overriding detector configuration.
4. You are using a supported synthetic format.
5. The destination application is configured appropriately.
6. Protection is not paused.

If the problem continues, open a GitHub issue with synthetic data only.

---

## A Secret Is Detected by the Wrong Detector

Some credential formats may overlap with generic secret patterns.

PasteGuard uses detector priority and overlap handling to prefer stronger, provider-specific detections where possible.

If you find a classification issue, submit a synthetic example through GitHub Issues.

---

## PasteGuard Detects Safe Content

This may be a false positive.

Open an issue containing:

- Detector name
- Synthetic example
- Expected behavior
- Actual behavior
- PasteGuard version

Never post real sensitive data.

---

## PasteGuard Misses a Credential

This may be a false negative or unsupported format.

Open a Detector Request containing:

- Provider
- Credential type
- Public provider documentation
- Synthetic example
- Expected placeholder

---

# 27. Request a Detector

If your provider or secret format is not supported, request a new detector.

Example:

```text
Provider:
ExampleCloud

Credential Type:
API Token

Synthetic Format:
example_test_abcdefghijklmnopqrstuvwxyz

Expected:
<EXAMPLECLOUD_TOKEN>
```

Never include a real credential.

---

# 28. Security Issues

Do not report security vulnerabilities containing sensitive information through a public GitHub Issue.

Report security concerns privately:

**hello@mindatwork.co.in**

See:

**[Security Policy](../SECURITY.md)**

---

# 29. Privacy

For detailed privacy information:

**[Privacy](../PRIVACY.md)**

---

# 30. Additional Documentation

- **[Detector Coverage](detectors.md)**
- **[Protected Apps](protected-apps.md)**
- **[Trusted Apps](trusted-apps.md)**
- **[Free vs Pro vs Organization](free-vs-pro.md)**
- **[Organization](organization.md)**
- **[FAQ](faq.md)**
- **[Privacy](../PRIVACY.md)**
- **[Security](../SECURITY.md)**
- **[Changelog](../CHANGELOG.md)**

---

# Get PasteGuard

PasteGuard is available for Windows through Microsoft Store.

https://apps.microsoft.com/detail/9nl0497qc6zk

Product ID:

```text
9NL0497QC6ZK
```

---

# PasteGuard

## Stop Secrets Before They Leak.

**100+ Secret & Sensitive-Data Detectors**

**Protected Apps**

**Trusted Apps**

**Local-First Protection**

> **No secret leaves your computer.**