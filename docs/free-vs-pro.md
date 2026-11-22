# PasteGuard Editions

PasteGuard is available in three editions:

- **PasteGuard Free**
- **PasteGuard Pro**
- **PasteGuard Organization**

Each edition is designed for a different level of clipboard protection and management.

---

# Overview

| Capability | Free | Pro | Organization |
|---|:---:|:---:|:---:|
| Clipboard Protection | ✅ | ✅ | ✅ |
| Permanent Free Usage | ✅ | — | — |
| 12 Essential Detectors | ✅ | ✅ | ✅ |
| 100+ Detector Catalog | — | ✅ | ✅ |
| Sensitive Data Protection | — | ✅ | ✅ |
| Protected Apps | ✅ | ✅ | ✅ |
| Trusted Apps | ✅ | ✅ | ✅ |
| Secure Paste | ✅ | ✅ | ✅ |
| Configurable Detector Selection | Limited | ✅ | Managed |
| Local Detection | ✅ | ✅ | ✅ |
| Local Activity History | ✅ | ✅ | ✅ |
| Pause / Resume Protection | ✅ | ✅ | Policy Controlled |
| Managed Detector Policies | — | — | ✅ |
| Managed Trusted Apps | — | — | ✅ |
| Managed Blocked Apps | — | — | ✅ |
| Enforced Protection Settings | — | — | ✅ |
| Organization Policy Versioning | — | — | ✅ |
| Prevention of Changes to Managed Settings | — | — | ✅ |

Availability of individual capabilities may depend on the current PasteGuard version and active policy.

---

# PasteGuard Free

## Permanent Free Protection

**PasteGuard Free is a permanent free edition.**

It is not a time-limited trial.

It does not expire.

Core Free protection remains available without requiring a paid upgrade.

PasteGuard Free is intended for users who want essential clipboard-security protection for common secret types.

---

# Free Detector Coverage

PasteGuard Free includes **12 essential secret detectors**:

1. Password
2. Private Key
3. Generic API Key
4. Generic Secret
5. Bearer Token
6. JSON Web Token (JWT)
7. Basic Authentication
8. Connection String
9. AWS Credentials
10. Azure Secrets
11. GitHub Token
12. OpenAI API Key

These detectors cover many common developer and credential-leak scenarios.

---

# Free Use Cases

PasteGuard Free can be useful for:

- Individual developers
- Students
- Independent consultants
- Personal development environments
- Basic API-key protection
- Password protection
- Private-key protection
- Common cloud credential protection
- GitHub credential protection
- OpenAI API-key protection

---

# PasteGuard Pro

## Broader Secret and Sensitive-Data Protection

**PasteGuard Pro** is an optional paid upgrade.

Pro is intended for users who regularly work with a broader range of:

- Cloud providers
- AI platforms
- DevOps systems
- Databases
- SaaS applications
- Authentication systems
- Payment information
- Banking information
- Identity information
- Sensitive personal data

PasteGuard Pro is not a time-limited trial.

---

# 100+ Detector Coverage

PasteGuard Pro unlocks the broader PasteGuard detector catalog with **100+ secret and sensitive-data detectors**.

Coverage includes:

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

---

## Source Control

Examples include:

- GitHub
- GitHub Fine-Grained PAT
- GitLab
- Bitbucket

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
- AMQP
- RabbitMQ
- Kafka

---

## Monitoring & Observability

Examples include:

- Datadog
- New Relic
- Sentry
- Grafana

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

---

## Authentication

Examples include:

- Passwords
- Bearer tokens
- Basic Authentication
- OAuth client secrets
- JWTs
- URL credentials

---

## Keys & Certificates

Examples include:

- RSA private keys
- EC private keys
- OpenSSH private keys
- PKCS#12 / PFX passwords
- Java Keystore passwords

---

# Sensitive Data Protection in Pro

PasteGuard Pro includes broader sensitive-data protection.

Examples include:

## Payment Information

- Payment card numbers
- Credit card numbers
- Debit card numbers
- CVV
- CVC
- Card expiry

## Banking Information

- IBAN
- Bank account numbers

## Identity Information

- Emirates ID
- Passport numbers

## Optional Personal Data Protection

- Email addresses
- Phone numbers
- Dates of birth

Optional personal-data detectors can be enabled where broader PII protection is appropriate.

---

# Pro Use Cases

PasteGuard Pro can be useful for:

- Professional developers
- DevOps engineers
- Cloud engineers
- Security engineers
- Consultants
- Production-support teams
- Platform engineers
- Technical leads
- Users working across multiple SaaS and cloud platforms
- Users handling payment or sensitive identity information

---

# PasteGuard Organization

## Managed Clipboard Security

**PasteGuard Organization** is designed for companies, enterprises, teams, and managed Windows environments.

It includes the broader detector capabilities available with PasteGuard Pro plus centralized policy and enforcement capabilities.

PasteGuard Organization is not a time-limited trial.

---

# Organization Capabilities

Depending on administrator configuration, PasteGuard Organization can include:

- Organization-managed detector configuration
- Centrally controlled protection settings
- Managed Trusted App policies
- Managed Blocked App policies
- Enforced detector settings
- Pause restrictions
- Organization policy identification
- Organization policy versioning
- Prevention of changes to organization-controlled settings

---

# Managed Detector Configuration

Administrators can control which detector categories should be active on managed devices.

Conceptually:

```text id="808e5w"
Organization Policy
       ↓
Detector Configuration
       ↓
Managed Device
       ↓
PasteGuard Enforcement
```

This helps organizations maintain consistent protection across managed Windows endpoints.

---

# Managed Trusted Apps

Administrators may define applications that are trusted across the organization.

Example:

```text id="rcibn6"
Organization Policy
       ↓
Trusted Application
       ↓
Managed Device
       ↓
Original Content Allowed
```

Trusted applications should only be used for approved business workflows.

---

# Managed Blocked Apps

Organizations may define applications where sensitive paste operations should not be allowed.

Conceptually:

```text id="fywzwt"
Sensitive Content
      ↓
Blocked App
      ↓
Organization Policy
      ↓
Paste Prevented
```

The exact behavior depends on organization policy and protection configuration.

---

# Enforced Settings

Organization-controlled settings may be locked so local users cannot modify them.

Examples may include:

- detector selection
- protection behavior
- Trusted Apps
- Blocked Apps
- pause controls
- centrally managed configuration

This can help prevent local changes from weakening organization-defined clipboard security.

---

# Pause Restrictions

PasteGuard Organization may restrict whether users can pause protection.

This is useful where continuous protection is required.

Instead of globally pausing protection, approved workflows can use centrally managed Trusted Apps where appropriate.

---

# Organization Policy Versioning

Organization policies can include identification and version information.

This helps administrators understand which configuration is active on managed devices.

Conceptually:

```text id="fwv2be"
Policy
  ↓
Version
  ↓
Managed Device
  ↓
PasteGuard
```

---

# Local Processing Across Editions

PasteGuard is designed around local processing.

Across Free, Pro, and Organization editions, core secret detection and sanitization occur locally on the Windows device.

Clipboard secrets do not need to be uploaded to:

- external AI services
- remote secret scanners
- cloud detection APIs

Core flow:

```text id="wczvuc"
Clipboard
   ↓
Local Detection
   ↓
Policy Evaluation
   ↓
Sanitize / Block / Allow
   ↓
Destination
```

> **No secret leaves your computer.**

Microsoft Store licensing, purchases, entitlement verification, and application updates may communicate with Microsoft services.

Clipboard secrets are not sent to Microsoft as part of PasteGuard's secret-detection functionality.

---

# Which Edition Should I Use?

## Choose PasteGuard Free if:

- You want permanent basic protection.
- You mainly need common secret detectors.
- You are evaluating PasteGuard.
- You are an individual user with basic clipboard-security needs.
- You do not need the broader detector catalog.

---

## Choose PasteGuard Pro if:

- You regularly work with multiple cloud providers.
- You handle many API keys and tokens.
- You work with DevOps and infrastructure credentials.
- You need broader database or SaaS detection.
- You need payment or sensitive-data detection.
- You want the broader 100+ detector catalog.

---

## Choose PasteGuard Organization if:

- You need centralized policy.
- You manage multiple Windows devices.
- You need consistent detector configuration.
- You need organization-managed Trusted Apps.
- You need blocked application policies.
- You need pause restrictions.
- You need to prevent local users from changing managed security settings.

---

# Trial Information

PasteGuard does **not** use a time-limited trial model.

## PasteGuard Free

- Permanent free edition
- Does not expire
- Core protection remains available

## PasteGuard Pro

- Optional paid upgrade
- Not a trial

## PasteGuard Organization

- Optional paid edition
- Not a trial

No PasteGuard feature is temporarily enabled solely because of a trial period.

---

# Purchases

Pro and Organization functionality may require a valid entitlement.

Current pricing, billing options, and availability are displayed by Microsoft Store before purchase and may vary by market.

Get PasteGuard:

https://apps.microsoft.com/detail/9nl0497qc6zk

---

# Upgrade Path

Users can start with PasteGuard Free and upgrade when broader protection is required.

Conceptually:

```text id="9jiwlh"
PasteGuard Free
      ↓
Need More Detectors
      ↓
PasteGuard Pro
      ↓
Need Central Management
      ↓
PasteGuard Organization
```

---

# Detector Availability

Detector availability can depend on:

- PasteGuard edition
- active entitlement
- user configuration
- organization-managed policy
- PasteGuard version

For the full detector catalog:

**[Detector Coverage](detectors.md)**

---

# Protected Apps

Protected Apps are supported across the PasteGuard workflow.

They allow users to define destinations where clipboard protection should be applied.

See:

**[Protected Apps](protected-apps.md)**

---

# Trusted Apps

Trusted Apps allow approved applications to receive original clipboard content when permitted by policy.

See:

**[Trusted Apps](trusted-apps.md)**

---

# Organization Management

For more information about centrally managed policies:

**[PasteGuard Organization](organization.md)**

---

# Related Documentation

- **[Getting Started](getting-started.md)**
- **[Detector Coverage](detectors.md)**
- **[Protected Apps](protected-apps.md)**
- **[Trusted Apps](trusted-apps.md)**
- **[Organization](organization.md)**
- **[FAQ](faq.md)**
- **[Privacy](../PRIVACY.md)**
- **[Security](../SECURITY.md)**

---

# Get PasteGuard

PasteGuard is available for Windows through Microsoft Store.

https://apps.microsoft.com/detail/9nl0497qc6zk

Product ID:

```text id="y2rmz0"
9NL0497QC6ZK
```

---

# PasteGuard

## Stop Secrets Before They Leak.

**Free for essential protection**

**Pro for 100+ detector coverage**

**Organization for managed security policies**

**Local-First Protection**

> **No secret leaves your computer.**