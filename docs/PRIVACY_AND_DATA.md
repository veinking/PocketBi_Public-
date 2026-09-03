# Privacy and Data Handling

PocketBI is built around a practical principle: keep user data as close to the user as the job allows, and be explicit when a feature requires an account, server, or business integration.

This page is a public product overview, not a replacement for the legally controlling product-specific privacy policies.

Official privacy center:

https://pocketbi.app/privacy-center

## Local-first where practical

Core file analysis and transformation workflows are designed to remain on-device or in-browser when the feature can reasonably work that way.

A local-first design can reduce unnecessary transfer of business datasets and make simple workflows faster and easier to understand.

Some capabilities—such as accounts, cloud workspaces, paid entitlements, business integrations, or server-side automation—can require network services. When they do, users should rely on the applicable product privacy policy and user-facing disclosures for current details.

## Separate product boundaries

PocketBI products can share a common identity and support experience without requiring every category of data to be combined into one backend.

Product-specific data practices should remain product-specific where the workflows differ.

## Public support hygiene

When asking for help, do not publicly share:

- passwords
- one-time codes
- API keys
- access tokens
- session cookies
- recovery links
- full payment-card information
- private signing material
- confidential production datasets
- personal information that is not necessary to reproduce a problem

When a dataset is needed to reproduce a bug, prefer a **sanitized or synthetic sample** that preserves the structure of the problem without exposing real people, customers, or business secrets.

## Data verification and privacy

Privacy and correctness are related.

A workflow that silently changes identifiers, creates values that were not in the source, or mixes records incorrectly can create both data-quality and privacy problems.

For important work, verify:

- row and column counts
- key identifiers
- null handling
- joins and unmatched records
- exported files

## Business data

Business workflows can involve more sensitive operational data than a casual individual file.

Organizations should:

- use scoped access where available
- separate testing from production-oriented workflows
- avoid embedding credentials in files or scripts
- review outputs before downstream use
- keep confidential datasets out of public issue trackers

## What this public repository does not expose

This repository intentionally avoids publishing:

- production database schemas
- private infrastructure maps
- internal service credentials
- secret environment configuration
- privileged administrative APIs
- customer data
- private operational logs
- exploit-enabling security details

That information is not required to understand or use the products and belongs in private operational systems.

## Questions

For current product-specific privacy information, use:

https://pocketbi.app/privacy-center

For support, see [`../SUPPORT.md`](../SUPPORT.md).

For suspected security vulnerabilities, see [`../SECURITY.md`](../SECURITY.md).
