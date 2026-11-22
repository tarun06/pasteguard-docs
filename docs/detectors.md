# PasteGuard Detector Coverage

PasteGuard supports **100+ secret and sensitive-data detectors** across AI, cloud, source control, databases, DevOps, package registries, messaging, monitoring, SaaS, authentication, identity, email services, cryptographic keys, and sensitive-data categories.

This document lists the supported detector types without exposing PasteGuard's proprietary detection implementation.

---

# AI

PasteGuard supports detection for:

- OpenAI API Key
- Anthropic API Key
- Hugging Face Token
- Groq API Key
- Mistral API Key
- Cohere API Key
- Perplexity API Key
- Replicate API Token

---

# Cloud

PasteGuard supports detection for:

- AWS Credentials
- AWS Secret Access Key
- AWS Session Token
- Azure Secrets
- Azure Client Secret
- Azure DevOps PAT
- Azure SAS Token
- Azure Storage Connection String
- Azure Service Bus Credential
- Azure Event Hubs Credential
- Google Cloud API Key
- Google OAuth Client Secret
- Google Service Account
- Cloudflare API Token
- DigitalOcean Token
- Firebase Credential
- Supabase Secret

---

# Source Control

PasteGuard supports detection for:

- GitHub Token
- GitHub Fine-Grained PAT
- GitLab Token
- Bitbucket Credential

---

# Database

PasteGuard supports detection for:

- MongoDB Credential
- PostgreSQL Credential
- MySQL Credential
- Redis Credential
- Snowflake Credential
- Database URL
- Generic Connection String
- SQL Server Credential
- Oracle Credential
- Elasticsearch Credential

---

# DevOps & Infrastructure

PasteGuard supports detection for:

- Consul ACL Token
- Nomad ACL Token
- Docker Hub Token
- Kubernetes Secret
- HashiCorp Vault Token
- Terraform Cloud Token
- Pulumi Access Token
- CircleCI Token
- Jenkins API Token
- JFrog Token
- SonarQube Token

---

# Package Registry

PasteGuard supports detection for:

- GitHub Packages Token
- npm Access Token
- PyPI API Token
- NuGet API Key

---

# Messaging

PasteGuard supports detection for:

- Slack Token
- Discord Token
- Telegram Bot Token
- AMQP Credential
- RabbitMQ Credential
- Kafka Credential

---

# Monitoring & Observability

PasteGuard supports detection for:

- Datadog API Key
- New Relic API Key
- Sentry Auth Token
- Grafana Token

---

# SaaS

PasteGuard supports detection for:

- Linear API Key
- Asana Access Token
- Dropbox Access Token
- Square Access Token
- Razorpay Secret
- Algolia API Key
- Stripe Key
- Twilio Auth Token
- SendGrid API Key
- Mailchimp API Key
- Vercel Token
- Netlify Token
- Heroku API Key
- Atlassian API Token
- Jira API Token
- Salesforce Access Token
- Notion Integration Token
- Shopify Access Token
- PayPal Client Secret
- Clerk Secret Key

---

# Authentication

PasteGuard supports detection for:

- Basic Authentication
- Bearer Token
- JSON Web Token (JWT)
- OAuth Client Secret
- Password
- URL Credential

---

# Keys & Certificates

PasteGuard supports detection for:

- PKCS#12 / PFX Password
- Java Keystore Password
- Private Key

Supported private-key formats include:

- RSA private keys
- EC private keys
- OpenSSH private keys
- Other supported private-key formats

---

# Generic Secrets

PasteGuard supports generic fallback detection for:

- Generic API Key
- Generic Secret
- Generic Access Token

These detectors help identify common secret-assignment patterns that may not match a provider-specific detector.

---

# Identity

PasteGuard supports detection for:

- Okta API Token
- Auth0 Client Secret

---

# Email Services

PasteGuard supports detection for:

- Mailgun API Key
- Postmark Server Token
- Resend API Key

---

# Sensitive Data

PasteGuard also supports detection of sensitive personal and financial information.

## Payment Information

Supported types include:

- Payment Card Number
- Credit Card Number
- Debit Card Number
- Card Expiry
- Card Security Code
- CVV
- CVC

---

## Banking Information

Supported types include:

- IBAN
- Bank Account Number

---

## Identity Information

Supported types include:

- Emirates ID
- Passport Number

---

## Optional Personal Data Protection

The following detectors can be enabled when broader personal-data protection is required:

- Email Address
- Phone Number
- Date of Birth

These detectors are useful for workflows that require broader PII protection.

---

# Free Detector Coverage

PasteGuard Free includes the essential detector set currently configured for the Free tier.

The Free detector set includes:

- OpenAI API Key
- AWS Credentials
- Azure Secrets
- GitHub Token
- Connection String
- Basic Authentication
- Bearer Token
- JWT
- Password
- Private Key
- Generic API Key
- Generic Secret

PasteGuard Free is a permanent free edition.

It is not a time-limited trial and does not expire.

---

# Pro Detector Coverage

PasteGuard Pro unlocks the broader detector catalog.

Pro includes provider-specific and advanced coverage across:

- AI platforms
- Cloud providers
- Identity platforms
- Source-control systems
- Databases
- DevOps and infrastructure
- Package registries
- Messaging platforms
- Monitoring and observability
- SaaS platforms
- Email services
- Authentication credentials
- Cryptographic keys and certificates
- Generic secrets
- Payment information
- Banking information
- Identity information
- Sensitive-data protection

PasteGuard Pro is an optional paid upgrade and is not a time-limited trial.

---

# PasteGuard Organization

PasteGuard Organization includes the broader detector capabilities available with Pro together with organization-managed controls.

Depending on administrator configuration, Organization capabilities can include:

- Managed detector configuration
- Trusted App policies
- Blocked App policies
- Enforced protection settings
- Pause restrictions
- Organization policy identification
- Policy versioning
- Prevention of changes to organization-controlled settings

---

# Example Detection

Original content:

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

PasteGuard can sanitize it into:

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

All examples in this repository use synthetic test data.

---

# Detector Design

PasteGuard's detection engine uses a combination of:

- Provider-specific patterns
- Context-aware detection
- Secret-format validation
- Detector priorities
- Validation rules
- Overlap handling
- False-positive reduction
- Local sanitization

Detection is performed locally on the Windows device.

Internal detector expressions, matching rules, validation logic, and proprietary implementation details are not published in this repository.

---

# Detector Selection

PasteGuard allows detector selection based on edition and user or organization configuration.

Detector availability may depend on:

- PasteGuard Free
- PasteGuard Pro
- PasteGuard Organization
- User-selected detector settings
- Organization-managed policies

---

# Request a New Detector

If PasteGuard does not currently support a credential or sensitive-data format you use, open a detector request.

Please include:

- Provider or product name
- Credential type
- Public provider documentation
- Synthetic example format
- Expected safe replacement
- Brief use case

Example:

```text
Provider:
ExampleCloud

Credential Type:
API Token

Synthetic Example:
example_test_abcdefghijklmnopqrstuvwxyz

Expected Replacement:
<EXAMPLECLOUD_TOKEN>
```

## Important

Never submit a real credential.

Do not include:

- Production passwords
- API keys
- Access tokens
- Private keys
- Signing certificates
- Customer credentials
- Payment card information
- Personal sensitive information
- Any other real production secret

---

# False Positives and False Negatives

If PasteGuard incorrectly detects safe content or misses a synthetic test credential, please open an issue.

Include:

- Detector or provider name
- Synthetic example
- Expected behavior
- Actual behavior
- PasteGuard version

Never use a real production credential in a public issue.

---

# Privacy

PasteGuard performs secret and sensitive-data detection locally on the Windows device.

Clipboard secrets do not need to be sent to an external AI service or remote cloud detection service.

For more information, see:

**[Privacy](../PRIVACY.md)**

---

# Security

If you discover a potential security vulnerability, do not disclose sensitive details through a public GitHub issue.

See:

**[Security Policy](../SECURITY.md)**

or contact:

**hello@mindatwork.co.in**

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