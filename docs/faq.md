# PasteGuard FAQ

Frequently asked questions about PasteGuard.

---

# General

## What is PasteGuard?

PasteGuard is a local-first clipboard security utility for Windows.

It helps prevent accidental exposure of secrets and sensitive data during copy-and-paste workflows.

PasteGuard can detect supported sensitive values and apply protection based on the destination application and active policy.

Possible actions include:

- Allow
- Sanitize
- Block

---

## What problem does PasteGuard solve?

Developers and professionals frequently copy:

- API keys
- Passwords
- Access tokens
- Connection strings
- Private keys
- Cloud credentials
- Database credentials
- Payment information
- Identity information

One wrong paste into a browser, AI assistant, chat application, support portal, or email client can expose sensitive information.

PasteGuard helps protect the paste step before the original value reaches the destination.

---

## How does PasteGuard work?

Conceptually:

```text
Copy
  ↓
PasteGuard Detects
  ↓
Destination Evaluated
  ↓
Policy Applied
  ↓
Allow / Sanitize / Block
  ↓
Paste
```

---

## Does PasteGuard scan everything I copy?

PasteGuard evaluates clipboard content as part of its protection workflow according to the configured behavior and active settings.

The exact behavior depends on:

- enabled detectors
- protection mode
- destination application
- Trusted App configuration
- Protected App configuration
- organization policy

---

## Is PasteGuard available for Windows?

Yes.

PasteGuard is built for Windows.

Get it from Microsoft Store:

https://apps.microsoft.com/detail/9nl0497qc6zk

Product ID:

```text
9NL0497QC6ZK
```

---

# Privacy

## Does PasteGuard send my clipboard to the cloud?

PasteGuard is designed around local processing.

Core secret detection, sensitive-data detection, policy evaluation, and sanitization are performed locally on the Windows device.

Clipboard secrets do not need to be sent to:

- external AI services
- remote secret scanners
- cloud detection APIs

---

## Does PasteGuard use AI to scan my clipboard?

PasteGuard does not require remote AI processing to perform its core secret-detection workflow.

Detection is designed to happen locally.

---

## Does PasteGuard send clipboard secrets to Microsoft?

Clipboard secrets are not sent to Microsoft as part of PasteGuard's secret-detection functionality.

Microsoft Store licensing, purchases, entitlement verification, and application updates may communicate with Microsoft services.

---

## Does PasteGuard store raw secrets?

PasteGuard is designed so raw detected secrets are not intentionally stored in activity history.

---

## Is PasteGuard completely offline?

Core detection is local.

However, some application functionality may involve online services such as:

- Microsoft Store licensing
- entitlement verification
- purchases
- application updates

Clipboard secrets are not required to be uploaded for core detection.

---

# Detection

## How many detectors does PasteGuard support?

PasteGuard supports **100+ secret and sensitive-data detectors** across multiple categories.

For the current public detector catalog, see:

**[Detector Coverage](detectors.md)**

---

## What categories are supported?

PasteGuard supports detector categories including:

- AI
- Cloud
- Source Control
- Databases
- DevOps & Infrastructure
- Package Registries
- Messaging
- Monitoring & Observability
- SaaS
- Authentication
- Identity
- Keys & Certificates
- Email Services
- Generic Secrets
- Sensitive Data

---

## Does PasteGuard detect API keys?

Yes.

PasteGuard supports provider-specific and generic API-key detection.

Examples include:

- OpenAI
- Anthropic
- Google Cloud
- GitHub
- GitLab
- Stripe
- Twilio
- SendGrid
- Datadog
- Cloudflare
- and many more

---

## Does PasteGuard detect passwords?

Yes.

Password detection is included in the Free detector set.

---

## Does PasteGuard detect JWTs?

Yes.

PasteGuard supports JSON Web Token detection.

JWT detection is included in the Free edition.

---

## Does PasteGuard detect private keys?

Yes.

PasteGuard supports private-key detection, including supported formats such as:

- RSA
- EC
- OpenSSH

Private-key detection is included in the Free edition.

---

## Does PasteGuard detect connection strings?

Yes.

PasteGuard supports database and service connection-string detection.

Connection-string detection is included in the Free edition.

---

## Does PasteGuard detect AWS credentials?

Yes.

PasteGuard can detect supported AWS credential types including access credentials, secret access keys, and session tokens.

Core AWS credential protection is included in the Free edition.

---

## Does PasteGuard detect Azure credentials?

Yes.

Supported Azure-related detections include examples such as:

- Azure secrets
- Azure client secrets
- Azure DevOps PATs
- Azure SAS tokens
- Azure Storage connection strings
- Azure Service Bus credentials
- Azure Event Hubs credentials

Core Azure secret protection is included in the Free edition.

---

## Does PasteGuard detect GitHub tokens?

Yes.

Supported GitHub-related detection includes:

- GitHub Token
- GitHub Fine-Grained PAT
- GitHub Packages credentials

Core GitHub token detection is included in the Free edition.

---

## Does PasteGuard detect AI API keys?

Yes.

Examples include:

- OpenAI
- Anthropic
- Hugging Face
- Groq
- Mistral
- Cohere
- Perplexity
- Replicate

---

# Sensitive Data

## Does PasteGuard detect payment card numbers?

Yes.

PasteGuard supports payment-card-number detection as part of sensitive-data protection.

---

## Does PasteGuard detect CVV or CVC values?

Yes.

PasteGuard supports contextual detection of supported card security codes such as:

- CVV
- CVC

---

## Does PasteGuard detect card expiry dates?

Yes.

PasteGuard supports contextual card-expiry detection.

---

## Does PasteGuard detect IBANs?

Yes.

PasteGuard supports IBAN detection.

---

## Does PasteGuard detect bank account numbers?

Yes.

PasteGuard supports contextual bank-account-number detection.

---

## Does PasteGuard detect Emirates ID?

Yes.

PasteGuard supports UAE Emirates ID detection.

---

## Does PasteGuard detect passport numbers?

Yes.

PasteGuard supports contextual passport-number detection.

---

## Does PasteGuard detect email addresses?

Email-address detection can be enabled when broader PII protection is required.

---

## Does PasteGuard detect phone numbers?

Phone-number detection can be enabled when broader PII protection is required.

---

## Does PasteGuard detect date of birth?

Date-of-birth detection can be enabled when broader PII protection is required.

---

# Protected Apps

## What is a Protected App?

A Protected App is a destination where PasteGuard should apply clipboard protection.

If sensitive content is detected, PasteGuard can sanitize or block it according to the active policy.

See:

**[Protected Apps](protected-apps.md)**

---

## What types of apps can I protect?

Examples may include:

- browsers
- AI assistants
- chat applications
- Microsoft Teams
- email clients
- ticketing systems
- support portals
- other applications selected by the user

---

## Can PasteGuard sanitize secrets before paste?

Yes.

For example:

```text
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

can become:

```text
OPENAI_API_KEY=<OPENAI_API_KEY>
```

---

## Can PasteGuard block a paste completely?

Yes, where the active protection mode or policy requires blocking.

---

# Trusted Apps

## What is a Trusted App?

A Trusted App is an explicitly approved application that may receive original clipboard content when policy permits.

See:

**[Trusted Apps](trusted-apps.md)**

---

## Why would I use Trusted Apps?

Some applications legitimately require access to original secrets.

Examples may include:

- Visual Studio
- VS Code
- internal development tools
- approved enterprise applications

Trusted Apps make it possible to allow approved workflows without globally disabling PasteGuard protection.

---

## Should I trust my browser?

Use caution.

A browser can access many unrelated destinations:

```text
Browser
├── AI Assistant
├── Webmail
├── Public Website
├── Internal Portal
├── Ticketing System
└── External SaaS
```

Broadly trusting a browser may reduce protection depending on how destination identification is configured.

Only trust applications that genuinely require original sensitive content.

---

## Can an organization control Trusted Apps?

Yes.

PasteGuard Organization can support centrally managed Trusted App policies.

---

# Editions

## Is PasteGuard free?

Yes.

PasteGuard Free is a permanent free edition.

It is not a time-limited trial and does not expire.

---

## What is included in PasteGuard Free?

PasteGuard Free includes core clipboard protection and 12 essential detectors:

1. Password
2. Private Key
3. Generic API Key
4. Generic Secret
5. Bearer Token
6. JWT
7. Basic Authentication
8. Connection String
9. AWS Credentials
10. Azure Secrets
11. GitHub Token
12. OpenAI API Key

---

## What is PasteGuard Pro?

PasteGuard Pro is an optional paid upgrade that unlocks the broader detector catalog.

It includes 100+ supported detector types across areas such as:

- AI
- Cloud
- Databases
- DevOps
- Source Control
- SaaS
- Monitoring
- Authentication
- Sensitive Data

---

## Is Pro a trial?

No.

PasteGuard Pro is not a time-limited trial.

---

## What is PasteGuard Organization?

PasteGuard Organization is intended for businesses and managed Windows environments.

It includes broader detector coverage plus organization-level controls such as:

- centrally managed detector configuration
- Trusted App policies
- Blocked App policies
- enforced settings
- pause restrictions
- organization policy versioning

See:

**[PasteGuard Organization](organization.md)**

---

## Is Organization a trial?

No.

PasteGuard Organization is not a time-limited trial.

---

## Where can I compare editions?

See:

**[Free vs Pro vs Organization](free-vs-pro.md)**

---

# Testing

## How should I test PasteGuard?

Always use synthetic credentials.

Example:

```text
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

Never use a real production credential just to verify detection.

---

## Can I test payment-card detection?

Yes, but use recognized synthetic test values only.

Example:

```json
{
  "CardNumber": "4111111111111111",
  "ExpiryDate": "12/30",
  "CVV": "123"
}
```

Do not use a real payment card.

---

## Can I test identity-data detection?

Yes, using synthetic examples only.

Do not publish or test with a real person's:

- Emirates ID
- passport number
- bank account information
- phone number
- date of birth

---

# False Positives and False Negatives

## What is a false positive?

A false positive occurs when safe content is incorrectly classified as sensitive.

If this happens, open a GitHub issue with:

- detector name
- synthetic example
- expected behavior
- actual behavior
- PasteGuard version

---

## What is a false negative?

A false negative occurs when a supported secret is not detected.

Report it with synthetic data only.

---

## What if my provider is not supported?

Open a Detector Request.

Include:

- provider name
- credential type
- public documentation
- synthetic format
- expected replacement

Never include a real credential.

---

# Activity History

## Does PasteGuard keep activity history?

PasteGuard can maintain local activity information for supported protection events.

---

## Does history contain my raw secret?

PasteGuard is designed so raw detected secrets are not intentionally stored in activity history.

---

# Pause and Resume

## Can I pause PasteGuard?

Pause and resume functionality may be available depending on configuration.

In organization-managed environments, administrators may restrict pause functionality.

---

## Why would an organization disable pause?

To reduce periods where users could temporarily disable clipboard protection.

Trusted Apps can provide a more targeted alternative for approved workflows.

---

# Organization Management

## Can an administrator choose detectors?

PasteGuard Organization can support managed detector configuration.

---

## Can an administrator prevent users from changing settings?

Organization-controlled settings may be locked so local users cannot modify them.

---

## Can an administrator block certain applications?

PasteGuard Organization can support policies for blocked applications.

---

## Can an administrator enforce Trusted Apps?

Yes, depending on organization policy configuration.

---

## Can policies have versions?

Organization policies can include identification and version information to help with deployment and troubleshooting.

---

# Security

## How do I report a security issue?

Do not publish sensitive vulnerability information through a public GitHub issue.

Report security concerns privately:

**hello@mindatwork.co.in**

See:

**[Security Policy](../SECURITY.md)**

---

## What should I never post in a GitHub issue?

Never post:

- production passwords
- API keys
- access tokens
- private keys
- certificate passwords
- customer credentials
- payment information
- real identity information
- real bank details
- other production secrets

---

# Troubleshooting

## PasteGuard does not detect my test credential

Check:

1. The relevant detector is enabled.
2. Your PasteGuard edition includes the detector.
3. Protection is active.
4. The test value uses a supported synthetic format.
5. Organization policy is not overriding your local settings.

---

## PasteGuard does not sanitize in a Protected App

Check:

1. The application is configured as Protected.
2. Protection is not paused.
3. The detector is enabled.
4. The content is recognized.
5. Your active policy permits sanitization.
6. Organization policy is not changing the behavior.

---

## PasteGuard sanitizes content in a Trusted App

Check:

1. The application is actually configured as Trusted.
2. The application identity matches the configured entry.
3. Organization policy is not overriding the local configuration.
4. The installed application has not changed identity after an update.

---

## PasteGuard allows original content where I expected sanitization

Check:

1. The application is not accidentally Trusted.
2. Protection is active.
3. The relevant detector is enabled.
4. Organization policy is correct.
5. The application identity matches the expected destination.

---

# Microsoft Store

## Where can I install PasteGuard?

PasteGuard is available through Microsoft Store:

https://apps.microsoft.com/detail/9nl0497qc6zk

Product ID:

```text
9NL0497QC6ZK
```

---

## Where do I find current pricing?

Current pricing, billing options, availability, and market-specific information are shown by Microsoft Store.

---

# Support

## Where can I ask a question?

You can use GitHub Issues or Discussions for non-sensitive product questions.

Do not post real secrets.

---

## How do I request a feature?

Open a GitHub Feature Request.

Useful requests include:

- new detector support
- Protected App improvements
- Trusted App improvements
- UX improvements
- organization-policy requirements
- false-positive improvements
- false-negative improvements

---

## How do I contact PasteGuard?

**Publisher:** Mind At Work

**Website:**  
https://mindatwork.co.in

**Email:**  
hello@mindatwork.co.in

---

# Related Documentation

- **[Getting Started](getting-started.md)**
- **[Detector Coverage](detectors.md)**
- **[Protected Apps](protected-apps.md)**
- **[Trusted Apps](trusted-apps.md)**
- **[Free vs Pro vs Organization](free-vs-pro.md)**
- **[PasteGuard Organization](organization.md)**
- **[Privacy](../PRIVACY.md)**
- **[Security](../SECURITY.md)**
- **[Changelog](../CHANGELOG.md)**

---

# PasteGuard

## Stop Secrets Before They Leak.

**100+ Secret & Sensitive-Data Detectors**

**Protected Apps**

**Trusted Apps**

**Local-First Protection**

> **No secret leaves your computer.**

### Get PasteGuard for Windows

https://apps.microsoft.com/detail/9nl0497qc6zk