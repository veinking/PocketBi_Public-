# Security Policy

PocketBI takes security and data integrity seriously.

## Reporting a vulnerability

Please **do not open a public GitHub issue** for a suspected vulnerability, exposed credential, authorization problem, account-takeover path, data-isolation problem, or other security-sensitive defect.

Instead, contact:

**support@pocketbi.app**

Use a subject such as:

`Security report — <product name>`

Include only the information needed to understand and reproduce the issue safely.

Helpful details include:

- affected PocketBI product
- affected public URL or user-visible feature
- high-level description of the problem
- steps to reproduce using test/non-sensitive data
- expected behavior
- observed behavior
- browser/device/app version where relevant
- screenshots with private information removed

## Do not send

Do not send or publish:

- real passwords
- private API keys or tokens
- authentication cookies
- full payment-card information
- signing certificates/private keys
- customer datasets
- unnecessary personal information

If you discover an exposed secret, report where it was exposed without copying the secret into a public issue.

## Responsible testing

Please avoid testing that:

- accesses or modifies another user's data
- disrupts production availability
- creates excessive automated traffic
- attempts destructive operations against production systems
- uses social engineering
- sends spam
- targets third-party providers outside PocketBI's control

Use your own account and non-sensitive test data whenever possible.

## Scope of this repository

`PocketBi_Public-` is a public documentation/product-information repository. It is **not** intended to contain production credentials or proprietary backend source code.

If sensitive internal information is accidentally published here, report it privately using the address above rather than amplifying it through a public issue.

## Data-integrity reports

Silent data mutation, cross-user data exposure, incorrect joins that mix records, and exports that materially change source values can have security-like consequences even when they are not traditional vulnerabilities. Report serious data-integrity defects privately if they could expose or corrupt confidential information.

## Response expectations

Security reports are triaged based on impact, reproducibility, and risk. Public disclosure should wait until a fix or safe mitigation is available.
