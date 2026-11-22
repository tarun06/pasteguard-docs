# Protected Apps

PasteGuard lets you choose which applications should receive clipboard protection.

A **Protected App** is an application where PasteGuard should evaluate clipboard content before paste and apply the configured protection policy.

This helps reduce the risk of accidentally pasting secrets or sensitive data into the wrong destination.

---

# Why Protected Apps Matter

Many data leaks happen during normal copy-and-paste workflows.

A common example:

```text id="t0jnh0"
Copy API Key
   ↓
Switch to Browser
   ↓
Paste into AI / Chat / Support Tool
```

Without protection, the original value may be exposed immediately.

With PasteGuard:

```text id="lfdl0r"
Copy
  ↓
PasteGuard Detects
  ↓
Destination Is Protected
  ↓
Policy Applied
  ↓
Sanitize / Block
  ↓
Safer Paste
```

---

# Examples of Protected Apps

Applications that users may choose to protect include:

- Web browsers
- AI assistants
- Chat applications
- Microsoft Teams
- Email clients
- Support portals
- Ticketing systems
- External websites
- Collaboration applications
- Other applications selected by the user

The exact list depends on the user's workflow and security requirements.

---

# Example

Suppose the clipboard contains:

```text id="j9du4k"
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

If the destination application is configured as protected, PasteGuard can sanitize the content before paste:

```text id="lt1mlf"
OPENAI_API_KEY=<OPENAI_API_KEY>
```

The original credential does not need to be pasted into the protected application.

---

# Protected App Behavior

Depending on the active protection mode and policy, a protected destination can result in:

## Sanitize

PasteGuard replaces sensitive values with safe placeholders.

Example:

```text id="qgqufi"
AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/example
```

becomes:

```text id="ppjpap"
AWS_SECRET_ACCESS_KEY=<AWS_SECRET_KEY>
```

---

## Block

PasteGuard can prevent the paste operation when the configured policy requires blocking.

Example flow:

```text id="ajq59s"
Sensitive Clipboard Content
          ↓
      PasteGuard
          ↓
      Detection
          ↓
   Protected Destination
          ↓
        Block
```

---

## Allow

If no sensitive content is detected, the paste can continue normally.

The exact behavior depends on active settings and policy.

---

# Protected Apps vs Trusted Apps

Protected Apps and Trusted Apps serve different purposes.

## Protected Apps

Protected Apps are destinations where PasteGuard should apply clipboard protection.

```text id="hh7z6x"
Sensitive Content
      ↓
Protected App
      ↓
PasteGuard Policy
      ↓
Sanitize / Block
```

## Trusted Apps

Trusted Apps are explicitly approved destinations that may receive the original clipboard content when allowed.

```text id="u6pafa"
Sensitive Content
      ↓
Trusted App
      ↓
PasteGuard Policy
      ↓
Allow Original Content
```

For more information, see:

**[Trusted Apps](trusted-apps.md)**

---

# Recommended Protected Destinations

For many users, the following application types are good candidates for protection:

## Browsers

Browsers can be used to access:

- AI tools
- Webmail
- Support systems
- SaaS applications
- Ticketing platforms
- External portals
- Administrative consoles

Because the same browser can access many destinations, protecting browser workflows can be valuable.

---

## AI Assistants

AI assistants can be useful for:

- Code review
- Debugging
- Documentation
- Troubleshooting
- Writing
- Research

However, developers may accidentally paste:

- API keys
- Access tokens
- Connection strings
- Passwords
- Private configuration
- Sensitive customer data

PasteGuard can help sanitize supported sensitive values before they are pasted.

---

## Chat Applications

Examples include:

- Team chat
- External chat
- Customer communication
- Collaboration platforms

Secrets copied from development or production systems can otherwise be pasted unintentionally.

---

## Email Clients

Email is a common destination for:

- Configuration samples
- Troubleshooting information
- Logs
- Screenshots
- Technical instructions

PasteGuard can help reduce accidental inclusion of supported sensitive clipboard values.

---

## Support and Ticketing Systems

Support engineers often copy:

- Logs
- Configuration
- Connection information
- API responses
- Error details

This makes support and ticketing applications useful candidates for protection.

---

# Choosing Protected Apps

A simple approach is:

## Protect destinations where information leaves your trusted development context

Examples:

```text id="n9h5zu"
Browser
AI Assistant
External Chat
Email
Support Portal
Ticketing Tool
```

## Trust only applications that genuinely need original secrets

Examples may include:

```text id="3nrj7n"
Visual Studio
VS Code
Approved Internal Tools
```

This gives you a practical separation between:

```text id="oihsq8"
Riskier Destination
      ↓
Protected App
```

and:

```text id="vbszdl"
Approved Destination
      ↓
Trusted App
```

---

# Configuration

To configure Protected Apps:

1. Open PasteGuard.
2. Navigate to application protection settings.
3. Add or select the application you want to protect.
4. Confirm the application is marked as protected.
5. Ensure clipboard protection is active.
6. Test using synthetic secrets only.

The exact user interface may vary between PasteGuard versions.

---

# Testing a Protected App

Always use synthetic data.

Example test value:

```text id="l8x407"
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

Paste it into the configured Protected App.

Expected behavior depends on protection mode.

For sanitization mode:

```text id="7e5x60"
OPENAI_API_KEY=<OPENAI_API_KEY>
```

For blocking mode, the paste should be prevented according to policy.

---

# Test Sensitive Data

You can also test with synthetic sensitive data.

Example:

```json id="wwj7e3"
{
  "CardNumber": "4111111111111111",
  "IBAN": "GB82WEST12345698765432",
  "EmiratesId": "784-1987-1234567-1"
}
```

Expected sanitized result:

```json id="5gx2ns"
{
  "CardNumber": "<CARD_NUMBER>",
  "IBAN": "<IBAN>",
  "EmiratesId": "<EMIRATES_ID>"
}
```

Never use a real card number, bank account, identity number, or production credential for testing.

---

# Application Identification

PasteGuard identifies supported Windows destination applications so the configured protection policy can be applied.

Application identification may use operating-system-level application information available to PasteGuard.

Users should verify that the intended application is correctly configured before relying on a protection rule.

---

# Browsers and Web Applications

A browser can host many different web applications.

For example:

```text id="ykvchz"
Browser
├── AI Assistant
├── Webmail
├── Ticketing System
├── SaaS Portal
└── Internal Application
```

Depending on PasteGuard configuration, browser-level protection may affect paste operations performed through that browser process.

Consider your workflow carefully when deciding whether a browser should be protected or trusted.

---

# Protected App Precedence

Application behavior should always be evaluated according to the active PasteGuard settings and organization policy.

In managed environments, users may not be able to override application classifications defined by administrators.

If an organization policy controls the destination:

```text id="h3iclj"
Organization Policy
        ↓
Application Classification
        ↓
Protection Behavior
```

The organization-controlled policy takes precedence where applicable.

---

# Organization-Managed Protected Apps

PasteGuard Organization can support centrally managed application policies.

Administrators may be able to define:

- Protected applications
- Blocked applications
- Trusted applications
- Enforced protection behavior
- Settings users cannot modify

This helps organizations maintain consistent clipboard security across managed Windows devices.

For more information:

**[PasteGuard Organization](organization.md)**

---

# Blocked Apps

In organization-managed environments, an administrator may designate applications where sensitive paste operations should be blocked.

Conceptually:

```text id="e9t5vs"
Sensitive Clipboard
      ↓
Blocked Destination
      ↓
Organization Policy
      ↓
Paste Prevented
```

The exact behavior depends on the configured organization policy.

---

# Security Recommendations

When configuring Protected Apps:

- Protect applications that do not require production secrets.
- Protect external communication tools.
- Protect AI and browser destinations where appropriate.
- Avoid trusting an application simply for convenience.
- Review application settings periodically.
- Remove applications that are no longer needed.
- Use organization-managed policies where centralized enforcement is required.

---

# Avoid Over-Trusting Applications

Trusted Apps bypass sanitization when explicitly allowed.

For that reason, do not mark applications as trusted unless they genuinely require access to original clipboard secrets.

A broad Trusted Apps list can reduce the effectiveness of clipboard protection.

Prefer:

```text id="5yg2no"
Few Trusted Apps
+
More Protected Destinations
```

rather than:

```text id="smn0qr"
Many Trusted Apps
+
Little Protection
```

---

# Protection Is Destination-Aware

PasteGuard combines sensitive-content detection with destination awareness.

Conceptually:

```text id="jy8uzc"
Clipboard Content
       +
Destination Application
       +
Active Policy
       ↓
PasteGuard Decision
       ↓
Sanitize / Block / Allow
```

This makes clipboard protection more useful than applying the same behavior to every application.

---

# Local Processing

Protected App evaluation is part of PasteGuard's local protection workflow.

Core clipboard detection and policy evaluation are performed locally on the Windows device.

Clipboard secrets do not need to be uploaded to a remote detection service.

> **No secret leaves your computer.**

---

# Troubleshooting

## PasteGuard Is Not Sanitizing in a Protected App

Check:

1. PasteGuard protection is enabled.
2. Protection is not paused.
3. The destination application is configured as protected.
4. The relevant detector is enabled.
5. Your PasteGuard edition includes the detector.
6. Organization policy is not changing the application behavior.
7. You are testing with a supported synthetic value.

---

## The Application Is Receiving Original Content

Check whether:

- The application is configured as Trusted.
- Protection is paused.
- The detector is disabled.
- The content does not match a supported detector.
- Organization policy permits the original content.
- The application identity differs from the one configured.

---

## The Application Is Incorrectly Protected

Verify the configured application identity.

If you believe application identification is incorrect, open a bug report with:

- Application name
- Windows application/process information if available
- Expected behavior
- Actual behavior
- PasteGuard version

Do not include real credentials.

---

# Feedback

If you encounter an issue with Protected Apps, open a GitHub issue.

Useful information includes:

- Application name
- Expected behavior
- Actual behavior
- PasteGuard version
- Protection mode
- Synthetic test data

Never post real credentials or sensitive customer information.

---

# Related Documentation

- **[Getting Started](getting-started.md)**
- **[Detector Coverage](detectors.md)**
- **[Trusted Apps](trusted-apps.md)**
- **[Free vs Pro vs Organization](free-vs-pro.md)**
- **[Organization](organization.md)**
- **[FAQ](faq.md)**
- **[Security Policy](../SECURITY.md)**
- **[Privacy](../PRIVACY.md)**

---

# Get PasteGuard

PasteGuard is available for Windows through Microsoft Store.

https://apps.microsoft.com/detail/9nl0497qc6zk

Product ID:

```text id="w8vzst"
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