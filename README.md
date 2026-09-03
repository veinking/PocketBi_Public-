# PocketBI

**Practical software for modern data work.**

PocketBI is a connected family of focused tools for cleaning, transforming, analyzing, visualizing, comparing, and coding with data. The goal is simple: start with a file or business workflow, use the smallest tool that solves the job, and move forward without turning basic data work into an infrastructure project.

This repository is the **public documentation and product-information home for the PocketBI ecosystem**. It intentionally does **not** contain the proprietary production source code, private infrastructure configuration, credentials, internal security details, customer data, or release-only implementation notes for the commercial products.

> Public product information belongs here. Private implementation details stay private.

## Start here

- **PocketBI:** https://pocketbi.app
- **PocketBI Workspace:** https://pocketbi.app/Datasnap
- **PocketBI How To:** https://pocketbi.app/how-to
- **bIDE:** https://bideide.com
- **Support:** https://pocketbi.app/support
- **Privacy Center:** https://pocketbi.app/privacy-center

## The ecosystem

| Product | Best for | Platform | Public status |
| --- | --- | --- | --- |
| **PocketBI** | Importing, cleaning, transforming, joining, charting, and exporting everyday business data | Web + iPhone | Live / actively maintained |
| **PocketClean** | Repeatable deterministic cleanup for recurring messy files | Web | Live |
| **PocketViz** | Reusable charts, dashboards, and visual reporting | Web | Beta |
| **PowerSnap** | Fast diagnosis of structural and data-quality problems | Web | Live |
| **PocketBI Reconcile** | Comparing two exports and finding changed, added, missing, or mismatched records | Web | Live |
| **bIDE** | Python, R, JavaScript, SQL, notebooks, and custom data analysis | Web | Live |
| **PocketBI Business** | Organization workflows, repeatable processing, scoped access, and run history | Web | Available and evolving |
| **PocketBI for iPhone** | Native mobile data work when an iPhone-first workflow is preferable | iOS | Active product track |
| **bIDE for iPhone** | Native coding/data-analysis workflow on iPhone | iOS | Pre-release validation |

See [`docs/STATUS.md`](docs/STATUS.md) for the current public-facing status snapshot.

## Which tool should I use?

**Start in PocketBI Workspace** if you have a CSV or Excel file and are not sure where to begin.

Use **PowerSnap** when you first need a quick diagnosis of what is wrong with a file.

Use **PocketClean** when the same dirty schema or cleanup job returns repeatedly and you want a reusable, deterministic workflow.

Use **Reconcile** when you have an old and new export and need to know what changed.

Use **PocketViz** when the data is already clean enough and the next job is a chart, dashboard, or reusable report.

Use **bIDE** when point-and-click tools stop being enough and you need code, SQL, notebooks, or custom analysis.

Use **PocketBI Business** when the problem is no longer one file for one person and becomes an organization-level recurring workflow.

## A typical workflow

```text
File or export
     ↓
PowerSnap          diagnose
     ↓
PocketClean        clean / standardize / repeat
     ↓
Reconcile          verify changes when needed
     ↓
PocketBI           transform / join / analyze
     ↓
PocketViz          visualize / report
     ↓
bIDE               custom code when needed
```

Not every job needs every product. The ecosystem is intentionally modular.

## PocketBI Workspace in one minute

A normal first-file workflow is:

1. Import a CSV, XLS, or XLSX file.
2. Verify headers, row count, column count, and representative values.
3. Review missing values, duplicates, formatting, and consistency issues.
4. Preview transformations before applying them.
5. Build a chart or summary from the cleaned working data.
6. Export the result and independently verify the downloaded file.

For the full walkthrough, see [`docs/USER_GUIDE.md`](docs/USER_GUIDE.md).

## Product principles

### Practical first

A useful result should not require a large setup project.

### Local-first where practical

Core file workflows are designed to keep imported data on-device or in-browser when a feature does not genuinely require server processing. Product-specific privacy policies describe the behavior of features that use accounts, cloud services, or business integrations.

### Verify the data, not just the screen

For important transforms, joins, cleanups, comparisons, and exports, check row counts, column counts, headers, nulls, and representative values. A visually correct interface is not proof that a dataset is correct.

### Focused tools

PocketBI products share a coherent identity and workflow philosophy without requiring every product to be one giant application.

### Recoverable workflows

Users should be able to understand what happened, retry when appropriate, and avoid losing work because of a single failure.

## Mobile apps

### PocketBI for iPhone

PocketBI also has a native iPhone product track for mobile-first data work. Its public purpose is the same as the web workspace: make common spreadsheet/data tasks approachable from a phone, including importing data, cleaning and transforming it, reviewing results, and creating useful outputs.

The native application is maintained separately from this documentation repository. Internal build numbers, signing details, App Store release gates, private test accounts, and release-candidate implementation notes are intentionally not published here.

### bIDE for iPhone

bIDE has a native iPhone product track focused on bringing the coding/data-analysis experience to mobile. The iOS release track is currently in pre-release validation. Public documentation will be updated as capabilities become generally available.

Internal TestFlight gates, exact release SHAs, signing configuration, and private regression artifacts are not part of this public repository.

## PocketBI Business

PocketBI Business extends the individual-file workflow to repeatable organization use cases. Public-facing concepts include:

- organizations and team access
- workspaces
- reusable processing profiles/workflows
- scoped credentials for approved integrations
- run history
- verification/lineage information where supported
- separation between testing and production-oriented workflows

This repository explains how to use those concepts without documenting private backend topology, credential formats, database internals, privileged endpoints, or operational secrets.

## Documentation

- [`docs/GETTING_STARTED.md`](docs/GETTING_STARTED.md) — choose a product and finish your first useful workflow
- [`docs/USER_GUIDE.md`](docs/USER_GUIDE.md) — detailed user guide across the ecosystem
- [`docs/ECOSYSTEM.md`](docs/ECOSYSTEM.md) — how the products fit together
- [`docs/STATUS.md`](docs/STATUS.md) — current public-facing product status
- [`docs/PRIVACY_AND_DATA.md`](docs/PRIVACY_AND_DATA.md) — public privacy/data-handling principles
- [`ROADMAP.md`](ROADMAP.md) — public roadmap themes
- [`SUPPORT.md`](SUPPORT.md) — support and bug-reporting guidance
- [`SECURITY.md`](SECURITY.md) — responsible security reporting
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — what public contributions are appropriate here

## What is intentionally not published

For the safety of users and the integrity of the commercial products, this repository does not publish:

- passwords, API keys, tokens, signing certificates, secrets, or environment values
- production database credentials or private schemas
- privileged/internal API routes or administrative bypasses
- customer datasets, logs containing customer data, or private analytics
- internal incident details that would expose an unresolved security weakness
- App Store/TestFlight credentials or review accounts
- exact private release-candidate SHAs and internal gate artifacts
- proprietary source code from private product repositories
- internal infrastructure maps that materially increase attack surface
- vendor account identifiers or private billing configuration

If an implementation detail is not necessary for a customer, evaluator, contributor, or user to understand or use PocketBI, it probably does not belong in this repository.

## Reporting bugs and security issues

Ordinary product bugs and documentation problems can be reported using the guidance in [`SUPPORT.md`](SUPPORT.md).

**Do not post suspected vulnerabilities, credentials, private user data, or exploit details in a public GitHub issue.** Follow [`SECURITY.md`](SECURITY.md) instead.

## License and source availability

This repository is public for product information, documentation, education, support, and transparency. Public visibility does not imply that the PocketBI commercial product source code is open source.

See [`LICENSE.md`](LICENSE.md).

---

**PocketBI** — practical tools for data cleaning, analysis, visualization, comparison, coding, and repeatable business workflows.
