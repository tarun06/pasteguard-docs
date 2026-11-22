# Contributing to PasteGuard Documentation

Thank you for your interest in improving PasteGuard.

This repository, `pasteguard-docs`, contains public documentation and product resources for PasteGuard.

The production PasteGuard source code is maintained privately and is not part of this repository.

---

# What You Can Contribute

Contributions are welcome for:

- Documentation corrections
- Documentation improvements
- Feature suggestions
- New detector requests
- False-positive reports
- False-negative reports
- Protected App feedback
- Trusted App feedback
- Organization-policy feedback
- UX suggestions
- Product feedback
- Screenshot or documentation corrections
- Typographical fixes

---

# What This Repository Does Not Accept

Do not submit:

- PasteGuard application source code
- Decompiled PasteGuard code
- Proprietary detector implementation
- Reverse-engineered security logic
- Internal organization-policy logic
- Signing certificates
- Real credentials
- Production secrets
- Customer information
- Personal sensitive information
- Unauthorized third-party copyrighted material

---

# Before You Open an Issue

Search existing issues first.

Your question or request may already have been reported.

When opening a new issue, provide enough information to understand the request without including sensitive data.

---

# Bug Reports

For a normal non-security bug, include:

- PasteGuard version
- Windows version
- PasteGuard edition
- Feature involved
- Steps to reproduce
- Expected behavior
- Actual behavior
- Synthetic test data where relevant
- Sanitized screenshots if useful

---

# Example Bug Report

```text id="zy4bcw"
PasteGuard Version:
1.x.x

Windows Version:
Windows 11

Edition:
Pro

Feature:
Protected Apps

Expected:
The synthetic OpenAI key should be sanitized.

Actual:
The original synthetic value was pasted.

Synthetic Test Value:
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

Never use real credentials.

---

# Detector Requests

Detector requests are especially welcome.

If you need support for a new provider or credential format, include:

- Provider name
- Product name
- Credential type
- Public documentation link
- Synthetic example
- Expected PasteGuard placeholder
- Why the detector is useful

---

# Example Detector Request

```text id="bznfyw"
Provider:
ExampleCloud

Product:
ExampleCloud Platform

Credential Type:
API Token

Documentation:
https://example.com/docs/authentication

Synthetic Example:
example_test_abcdefghijklmnopqrstuvwxyz

Expected Replacement:
<EXAMPLECLOUD_TOKEN>

Use Case:
Used by developers for deployment automation.
```

---

# Never Submit a Real Secret

Do not include real:

- Passwords
- API keys
- Access tokens
- Refresh tokens
- Session tokens
- Private keys
- Certificate passwords
- Database credentials
- Connection strings
- Cloud credentials
- Payment information
- Banking information
- Identity information
- Customer data

Use synthetic examples only.

---

# False Positives

A false positive occurs when PasteGuard identifies safe content as sensitive.

Please include:

- Detector name
- PasteGuard version
- Synthetic input
- Expected behavior
- Actual behavior

Example:

```text id="f6wtu7"
Detector:
Generic API Key

Synthetic Input:
api_key=not-a-real-secret-for-testing

Expected:
No detection

Actual:
Detected as Generic API Key
```

---

# False Negatives

A false negative occurs when a supported synthetic credential is not detected.

Please include:

- Provider
- Detector name
- Public provider documentation
- Synthetic value
- Expected replacement
- Actual behavior

Do not provide a real credential.

---

# Protected App Feedback

For Protected App issues, include:

- Application name
- Application/process name if known
- PasteGuard version
- PasteGuard edition
- Protection mode
- Expected behavior
- Actual behavior
- Synthetic test input

See:

**[Protected Apps](docs/protected-apps.md)**

---

# Trusted App Feedback

For Trusted App issues, include:

- Application name
- Application/process name if known
- Whether the device is organization-managed
- Expected behavior
- Actual behavior
- PasteGuard version
- Synthetic test input

See:

**[Trusted Apps](docs/trusted-apps.md)**

---

# Organization Feedback

For PasteGuard Organization feedback, include:

- PasteGuard version
- Policy version
- Managed feature
- Expected behavior
- Actual behavior
- Application involved if relevant
- Synthetic test input

Do not include confidential organization configuration unless explicitly requested through a private support channel.

See:

**[PasteGuard Organization](docs/organization.md)**

---

# Security Vulnerabilities

Do not report security vulnerabilities through a normal public GitHub Issue if the report contains sensitive details or describes a practical bypass.

Examples include:

- Protected App bypass
- Trusted App bypass
- Blocked App bypass
- Organization-policy bypass
- Raw secret exposure
- Unexpected remote transmission of clipboard content
- Sensitive values written to logs
- Raw secrets stored in activity history

Report security issues privately:

**hello@mindatwork.co.in**

See:

**[Security Policy](SECURITY.md)**

---

# Documentation Contributions

Documentation pull requests are welcome.

Useful contributions include:

- fixing spelling or grammar
- improving clarity
- correcting outdated documentation
- improving examples
- improving navigation
- adding missing public documentation
- fixing broken links

---

# Style Guidelines

Keep documentation:

- Clear
- Technical
- Concise
- Professional
- Easy to scan
- Security-conscious

Prefer short paragraphs and practical examples.

---

# Product Naming

Use the product name exactly as:

```text id="0jjmjc"
PasteGuard
```

Use edition names as:

```text id="5wxuij"
PasteGuard Free
PasteGuard Pro
PasteGuard Organization
```

Do not rename the product as:

```text id="5h9xcv"
Paste Guard
Paste-Guard
Pasteguard
PasteGaurd
```

unless referring to an external typo or legacy text.

---

# Security Terminology

Prefer consistent terminology:

```text id="6ikhrf"
Protected Apps
Trusted Apps
Blocked Apps
Secret Detection
Sensitive Data
Local-First
Sanitize
Block
Allow
Organization Policy
```

---

# Examples

Use synthetic values only.

Good:

```text id="f6syi4"
OPENAI_API_KEY=sk-proj-abcdefghijklmnopqrstuvwxyz123456
```

Bad:

```text id="4cpnsp"
A real production OpenAI API key
```

---

# Markdown

Use standard GitHub Markdown.

Recommended structure:

```text id="50faz7"
# Page Title

Short introduction.

---

# Main Section

Content.

## Subsection

Content.
```

Avoid unnecessary complex HTML unless it materially improves presentation.

---

# Links

Use relative links for files inside this repository.

Good:

```markdown id="46pwth"
[Detector Coverage](docs/detectors.md)
```

Prefer relative links over hard-coded GitHub repository URLs so links continue working across forks or repository moves.

---

# Screenshots

Screenshots should:

- show the real PasteGuard UI
- avoid exposing real credentials
- avoid exposing customer information
- avoid exposing personal information
- be readable
- use current product versions where possible

Place public screenshots under:

```text id="pdvhjk"
assets/
```

---

# Demo Assets

Public demo GIFs and images should use synthetic test values.

Recommended location:

```text id="u04yx6"
assets/
```

Example:

```text id="jdxgq7"
assets/pasteguard-demo.gif
```

---

# Pull Requests

A documentation pull request should ideally:

1. address one clear topic
2. describe what changed
3. explain why the change is useful
4. avoid unrelated changes
5. contain no secrets or sensitive information
6. preserve consistent product terminology

---

# Pull Request Example

```text id="ce33xy"
Title:
docs: clarify Trusted Apps behavior

Description:
- Clarifies difference between Protected Apps and Trusted Apps
- Adds a synthetic example
- Fixes broken documentation links
```

---

# Commit Message Suggestions

Documentation changes can use simple commit messages such as:

```text id="10c51b"
docs: update detector coverage

docs: improve getting started guide

docs: clarify trusted apps behavior

docs: fix broken links

docs: update FAQ
```

---

# Detector Contribution Requests

This repository accepts detector requests and public documentation changes.

It does not accept implementation pull requests for the proprietary PasteGuard detection engine.

If a detector is approved, implementation is handled privately in the PasteGuard source repository.

---

# Privacy

Do not submit personal or confidential information.

Examples include:

- real names where unnecessary
- personal phone numbers
- personal email addresses
- identity documents
- passport numbers
- Emirates IDs
- bank details
- customer records

See:

**[Privacy](PRIVACY.md)**

---

# Code of Conduct

Be respectful and constructive.

Do not:

- harass other contributors
- publish someone's private information
- intentionally submit harmful content
- post credentials
- post customer data
- use issues for spam or unrelated promotion

Technical disagreement is welcome when it remains respectful and focused on improving PasteGuard.

---

# Contributor Rights

Only submit content that:

- you created
- you have permission to contribute
- can legally be shared publicly

Do not submit confidential employer or customer material.

---

# Review

Mind At Work may:

- accept a contribution
- request changes
- edit documentation for consistency
- decline a contribution
- close duplicate or unsupported requests

Submission does not guarantee inclusion in PasteGuard.

---

# Contact

For general product questions:

**hello@mindatwork.co.in**

Website:

https://mindatwork.co.in

For security vulnerabilities, use the same email but clearly identify the message as a security report.

---

# Related Documentation

- **[Getting Started](docs/getting-started.md)**
- **[Detector Coverage](docs/detectors.md)**
- **[Protected Apps](docs/protected-apps.md)**
- **[Trusted Apps](docs/trusted-apps.md)**
- **[Free vs Pro vs Organization](docs/free-vs-pro.md)**
- **[PasteGuard Organization](docs/organization.md)**
- **[FAQ](docs/faq.md)**
- **[Privacy](PRIVACY.md)**
- **[Security](SECURITY.md)**

---

# Thank You

Thank you for helping improve PasteGuard documentation, detector coverage, and product quality.

## PasteGuard

**Stop Secrets Before They Leak.**

> **No secret leaves your computer.**