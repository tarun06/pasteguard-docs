# PasteGuard Organization

PasteGuard Organization is designed for businesses, enterprises, teams, and managed Windows environments that need centrally controlled clipboard-security policies.

It includes the broader detector capabilities available with PasteGuard Pro together with organization-level configuration and enforcement.

PasteGuard Organization is not a time-limited trial.

---

# What PasteGuard Organization Provides

PasteGuard Organization can support centrally managed controls such as:

- Organization-managed detector configuration
- Centrally controlled security settings
- Trusted App policies
- Blocked App policies
- Managed protection settings
- Pause restrictions
- Enforced detector configuration
- Organization policy identification
- Policy versioning
- Prevention of changes to organization-controlled settings

The exact behavior depends on administrator configuration and the PasteGuard version deployed to managed devices.

---

# Why Organization Management Matters

Individual users can configure their own security preferences.

Organizations often need something different:

```text id="41fw4b"
Organization Security Policy
          ↓
Multiple Windows Devices
          ↓
Consistent PasteGuard Configuration
```

Central management helps reduce configuration drift and ensures that important clipboard-security controls are not left entirely to individual users.

---

# Managed Detector Configuration

PasteGuard supports 100+ secret and sensitive-data detectors.

In an organization-managed environment, administrators may define which detectors should be enabled.

Conceptually:

```text id="r7tw8n"
Organization Policy
       ↓
Detector Selection
       ↓
Managed Device
       ↓
PasteGuard Enforcement
```

This can help ensure that users across the organization receive consistent protection for the secret and sensitive-data categories relevant to the business.

---

# Managed Trusted Apps

Trusted Apps are applications that may receive original clipboard content when permitted.

PasteGuard Organization can support centrally managed Trusted App policies.

Examples may include:

- approved development tools
- internal enterprise applications
- controlled administrative utilities
- other applications explicitly authorized by the organization

Conceptually:

```text id="5wqc0r"
Organization Policy
       ↓
Trusted App
       ↓
Managed Device
       ↓
Original Content Allowed
```

Trusted Apps should be configured carefully because they may receive unsanitized sensitive clipboard content.

---

# Managed Protected Apps

Administrators may define applications where PasteGuard protection should apply.

Examples can include:

- browsers
- AI assistants
- email clients
- chat applications
- support tools
- ticketing platforms
- other external-facing applications

Conceptually:

```text id="fp31ar"
Organization Policy
       ↓
Protected App
       ↓
Sensitive Paste
       ↓
Sanitize / Evaluate
```

This helps organizations enforce safer copy-and-paste behavior in applications that are more likely to expose data externally.

---

# Managed Blocked Apps

PasteGuard Organization can support policies where sensitive paste operations are blocked for selected applications.

Conceptually:

```text id="t8g2j0"
Sensitive Clipboard Content
          ↓
      Blocked App
          ↓
  Organization Policy
          ↓
     Paste Prevented
```

This is useful where sanitization is not sufficient and the organization requires a stricter control.

---

# Pause Restrictions

In managed environments, administrators may restrict whether users are allowed to pause PasteGuard protection.

Conceptually:

```text id="vlxjef"
User Requests Pause
        ↓
Organization Policy
        ↓
Allowed / Denied
```

Pause restrictions help reduce periods where protection is unintentionally disabled.

---

# Enforced Detector Configuration

Organization policy may define detector settings that local users cannot change.

This can include:

- enabled detectors
- disabled detectors
- mandatory detector categories
- sensitive-data protection
- application-specific protection rules

If detector settings are organization-controlled, local changes can be restricted.

---

# Enforced Application Policies

Organization policy may control:

- Trusted Apps
- Protected Apps
- Blocked Apps
- allowed application behavior
- paste restrictions
- protection mode

This helps keep destination-aware protection consistent across managed devices.

---

# Prevention of Local Changes

Some organization-managed settings can be protected from local modification.

Examples include:

- detector configuration
- Trusted Apps
- Blocked Apps
- protection mode
- pause settings
- policy-controlled security options

Conceptually:

```text id="4ww4yh"
Organization Policy
        ↓
Managed Setting
        ↓
Locked on Device
```

This helps prevent local configuration from weakening organization-defined security controls.

---

# Organization Policy Identification

Managed policies can include organization-specific identification.

This helps PasteGuard and administrators understand which policy context is active.

Conceptually:

```text id="nexjbx"
Organization
     ↓
Policy Identifier
     ↓
Managed Device
     ↓
PasteGuard
```

---

# Policy Versioning

Organization policies can include version information.

Versioning helps with:

- policy rollout
- troubleshooting
- deployment validation
- configuration tracking
- policy updates

Example:

```text id="edwrm1"
Policy v1
   ↓
Updated
   ↓
Policy v2
   ↓
Managed Devices
```

---

# Policy Evaluation

PasteGuard can evaluate:

```text id="9jryak"
Clipboard Content
       +
Detected Secret Type
       +
Destination Application
       +
Organization Policy
       ↓
PasteGuard Decision
```

Possible outcomes can include:

```text id="urjgz1"
Allow
Sanitize
Block
```

The exact result depends on the configured policy.

---

# Destination-Aware Security

PasteGuard Organization combines sensitive-content detection with destination application policy.

For example:

```text id="5mkhnu"
Sensitive Content
      ↓
Destination Identified
      ↓
Organization Policy
      ↓
Trusted / Protected / Blocked
      ↓
Allow / Sanitize / Block
```

This provides more control than applying the same clipboard behavior to every application.

---

# Example Policy Model

An organization may choose a model such as:

```text id="9n2om0"
Visual Studio
→ Trusted

VS Code
→ Trusted

Browser
→ Protected

AI Assistant
→ Protected

External Chat
→ Protected

Unapproved Utility
→ Blocked
```

This is only an example.

Each organization should configure policies according to its own security requirements.

---

# Local Processing

PasteGuard Organization continues to use local detection and policy evaluation on the Windows device.

Core flow:

```text id="n0u8wi"
Clipboard
   ↓
Local Detection
   ↓
Organization Policy Evaluation
   ↓
Allow / Sanitize / Block
   ↓
Destination
```

Clipboard secrets do not need to be uploaded to a remote AI or cloud detection service for core detection.

> **No secret leaves your computer.**

---

# Privacy

PasteGuard is designed around local processing.

Raw clipboard secrets are not intentionally stored in activity history.

Microsoft Store licensing, entitlement verification, application updates, and purchases may communicate with Microsoft services.

Clipboard secrets are not sent to Microsoft as part of PasteGuard's secret-detection functionality.

See:

**[Privacy](../PRIVACY.md)**

---

# Detector Coverage

PasteGuard Organization includes the broader detector coverage available with Pro.

This includes 100+ supported detector types across categories such as:

- AI
- Cloud
- Source Control
- Databases
- DevOps
- Package Registries
- Messaging
- Monitoring
- SaaS
- Authentication
- Keys & Certificates
- Sensitive Data

For the full list:

**[Detector Coverage](detectors.md)**

---

# Sensitive Data Protection

Organization-managed detector policies can also include sensitive-data categories such as:

- payment card numbers
- CVV / CVC
- card expiry
- IBAN
- bank account numbers
- Emirates ID
- passport numbers
- optional email detection
- optional phone-number detection
- optional date-of-birth detection

Organizations can decide which categories are appropriate for their environment.

---

# Example Organization Workflow

A user copies:

```text id="n2cx2a"
AWS_SECRET_ACCESS_KEY=ExampleSyntheticSecret123456789
```

The user attempts to paste it into a protected browser.

PasteGuard evaluates:

```text id="bljbec"
Sensitive Content
       +
Browser Destination
       +
Organization Policy
       ↓
Sanitize
```

Result:

```text id="12u6rq"
AWS_SECRET_ACCESS_KEY=<AWS_SECRET_KEY>
```

If the same value is pasted into a centrally trusted development tool and policy allows it, the original content may be permitted.

---

# Admin Responsibilities

Administrators should:

- define the intended detector policy
- review Trusted Apps carefully
- review Blocked Apps carefully
- test policies using synthetic values
- verify policy deployment
- review policy versions
- remove outdated application entries
- avoid granting broader trust than required

---

# User Responsibilities

Users should:

- avoid bypassing protection
- avoid adding unnecessary Trusted Apps where local configuration is allowed
- report false positives
- report false negatives
- use synthetic data when testing
- report suspicious policy behavior to the administrator

---

# Policy Testing

Always test organization policies with synthetic credentials.

Example:

```text id="7mlp8y"
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

Expected behavior depends on:

- detector configuration
- destination application
- active protection mode
- organization policy

Never use real production credentials for policy testing.

---

# Policy Rollout

A controlled rollout can follow a process such as:

```text id="qnhzjh"
Define Policy
    ↓
Test
    ↓
Pilot Devices
    ↓
Validate
    ↓
Broader Deployment
    ↓
Monitor
```

This can help identify configuration problems before organization-wide deployment.

---

# Policy Changes

When modifying organization policy:

1. update the intended configuration
2. increment or identify the policy version
3. test with synthetic data
4. deploy to a controlled group
5. verify expected application behavior
6. expand deployment when validated

---

# Troubleshooting Organization Policies

## Detector Is Not Active

Check:

- the organization policy includes the detector
- the correct policy version is active
- the device received the intended configuration
- the detector is available in the installed PasteGuard version

---

## Trusted App Is Being Sanitized

Check:

- the application is listed as trusted
- application identity matches the policy
- the latest policy version is active
- another policy rule is not overriding it

---

## Protected App Is Receiving Original Content

Check:

- whether the app is accidentally trusted
- whether the intended detector is enabled
- whether protection is paused
- whether the application identity is correct
- whether the correct policy version is active

---

## User Can Change a Managed Setting

Check:

- the setting is actually marked as organization-controlled
- the correct organization policy is active
- the device received the latest policy
- the installed version supports enforcement for that setting

---

# Reporting Organization Issues

For organization-related support, provide:

- PasteGuard version
- policy version
- affected feature
- expected behavior
- actual behavior
- application name if relevant
- synthetic test data only

Do not send real production credentials.

---

# Security Reporting

If you discover a policy bypass or enforcement weakness, treat it as a security issue.

Do not publish exploit details in a public GitHub Issue.

Report security concerns privately:

**hello@mindatwork.co.in**

See:

**[Security Policy](../SECURITY.md)**

---

# Editions

For a comparison of Free, Pro, and Organization:

**[Free vs Pro vs Organization](free-vs-pro.md)**

---

# Related Documentation

- **[Getting Started](getting-started.md)**
- **[Detector Coverage](detectors.md)**
- **[Protected Apps](protected-apps.md)**
- **[Trusted Apps](trusted-apps.md)**
- **[Free vs Pro vs Organization](free-vs-pro.md)**
- **[FAQ](faq.md)**
- **[Privacy](../PRIVACY.md)**
- **[Security](../SECURITY.md)**

---

# Contact

For organization inquiries:

**hello@mindatwork.co.in**

Website:

https://mindatwork.co.in

---

# Get PasteGuard

PasteGuard is available for Windows through Microsoft Store.

https://apps.microsoft.com/detail/9nl0497qc6zk

Product ID:

```text id="vburom"
9NL0497QC6ZK
```

---

# PasteGuard Organization

## Managed Clipboard Security for Windows

**100+ Secret & Sensitive-Data Detectors**

**Managed Trusted Apps**

**Managed Protected & Blocked Apps**

**Enforced Security Policies**

**Local-First Protection**

> **No secret leaves your computer.**