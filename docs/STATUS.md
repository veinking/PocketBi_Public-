# PocketBI Ecosystem — Public Status

**Status date:** September 3, 2026

This page is a public-facing snapshot of product availability and maturity. It intentionally avoids private release-candidate details, internal defect ledgers, security-sensitive implementation notes, deployment credentials, private build identifiers, and unreleased source information.

Status labels are descriptive rather than contractual. Individual features can move between preview, beta, and general availability as the products evolve.

## Current product status

| Product | Status | Current public role |
| --- | --- | --- |
| **PocketBI Web / Workspace** | **Live** | Main browser workspace for importing, cleaning, transforming, joining, visualizing, and exporting CSV/Excel data |
| **PocketBI for iPhone** | **Active product track** | Native mobile companion for iPhone-first data workflows; maintained separately from this documentation repo |
| **PocketClean** | **Live** | Deterministic cleanup and reusable workflows for recurring messy files |
| **PocketViz** | **Beta** | Reusable visualization/report workflows built around cleaned datasets |
| **PowerSnap** | **Live** | Fast file diagnosis and data-quality triage |
| **PocketBI Reconcile** | **Live** | Compare old/new exports and surface changed, added, missing, duplicate, or mismatched records |
| **bIDE Web** | **Live** | Browser IDE for Python, R, JavaScript, SQL, notebooks, and custom data work |
| **bIDE for iPhone** | **Pre-release validation** | Native mobile coding/data-analysis product track under active validation before broader release |
| **PocketBI Business** | **Available and evolving** | Organization workspaces, repeatable processing, scoped integrations, and run history |
| **PocketBI ID / Account** | **Live** | Shared user identity/account layer for supported PocketBI services |

## What “Live” means here

“Live” means there is a customer-facing production surface available today. It does **not** mean that every planned feature is complete or that the product will never have bugs.

PocketBI is under active development. Public status is intentionally conservative: a capability should not be described as generally available merely because it exists on a development branch or in an internal test build.

## Current development themes

The ecosystem is currently focused on improving:

- reliability and data-integrity verification
- repeatable workflows instead of one-off file operations
- file/workspace lifecycle management
- semantic type and value management
- clearer recovery from failed or interrupted operations
- stronger continuity between PocketBI, PocketClean, PocketViz, Reconcile, PowerSnap, and bIDE
- Business/Sandbox/production clarity for organization workflows
- web/native capability consistency where appropriate
- bIDE runtime quality across SQL, Python, R, and JavaScript
- mobile release readiness for native applications

These are directional themes, not promises of specific release dates.

## Public release philosophy

PocketBI uses a simple standard for public status:

1. A feature existing in source code is not enough.
2. A passing automated test is not enough by itself.
3. A preview deployment is not the same thing as production availability.
4. User-facing claims should reflect what a real user can actually access.
5. Data-integrity issues are treated more seriously than cosmetic issues.

## Mobile status notes

### PocketBI for iPhone

PocketBI has a native iPhone application track. Public-facing documentation focuses on what users can do with the app and avoids exposing signing, distribution, review-account, or internal release-gate information.

### bIDE for iPhone

bIDE's native iPhone application is still in pre-release validation. The release track includes mobile coding and data-analysis capabilities, but this repository will not present unreleased functionality as generally available until the product is ready for broader distribution.

## Why some details are omitted

This status page deliberately does not include:

- exact internal branch names or commit SHAs
- private CI/run identifiers
- internal TestFlight build numbers
- unresolved exploit details
- private API contracts
- customer-specific incidents
- private backend architecture
- internal vendor/account configuration

Those details do not help a normal user understand the ecosystem and can create unnecessary security or operational risk when published.

## Where to check next

- Product home: https://pocketbi.app
- User guide: [`USER_GUIDE.md`](USER_GUIDE.md)
- Public roadmap: [`../ROADMAP.md`](../ROADMAP.md)
- Support: [`../SUPPORT.md`](../SUPPORT.md)
