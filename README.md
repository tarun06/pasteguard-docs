# PasteGuard for Windows

### Stop Secrets Before They Leak.

**PasteGuard** is a local-first clipboard security utility for Windows that helps prevent accidental exposure of secrets and sensitive data during copy and paste.

It detects sensitive clipboard content before it reaches the wrong application and can automatically **sanitize, block, or allow** the content based on your protection settings.

**100+ Secret & Sensitive-Data Detectors** · **Protected Apps** · **Trusted Apps** · **Local-First Privacy**

> **No secret leaves your computer.**

[Get PasteGuard from Microsoft Store]
https://github.com/tarun06/pasteguard-docs/blob/main/assets/pasteguard-secret-detectors-plans.png

---
![PasteGuard secret detectors and Free, Pro, Organization plans]
https://github.com/tarun06/pasteguard-docs/blob/2bae0a38d68fa3fdb750ff14668bacdabf80c2b9/assets/pasteguard-secret-detectors-plans.png

![WalkThrough]
https://github.com/tarun06/pasteguard-docs/blob/2bae0a38d68fa3fdb750ff14668bacdabf80c2b9/assets/pasteguard-walkthrough.gif

![Demo]
https://github.com/tarun06/pasteguard-docs/blob/2bae0a38d68fa3fdb750ff14668bacdabf80c2b9/assets/pasteguard-demo.gif

---

## See PasteGuard in Action

Add your demo GIF here:

```markdown
![PasteGuard Demo](assets/pasteguard-demo.gif)
```

Recommended demo flow:

```text
Copy API key
    ↓
Switch to protected application
    ↓
Paste
    ↓
PasteGuard detects sensitive content
    ↓
Safe placeholder is pasted
```

---

# Copy → Detect → Sanitize → Paste

PasteGuard protects sensitive clipboard content before it reaches the destination application.

Example:

```text
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz
                         ↓
               PasteGuard detects it
                         ↓
OPENAI_API_KEY=<OPENAI_API_KEY>
```

PasteGuard can help protect:

- API keys
- Passwords
- Access tokens
- Cloud credentials
- Database credentials
- Connection strings
- Private keys
- Authentication tokens
- DevOps credentials
- Payment information
- Banking information
- Identity information
- Other sensitive data

---

# Why PasteGuard?

Developers and professionals copy sensitive information every day.

A normal workflow may look like:

```text
Copy
  ↓
Switch Window
  ↓
Paste
```

One wrong paste can expose sensitive data to:

- AI assistants
- Browsers
- Chat applications
- Email clients
- Microsoft Teams
- Ticketing systems
- Support portals
- External websites
- Other unintended applications

Traditional secret scanners often detect credentials only after they have already been committed, uploaded, logged, or shared.

PasteGuard works earlier:

```text
Copy
  ↓
Detect
  ↓
Evaluate Destination
  ↓
Sanitize / Block / Allow
  ↓
Paste
```

The goal is simple:

> Protect sensitive information before exposure occurs.

---

# Key Features

- Automatic clipboard protection
- **100+ secret and sensitive-data detectors**
- Secret sanitization before paste
- Blocking based on protection policy
- Protected Apps
- Trusted Apps
- Secure Paste
- Configurable detector selection
- Protection modes
- Pause and resume protection
- System tray controls
- Local activity history
- Local-only detection
- Sensitive-data protection
- Organization-managed security policies

---

# 100+ Secret & Sensitive-Data Detectors

PasteGuard supports detection across multiple security categories.

## AI

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

## Cloud

Examples include:

- AWS
- Azure
- Google Cloud
- Azure DevOps
- Cloudflare
- DigitalOcean
- Firebase
- Supabase
- Azure Storage
- Azure Service Bus
- Azure Event Hubs
- Azure Cosmos DB
- Azure Redis

---

## Source Control

Examples include:

- GitHub
- GitHub Fine-Grained PAT
- GitLab
- Bitbucket
- Azure DevOps PAT

---

## Databases

Examples include:

- MongoDB
- PostgreSQL
- MySQL
- Redis
- SQL Server
- Oracle
- Snowflake
- Elasticsearch
- Database URLs
- Connection strings

---

## DevOps & Infrastructure

Examples include:

- Docker
- Docker Registry
- Kubernetes
- HashiCorp Vault
- Terraform Cloud
- Pulumi
- CircleCI
- Jenkins
- JFrog
- SonarQube
- Consul
- Nomad
- Databricks

---

## Package Registries

Examples include:

- npm
- PyPI
- NuGet
- GitHub Packages

---

## Messaging

Examples include:

- Slack
- Telegram
- Discord
- RabbitMQ
- AMQP
- Kafka
- Confluent Cloud

---

## Monitoring & Observability

Examples include:

- Datadog
- New Relic
- Sentry
- Grafana
- Splunk

---

## SaaS

Examples include:

- Stripe
- Twilio
- SendGrid
- Mailchimp
- Vercel
- Netlify
- Heroku
- Atlassian
- Jira
- Salesforce
- Notion
- Shopify
- PayPal
- Clerk
- Linear
- Asana
- Dropbox
- Square
- Razorpay
- Algolia
- HubSpot
- Zendesk

---

## Email Services

Examples include:

- Mailgun
- Postmark
- Resend

---

## Payment Providers

Examples include:

- CyberSource
- Stripe
- Razorpay
- PayPal

---

## Authentication

PasteGuard can detect:

- Passwords
- Bearer tokens
- Basic Authentication credentials
- OAuth client secrets
- JWTs
- Credentials embedded in URLs

---

## Keys & Certificates

PasteGuard can detect:

- RSA private keys
- EC private keys
- OpenSSH private keys
- PKCS#12 / PFX passwords
- Java Keystore passwords
- Other supported private-key formats

---

# Sensitive Data Protection

PasteGuard can also protect sensitive personal and financial data.

## Payment Information

Supported examples include:

- Credit card numbers
- Debit card numbers
- CVV
- CVC
- Card expiry dates

Example:

```json
{
  "CardNumber": "4111111111111111",
  "ExpiryDate": "12/30",
  "CVV": "123"
}
```

PasteGuard can sanitize this into:

```json
{
  "CardNumber": "<CARD_NUMBER>",
  "ExpiryDate": "<CARD_EXPIRY>",
  "CVV": "<CVV>"
}
```

---

## Banking Information

Supported examples include:

- IBAN
- Bank account numbers

Example:

```json
{
  "IBAN": "GB82WEST12345698765432",
  "AccountNumber": "1234567890123456"
}
```

Sanitized:

```json
{
  "IBAN": "<IBAN>",
  "AccountNumber": "<BANK_ACCOUNT_NUMBER>"
}
```

---

## Identity Information

Supported examples include:

- Emirates ID
- Passport numbers

Example:

```json
{
  "EmiratesId": "784-1987-1234567-1",
  "PassportNumber": "N1234567"
}
```

Sanitized:

```json
{
  "EmiratesId": "<EMIRATES_ID>",
  "PassportNumber": "<PASSPORT_NUMBER>"
}
```

---

## Optional Personal Data Protection

PasteGuard can optionally protect:

- Email addresses
- Phone numbers
- Date of birth

These detectors can be enabled when broader PII protection is required.

---

# Protected Apps

PasteGuard lets you choose which applications should receive sanitized clipboard content.

Protected destinations may include:

- Browsers
- AI assistants
- Chat applications
- Microsoft Teams
- Email clients
- Ticketing systems
- Support portals
- External websites
- Other applications selected by the user

When sensitive content is pasted into a protected application, PasteGuard can sanitize or block the content according to the active protection policy.

Example:

```text
Original:

sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

becomes:

```text
<OPENAI_API_KEY>
```

---

# Trusted Apps

Not every application needs clipboard sanitization.

PasteGuard supports **Trusted Apps**.

Approved applications can receive the original clipboard content when explicitly allowed.

Examples may include:

- Visual Studio
- VS Code
- Internal development tools
- Approved enterprise applications
- Other trusted applications selected by the user

This allows PasteGuard to protect risky destinations without disrupting trusted workflows.

```text
Protected App

Sensitive Content
      ↓
   Sanitize
      ↓
Safe Placeholder
```

```text
Trusted App

Sensitive Content
      ↓
    Allow
      ↓
Original Content
```

In managed environments, Trusted App policies can also be controlled by organization policy.

---

# Local-First Privacy

PasteGuard is designed around **local processing**.

Secret detection, sensitive-data detection, policy evaluation, and sanitization are performed locally on your Windows device.

Clipboard secrets do not need to be uploaded to a cloud-based detection service or external AI service.

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

Raw detected secrets are not intentionally stored in PasteGuard activity history.

## No secret leaves your computer.

Microsoft Store licensing, application updates, entitlement verification, and purchases may communicate with Microsoft services, but clipboard secrets are not sent to Microsoft as part of PasteGuard's secret-detection functionality.

---

# Example Detection

Input:

```json
{
  "OPENAI_API_KEY": "sk-proj-abcdefghijklmnopqrstuvwxyz123456",
  "AWS_ACCESS_KEY_ID": "AKIAIOSFODNN7EXAMPLE",
  "GITHUB_TOKEN": "ghp_abcdefghijklmnopqrstuvwxyz123456",
  "CardNumber": "4111111111111111",
  "IBAN": "GB82WEST12345698765432",
  "EmiratesId": "784-1987-1234567-1"
}
```

PasteGuard can produce:

```json
{
  "OPENAI_API_KEY": "<OPENAI_API_KEY>",
  "AWS_ACCESS_KEY_ID": "<AWS_ACCESS_KEY>",
  "GITHUB_TOKEN": "<GITHUB_TOKEN>",
  "CardNumber": "<CARD_NUMBER>",
  "IBAN": "<IBAN>",
  "EmiratesId": "<EMIRATES_ID>"
}
```

---

# Protection Modes

Depending on configuration and policy, PasteGuard can:

```text
Detect
Sanitize
Block
Allow
```

Protection can also be paused and resumed when permitted by policy.

---

# PasteGuard Free

**PasteGuard Free is a permanent free edition.**

It is not a time-limited trial and does not expire.

Free includes core clipboard protection and **12 essential secret detectors**:

- Passwords
- Private keys
- Generic API keys
- Generic secrets
- Bearer tokens
- JSON Web Tokens
- Basic Authentication
- Connection strings
- AWS credentials
- Azure secrets
- GitHub tokens
- OpenAI API keys

Core Free functionality remains available without a paid upgrade.

---

# PasteGuard Pro

**PasteGuard Pro** is an optional paid upgrade for users who require broader secret and sensitive-data protection.

Pro includes:

- 100+ detectors
- AI credential detection
- Cloud credential detection
- Database credential detection
- DevOps and infrastructure detection
- Source-control credential detection
- SaaS credential detection
- Authentication detection
- Payment information detection
- Banking information detection
- Identity information detection
- Advanced sensitive-data protection
- Configurable detector selection

PasteGuard Pro is not a time-limited trial.

---

# PasteGuard Organization

**PasteGuard Organization** is designed for companies, teams, and managed Windows environments.

Organization includes the full detector capabilities available with Pro together with management and policy-enforcement features.

Capabilities can include:

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

Organization functionality requires a valid Organization entitlement and appropriate administrator configuration.

---

# Editions

| Capability | Free | Pro | Organization |
|---|:---:|:---:|:---:|
| Clipboard Protection | ✅ | ✅ | ✅ |
| 12 Essential Detectors | ✅ | ✅ | ✅ |
| 100+ Detectors | — | ✅ | ✅ |
| Sensitive Data Protection | — | ✅ | ✅ |
| Protected Apps | ✅ | ✅ | ✅ |
| Trusted Apps | ✅ | ✅ | ✅ |
| Local Detection | ✅ | ✅ | ✅ |
| Managed Policies | — | — | ✅ |
| Enforced Settings | — | — | ✅ |
| Organization Controls | — | — | ✅ |

---

# Built for Developers

PasteGuard is especially useful for:

- Software developers
- DevOps engineers
- Cloud engineers
- Security engineers
- Platform teams
- IT administrators
- Support teams
- Enterprise users
- Organizations handling sensitive information

Common workflows include:

```text
.env files
appsettings.json
Azure configuration
AWS credentials
CI/CD secrets
Database connection strings
API testing
Developer consoles
AI assistants
Support portals
Production troubleshooting
```

---

# Technology

PasteGuard is built for Windows using technologies including:

```text
C#
.NET
.NET MAUI
Windows Clipboard APIs
Local secret-detection engine
```

The detection engine combines:

- Provider-specific patterns
- Context-aware detection
- Validation rules
- Detector priorities
- Secret format validation
- Overlap handling
- False-positive reduction
- Local sanitization

---

# Security Philosophy

PasteGuard follows a simple principle:

> **Protect sensitive information before exposure occurs.**

Traditional flow:

```text
Secret
   ↓
Accidental Paste
   ↓
Exposure
   ↓
Scanner / Alert
   ↓
Incident Response
```

PasteGuard flow:

```text
Secret
   ↓
Clipboard
   ↓
PasteGuard
   ↓
Detect
   ↓
Sanitize / Block
   ↓
Safe Paste
```

---

# Getting Started

## 1. Install PasteGuard

Get PasteGuard from Microsoft Store.

**Microsoft Store Product ID**

```text
9NL0497QC6ZK
```

Install:

https://apps.microsoft.com/detail/9nl0497qc6zk

---

## 2. Launch PasteGuard

Start PasteGuard and enable clipboard protection.

---

## 3. Configure Protected Apps

Choose applications where sensitive clipboard content should be protected.

---

## 4. Configure Trusted Apps

Choose approved applications that may receive original clipboard content.

---

## 5. Configure Detectors

Enable detector categories appropriate for your workflow.

---

## 6. Test PasteGuard

Use synthetic credentials only.

Example:

```text
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

Never test using a real production credential.

---

# What's New

Recent improvements include:

- Expanded protection with **100+ secret and sensitive-data detectors**
- Payment card detection
- CVV/CVC detection
- Card expiry detection
- IBAN protection
- Bank account detection
- Emirates ID protection
- Passport number protection
- Optional email protection
- Optional phone-number protection
- Optional date-of-birth protection
- Azure Cosmos DB credential detection
- Azure Redis credential detection
- Databricks token detection
- Splunk HEC token detection
- Confluent Cloud detection
- HubSpot token detection
- Zendesk token detection
- CyberSource credential detection
- Docker Registry authentication detection
- OpenSSH private-key detection
- Improved JSON-formatted secret detection
- Improved quoted configuration-key detection
- Improved Azure Service Bus detection
- Improved Azure Event Hubs detection
- Improved Azure Storage detection
- Improved Azure DevOps PAT detection
- Improved Cloudflare detection
- Improved Supabase detection
- Improved Hugging Face detection
- Improved Replicate detection
- Improved sanitization accuracy
- Reduced partial secret exposure
- Reduced false positives

---

# Screenshots

Add your real PasteGuard screenshots under the `assets` folder.

Recommended files:

```text
assets/dashboard.png
assets/detectors.png
assets/protected-apps.png
assets/trusted-apps.png
assets/organization.png
```

Example:

```markdown
## Dashboard

![PasteGuard Dashboard](assets/dashboard.png)

## Detector Configuration

![PasteGuard Detectors](assets/detectors.png)

## Protected Apps

![PasteGuard Protected Apps](assets/protected-apps.png)

## Trusted Apps

![PasteGuard Trusted Apps](assets/trusted-apps.png)

## Organization Policies

![PasteGuard Organization](assets/organization.png)
```

---

# Demo

Add your PasteGuard demo GIF as:

```text
assets/pasteguard-demo.gif
```

Then add:

```markdown
![PasteGuard Demo](assets/pasteguard-demo.gif)
```

A good demo should show:

```text
Copy API Key
      ↓
Switch to Protected App
      ↓
Paste
      ↓
PasteGuard Detects
      ↓
<OPENAI_API_KEY>
```

---

# Security

Security is central to PasteGuard.

If you discover a potential security vulnerability, **do not publish sensitive details through a public GitHub Issue**.

Report security issues privately:

**hello@mindatwork.co.in**

Please include:

- Description
- Steps to reproduce
- PasteGuard version
- Relevant logs with secrets removed
- Screenshots with sensitive information removed

Never include:

- Real passwords
- API keys
- Access tokens
- Private keys
- Credit-card information
- Production credentials
- Personal sensitive data

---

# Privacy

PasteGuard is designed around local processing.

Sensitive clipboard content is processed locally for detection and sanitization.

PasteGuard does not require clipboard secrets to be sent to a remote AI service.

Raw detected secrets are not intentionally stored in activity history.

For privacy questions:

**hello@mindatwork.co.in**

---

# Feature Requests

We welcome feedback from:

- Developers
- DevOps engineers
- Security professionals
- Enterprise IT teams
- Windows users

Useful requests include:

- New detector support
- False-positive reports
- False-negative reports
- Protected App improvements
- Trusted App improvements
- Organization policy requirements
- UX improvements

---

# New Detector Requests

If PasteGuard does not currently recognize a credential format you use, open an issue.

Please provide:

- Provider/product
- Credential type
- Public provider documentation
- Synthetic example
- Expected PasteGuard replacement

Example:

```text
Provider:
ExampleCloud

Secret Type:
API Token

Synthetic Format:
example_test_abcdefghijklmnopqrstuvwxyz

Expected:
<EXAMPLECLOUD_TOKEN>
```

## Never submit a real secret.

---

# Support PasteGuard

If PasteGuard is useful to you:

⭐ Star this repository

🛡️ Request a new detector

💡 Suggest a feature

🐛 Report an issue

📣 Share PasteGuard with developers and security teams

---

# Microsoft Store

PasteGuard is distributed through Microsoft Store.

## Get PasteGuard

https://apps.microsoft.com/detail/9nl0497qc6zk

Microsoft Store Product ID:

```text
9NL0497QC6ZK
```

---

# Contact

**Publisher:** Mind At Work

**Product:** PasteGuard

**Website:**  
https://mindatwork.co.in

**Email:**  
hello@mindatwork.co.in

---

# About This Repository

This repository contains public documentation, screenshots, product information, release information, and supporting resources for PasteGuard.

**PasteGuard is proprietary software.**

The production PasteGuard application source code is maintained privately and is not published in this repository.

Do not use this repository as a source for production PasteGuard binaries unless explicitly provided by Mind At Work.

---

# License

PasteGuard is proprietary software developed by **Mind At Work**.

This repository contains public documentation and product resources relating to PasteGuard.

The PasteGuard application source code is not distributed through this repository.

Unless explicitly stated otherwise, all PasteGuard software, branding, documentation, and associated materials remain the property of Mind At Work.

Copyright © Mind At Work. All rights reserved.

---

# PasteGuard

## Stop Secrets Before They Leak.

### 100+ Secret & Sensitive-Data Detectors

### Protected Apps

### Trusted Apps

### Local-First Protection

### No secret leaves your computer.
