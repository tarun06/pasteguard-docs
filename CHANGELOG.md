# PasteGuard Changelog

All notable public-facing changes to PasteGuard can be documented here.

This changelog focuses on product capabilities, detector coverage, security improvements, and user-visible behavior.

---

# Latest Release

## Added

- Expanded detector coverage to **100+ secret and sensitive-data detectors**
- Payment card number detection
- Card expiry detection
- CVV / CVC detection
- IBAN detection
- Bank account number detection
- Emirates ID detection
- Passport number detection
- Optional email-address detection
- Optional phone-number detection
- Optional date-of-birth detection
- Additional AI credential coverage
- Additional cloud credential coverage
- Additional DevOps credential coverage
- Additional SaaS credential coverage
- Additional monitoring credential coverage
- Additional messaging credential coverage
- Additional authentication coverage

---

## Improved

- Improved provider-specific secret detection
- Improved JSON-formatted credential detection
- Improved quoted configuration-key handling
- Improved secret prioritization
- Improved overlap handling
- Improved sanitization coverage
- Reduced risk of partial-secret exposure
- Reduced false positives
- Improved false-negative handling for supported formats
- Improved contextual credential detection

---

# AI Detector Improvements

Improved or expanded detection for:

- OpenAI
- Anthropic
- Hugging Face
- Groq
- Mistral
- Cohere
- Perplexity
- Replicate

---

# Cloud Detector Improvements

Improved or expanded detection for:

- AWS credentials
- AWS Secret Access Keys
- AWS Session Tokens
- Azure secrets
- Azure Client Secrets
- Azure DevOps PATs
- Azure SAS tokens
- Azure Storage connection strings
- Azure Service Bus credentials
- Azure Event Hubs credentials
- Google Cloud API keys
- Google OAuth client secrets
- Google Service Accounts
- Cloudflare API credentials
- DigitalOcean tokens
- Firebase credentials
- Supabase secrets

---

# Source Control Detector Improvements

Improved or expanded detection for:

- GitHub tokens
- GitHub Fine-Grained PATs
- GitLab tokens
- Bitbucket credentials

---

# Database Detector Improvements

Improved or expanded detection for:

- MongoDB credentials
- PostgreSQL credentials
- MySQL credentials
- Redis credentials
- Snowflake credentials
- Database URLs
- Generic connection strings
- SQL Server credentials
- Oracle credentials
- Elasticsearch credentials

---

# DevOps & Infrastructure Improvements

Improved or expanded detection for:

- Consul ACL tokens
- Nomad ACL tokens
- Docker Hub tokens
- Kubernetes secrets
- HashiCorp Vault tokens
- Terraform Cloud tokens
- Pulumi access tokens
- CircleCI tokens
- Jenkins API tokens
- JFrog tokens
- SonarQube tokens

---

# Package Registry Improvements

Improved or expanded detection for:

- GitHub Packages tokens
- npm access tokens
- PyPI API tokens
- NuGet API keys

---

# Messaging Improvements

Improved or expanded detection for:

- Slack tokens
- Discord tokens
- Telegram bot tokens
- AMQP credentials
- RabbitMQ credentials
- Kafka credentials

---

# Monitoring & Observability Improvements

Improved or expanded detection for:

- Datadog API keys
- New Relic API keys
- Sentry authentication tokens
- Grafana tokens

---

# SaaS Improvements

Improved or expanded detection for:

- Linear
- Asana
- Dropbox
- Square
- Razorpay
- Algolia
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

---

# Authentication Improvements

Improved or expanded detection for:

- Basic Authentication credentials
- Bearer tokens
- JSON Web Tokens
- OAuth client secrets
- Password assignments
- Credentials embedded inside URLs

---

# Identity Improvements

Improved or expanded detection for:

- Okta API tokens
- Auth0 client secrets

---

# Email Service Improvements

Improved or expanded detection for:

- Mailgun API keys
- Postmark server tokens
- Resend API keys

---

# Key & Certificate Improvements

Improved or expanded handling for:

- Private keys
- RSA private keys
- EC private keys
- OpenSSH private keys
- PKCS#12 / PFX passwords
- Java Keystore passwords

---

# Sensitive Data Improvements

Added or expanded support for:

## Payment

- Payment card numbers
- Credit card numbers
- Debit card numbers
- Card expiry
- CVV
- CVC

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

# Sanitization Improvements

PasteGuard's sanitization logic has been improved to better handle situations where multiple detectors match overlapping portions of the same sensitive value.

The goal is to ensure that:

```text id="61b3k5"
Sensitive Value
      ↓
Detection
      ↓
Complete Protected Region
      ↓
Safe Replacement
```

rather than exposing a smaller unmatched portion of the original value.

---

# Detector Priority Improvements

Provider-specific detectors are designed to take priority over broader generic detectors where appropriate.

This improves replacement quality.

Example:

```text id="ffmfvx"
Provider-Specific Credential
        ↓
Specific Detector
        ↓
Provider-Specific Placeholder
```

instead of:

```text id="5gghbj"
Provider-Specific Credential
        ↓
Generic Detector
        ↓
<SECRET>
```

---

# Configuration Detection Improvements

PasteGuard has improved support for credentials commonly copied from:

- `appsettings.json`
- `.env` files
- JSON payloads
- configuration files
- CI/CD configuration
- cloud configuration
- connection strings
- environment-variable assignments

---

# Quoted JSON Key Support

Detection has been improved for common configuration styles such as:

```json id="97w4cm"
{
  "API_KEY": "synthetic-secret-value"
}
```

and:

```text id="3045c9"
API_KEY=synthetic-secret-value
```

---

# Azure Improvements

Azure-related detection improvements include better handling of:

- Azure DevOps PATs
- Azure SAS tokens
- Azure Storage connection strings
- Azure Service Bus credentials
- Azure Event Hubs credentials
- Azure Client Secrets

---

# Cloudflare Improvements

Improved detection of Cloudflare credential assignments using common configuration key formats.

---

# Supabase Improvements

Improved support for supported Supabase credential formats, including service and secret credential patterns.

---

# Hugging Face Improvements

Improved recognition of supported Hugging Face access-token formats.

---

# Replicate Improvements

Improved recognition of supported Replicate API-token formats.

---

# CircleCI Improvements

Improved detection in common configuration formats.

---

# Jenkins Improvements

Improved detection in common JSON and configuration-key formats.

---

# Consul Improvements

Improved recognition of Consul ACL tokens.

---

# Nomad Improvements

Improved recognition of Nomad ACL tokens.

---

# Protected Apps

Protected App functionality continues to support destination-aware clipboard protection.

Depending on protection mode and policy, supported actions can include:

- sanitize
- block
- allow

See:

**[Protected Apps](docs/protected-apps.md)**

---

# Trusted Apps

Trusted Apps allow explicitly approved destinations to receive original clipboard content where policy permits.

See:

**[Trusted Apps](docs/trusted-apps.md)**

---

# Organization Improvements

PasteGuard Organization supports organization-managed controls such as:

- centrally managed detector configuration
- Trusted App policies
- Blocked App policies
- enforced security settings
- pause restrictions
- policy identification
- policy versioning

See:

**[PasteGuard Organization](docs/organization.md)**

---

# Privacy

PasteGuard remains designed around local processing.

Core detector processing does not require clipboard secrets to be uploaded to a remote secret-detection or AI service.

See:

**[Privacy](PRIVACY.md)**

---

# Security

Security-related improvements focus on:

- safer sanitization
- better detector prioritization
- overlap handling
- reduced partial exposure
- local processing
- stronger destination-aware protection

See:

**[Security Policy](SECURITY.md)**

---

# Documentation

Public documentation now includes:

- Getting Started
- Detector Coverage
- Protected Apps
- Trusted Apps
- Free vs Pro vs Organization
- Organization
- FAQ
- Privacy
- Security
- Changelog

---

# Microsoft Store

PasteGuard is distributed through Microsoft Store.

https://apps.microsoft.com/detail/9nl0497qc6zk

Product ID:

```text id="xj5oaq"
9NL0497QC6ZK
```

---

# Notes

This public changelog intentionally avoids publishing:

- proprietary detector expressions
- private implementation details
- internal source code
- production credentials
- private organization configuration
- security-sensitive implementation details

---

# PasteGuard

## Stop Secrets Before They Leak.

**100+ Secret & Sensitive-Data Detectors**

**Protected Apps**

**Trusted Apps**

**Local-First Protection**

> **No secret leaves your computer.**