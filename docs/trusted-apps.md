# Trusted Apps

PasteGuard supports **Trusted Apps** so explicitly approved applications can receive original clipboard content without sanitization when allowed by the active policy.

This helps avoid unnecessary disruption in approved development and enterprise workflows while keeping higher-risk destinations protected.

---

# What Is a Trusted App?

A Trusted App is an application that PasteGuard is allowed to treat as an approved destination.

When sensitive clipboard content is pasted into a Trusted App, PasteGuard may allow the original content instead of sanitizing it.

Conceptually:

```text
Sensitive Clipboard Content
          ↓
      PasteGuard
          ↓
      Trusted App
          ↓
         Allow
          ↓
    Original Content
```

Trusted Apps should be configured carefully.

---

# Why Trusted Apps Matter

Not every application should be treated the same way.

For example:

- A browser may be used for AI assistants, external portals, webmail, or support systems.
- An internal development tool may legitimately require access to a secret.
- A trusted IDE may be part of an approved development workflow.
- An enterprise tool may require original configuration values.

Without Trusted Apps, users may be forced to disable protection too broadly.

PasteGuard instead allows a more controlled model:

```text
Riskier Destinations
        ↓
Protected Apps
        ↓
Sanitize / Block
```

while:

```text
Approved Destinations
        ↓
Trusted Apps
        ↓
Allow Original Content
```

---

# Example Trusted Applications

Depending on the user's workflow, Trusted Apps may include:

- Visual Studio
- VS Code
- Approved internal development tools
- Approved enterprise applications
- Internal administrative tools
- Other explicitly trusted applications

These are examples only.

An application should be trusted only if the user or organization has a clear reason to allow original sensitive clipboard content.

---

# Trusted Apps vs Protected Apps

Trusted Apps and Protected Apps serve opposite purposes.

## Protected App

A Protected App is a destination where PasteGuard should protect clipboard content.

Example:

```text
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

can become:

```text
OPENAI_API_KEY=<OPENAI_API_KEY>
```

Flow:

```text
Sensitive Content
      ↓
Protected App
      ↓
PasteGuard
      ↓
Sanitize / Block
```

---

## Trusted App

A Trusted App is an explicitly approved destination where original content may be allowed.

Flow:

```text
Sensitive Content
      ↓
Trusted App
      ↓
PasteGuard
      ↓
Allow Original Content
```

For more information about protected destinations, see:

**[Protected Apps](protected-apps.md)**

---

# Example Workflow

A developer copies:

```text
DATABASE_URL=postgresql://admin:VeryStrongPassword123@db.example.com/app
```

## Pasting into a Protected App

PasteGuard can detect the database credential and sanitize it:

```text
DATABASE_URL=<POSTGRESQL_CREDENTIAL>
```

## Pasting into a Trusted App

If the destination application is explicitly trusted and policy permits it, PasteGuard may allow:

```text
DATABASE_URL=postgresql://admin:VeryStrongPassword123@db.example.com/app
```

This allows legitimate development work without disabling PasteGuard globally.

---

# Configure Trusted Apps Carefully

Trusted Apps effectively bypass sanitization when policy permits.

For that reason, avoid trusting an application simply because PasteGuard protection is inconvenient.

A good security approach is:

```text
Small Trusted App List
        +
Broad Protection Where Appropriate
```

Avoid:

```text
Large Trusted App List
        +
Minimal Effective Protection
```

Every trusted application increases the number of destinations where original sensitive clipboard content may be allowed.

---

# Recommended Trusted App Strategy

Use Trusted Apps for applications that:

- genuinely require original secrets
- are explicitly approved
- are part of trusted development workflows
- are internally managed
- have a clear business requirement
- are reviewed periodically

Do not trust applications simply because they are frequently used.

---

# Applications That Often Should Not Be Trusted by Default

Depending on your environment, use caution before trusting:

- web browsers
- AI assistants
- external chat applications
- email clients
- ticketing systems
- support portals
- social platforms
- unknown third-party tools
- external SaaS applications

These applications may represent destinations where sensitive information could leave your intended workflow.

---

# Trusted App Configuration

To configure a Trusted App:

1. Open PasteGuard.
2. Navigate to application protection settings.
3. Locate the Trusted Apps configuration.
4. Add or select the application you explicitly approve.
5. Confirm the application identity.
6. Save the configuration.
7. Test using synthetic credentials only.

The exact user interface may vary between PasteGuard versions.

---

# Test a Trusted App Safely

Always use synthetic credentials.

Example:

```text
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

Paste the value into a Trusted App.

If Trusted App policy permits original content, PasteGuard may allow the value unchanged.

Never test Trusted App behavior using a real production secret.

---

# Trusted Apps and Organization Policy

PasteGuard Organization can support centrally managed Trusted App policies.

Administrators may define which applications are trusted across managed devices.

Conceptually:

```text
Organization Policy
       ↓
Trusted App List
       ↓
Managed Windows Device
       ↓
PasteGuard Enforcement
```

Organization-managed settings may prevent users from modifying centrally controlled Trusted Apps.

---

# Organization-Managed Trusted Apps

Depending on policy configuration, administrators may control:

- which applications are trusted
- which applications are protected
- which applications are blocked
- whether users can add their own Trusted Apps
- whether users can remove organization-defined Trusted Apps
- whether local application settings can be changed
- whether organization policy overrides user settings

This helps maintain consistent clipboard-security behavior across managed environments.

For more information:

**[PasteGuard Organization](organization.md)**

---

# Trusted Apps and Blocked Apps

In an organization-managed environment, applications can conceptually fall into different policy groups.

```text
Application
    ↓
Policy Evaluation
    ↓
┌───────────────┬──────────────┬──────────────┐
│ Trusted       │ Protected    │ Blocked      │
├───────────────┼──────────────┼──────────────┤
│ Allow         │ Sanitize     │ Prevent      │
│ Original      │ / Evaluate   │ Paste        │
└───────────────┴──────────────┴──────────────┘
```

The exact action depends on organization configuration and active protection mode.

---

# Destination-Aware Protection

PasteGuard combines:

```text
Clipboard Content
       +
Destination Application
       +
Detector Configuration
       +
Protection Policy
       ↓
PasteGuard Decision
```

Possible outcomes include:

```text
Allow
Sanitize
Block
```

Trusted Apps are one part of this destination-aware model.

---

# Why Not Disable Protection Instead?

Without Trusted Apps, a user who needs to paste a legitimate secret may be tempted to pause PasteGuard.

That creates a broader security gap.

A Trusted App provides a more targeted approach:

```text
Disable Protection
→ Everything temporarily exposed
```

versus:

```text
Trusted App
→ Only explicitly approved destination allowed
```

Where supported by policy, the second approach provides more controlled behavior.

---

# Pause Restrictions

In managed environments, organization policy may restrict or prevent users from pausing protection.

Trusted Apps can help approved workflows continue without requiring global protection to be disabled.

---

# Trusted Apps and Local Processing

Trusted App evaluation is performed as part of PasteGuard's local policy flow.

Conceptually:

```text
Clipboard
   ↓
Local Detection
   ↓
Destination Identification
   ↓
Trusted App Evaluation
   ↓
Policy Decision
   ↓
Allow / Sanitize / Block
```

Core secret detection and destination-policy evaluation are performed locally on the Windows device.

> **No secret leaves your computer.**

---

# Security Considerations

Trusted Apps should be treated as a security-sensitive configuration.

Before adding an application, consider:

- Does this application genuinely require original secrets?
- Is the application controlled by you or your organization?
- Could the application transmit clipboard content externally?
- Is the application frequently updated or replaced?
- Could another executable be mistaken for the trusted application?
- Is the trust still required?

Review the Trusted Apps list periodically.

---

# Avoid Trusting Browsers Broadly

Browsers deserve special consideration because one browser process may access many unrelated destinations.

For example:

```text
Browser
├── Internal Portal
├── AI Assistant
├── Webmail
├── Public Website
├── Support Platform
└── External SaaS Tool
```

Trusting the entire browser may allow original sensitive clipboard content into all of those workflows depending on how application identification is configured.

Where possible, prefer a security posture that protects broadly shared destinations.

---

# Review Trusted Apps Regularly

Periodically review:

- applications still in use
- old development tools
- renamed executables
- replaced applications
- temporary tools
- applications that no longer need secrets

Remove unnecessary Trusted Apps.

A smaller trust list is generally easier to reason about.

---

# Troubleshooting

## Original Content Is Being Sanitized in a Trusted App

Check:

1. The application is actually configured as Trusted.
2. PasteGuard correctly identifies the application.
3. Organization policy is not overriding the local Trusted App configuration.
4. The application executable has not changed.
5. The active protection mode permits Trusted App behavior.
6. PasteGuard protection is running normally.

---

## Original Content Is Allowed in an Application That Should Be Protected

Check:

1. Whether the application has accidentally been added as Trusted.
2. Whether another application identity is being matched.
3. Whether organization policy defines it as Trusted.
4. Whether protection is paused.
5. Whether the detector is enabled.
6. Whether the content is actually detected as sensitive.

If you believe this is a product issue, report it using synthetic data only.

---

## Application Identity Changed

Application updates can sometimes change executable names or application identity.

If Trusted App behavior changes after an update:

1. verify the installed application
2. review the Trusted Apps list
3. remove obsolete entries
4. add the current approved application if required
5. test with synthetic data

---

# Reporting Trusted App Issues

When reporting a Trusted App issue, include:

- application name
- application/process name if known
- expected behavior
- actual behavior
- PasteGuard version
- whether the device is organization-managed
- synthetic test input

Never submit a real credential.

---

# Security Issues

If you discover a way to bypass Protected App or Trusted App enforcement unexpectedly, treat it as a potential security issue.

Do not publish exploit details or sensitive information in a public issue.

Report security concerns privately:

**hello@mindatwork.co.in**

See:

**[Security Policy](../SECURITY.md)**

---

# Related Documentation

- **[Getting Started](getting-started.md)**
- **[Detector Coverage](detectors.md)**
- **[Protected Apps](protected-apps.md)**
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