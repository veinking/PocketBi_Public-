# PocketBI Ecosystem

PocketBI is a product family rather than one giant application. Each tool solves a focused part of the data workflow while sharing a common product identity, support experience, and increasingly connected user journey.

This document describes the **public product architecture**. It intentionally does not document private network topology, databases, privileged services, deployment credentials, internal schemas, or other security-sensitive implementation details.

## The public mental model

Think of PocketBI as a set of exits from the same data journey:

```text
                     ┌──────────────┐
                     │   PowerSnap  │
                     │   diagnose   │
                     └──────┬───────┘
                            ↓
┌──────────┐        ┌──────────────┐        ┌─────────────┐
│  source  │ ─────→ │ PocketClean  │ ─────→ │  Reconcile  │
│   data   │        │ clean/repeat │        │compare/check│
└──────────┘        └──────┬───────┘        └──────┬──────┘
                            ↓                       │
                     ┌──────────────┐              │
                     │   PocketBI   │ ←────────────┘
                     │ transform /  │
                     │ analyze      │
                     └──────┬───────┘
                            ↓
                     ┌──────────────┐
                     │  PocketViz   │
                     │ report       │
                     └──────┬───────┘
                            ↓
                     ┌──────────────┐
                     │     bIDE     │
                     │ custom code  │
                     └──────────────┘
```

A user does not have to follow this sequence exactly. The right path depends on the job.

## PocketBI

PocketBI is the flagship general-purpose workspace.

Use it to:

- import CSV and Excel data
- inspect structure and quality
- clean common issues
- transform columns and values
- calculate new fields
- filter and aggregate
- join datasets
- build charts
- export results
- move toward a repeatable workflow when the task grows beyond one file

PocketBI is usually the best starting point for a first-time user.

## PocketClean

PocketClean specializes in repeatable deterministic cleanup.

It is most useful when the same kind of messy file keeps returning and the user needs consistent rules rather than a one-time manual cleanup.

Examples include:

- recurring vendor exports
- monthly finance files
- CRM extracts
- operations reports
- repeated date/number formatting cleanup
- whitespace and categorical normalization

The design goal is **repeatability without silently inventing data**.

## PocketViz

PocketViz specializes in visualization and reusable reporting.

The goal is not to produce a chart simply because a column exists. Useful reporting should prioritize meaningful categories, measures, dates, and business dimensions over identifiers or near-unique labels.

## PowerSnap

PowerSnap is the fast diagnostic entry point.

Use it when the first question is:

> “What is wrong with this file?”

It helps identify structural and cleanliness problems before a user commits to a deeper workflow.

## PocketBI Reconcile

Reconcile is for two-file comparison.

Typical jobs include:

- yesterday vs today
- prior month vs current month
- source system vs exported system
- expected records vs actual records
- before-cleaning vs after-cleaning validation

A strong reconcile workflow depends on a stable match key and careful handling of duplicates, missing values, and type differences.

## bIDE

bIDE is the code-first side of the ecosystem.

It exists for cases where visual tools are no longer the best abstraction.

Public runtime/product direction includes:

- SQL
- Python
- R
- JavaScript
- notebook-style workflows
- file/data analysis

bIDE is a PocketBI product but remains a focused IDE rather than being collapsed into the main PocketBI workspace.

## PocketBI Business

PocketBI Business takes the same ideas—clean, transform, verify, repeat—and applies them to organization workflows.

Public concepts include:

- organizations
- teams and roles
- workspaces
- reusable processing configurations
- scoped integration access
- run history
- verification/lineage information where supported
- a distinction between testing and production-oriented execution

The public docs describe these concepts at the level needed to use the product. Internal control-plane implementation, privileged routes, credential formats, and backend data models are intentionally private.

## PocketBI ID

PocketBI ID is the shared identity/account concept for supported PocketBI services.

Its role is to reduce the feeling that every product is an unrelated website while still allowing products to keep appropriate technical boundaries.

## Native apps

### PocketBI for iPhone

The native PocketBI application brings the core data-work philosophy to iPhone. Mobile and web do not have to be pixel-for-pixel identical, but the major concepts should remain understandable across both surfaces.

### bIDE for iPhone

The native bIDE application extends the code/data-analysis workflow to iPhone. It is maintained on its own release track and is not considered generally available merely because a capability exists in an internal build.

## Why the tools remain separate

A monolithic application is not automatically a better ecosystem.

Keeping products focused can provide:

- simpler user interfaces
- clearer purpose
- independent deployment/release cycles
- reduced blast radius when one product has a problem
- easier experimentation without destabilizing every workflow

The long-term goal is **shared continuity without shared fragility**.

## What should feel shared

Even when the applications remain technically independent, users should recognize the same principles:

- consistent PocketBI naming and navigation
- stable support/privacy information
- understandable data lifecycle
- clear Free/paid/Business boundaries
- predictable file handling
- useful error recovery
- obvious next steps between products
- trustworthy exports

## What should remain product-specific

Some capabilities should stay specialized:

- advanced coding belongs in bIDE
- recurring cleanup belongs in PocketClean
- dedicated comparisons belong in Reconcile
- visualization templates belong in PocketViz
- business administration belongs in PocketBI Business

That specialization is intentional.

## Data movement philosophy

The ecosystem should not make users re-upload and recreate context unnecessarily. Where safe and appropriate, results should be able to move forward into the next tool or be downloaded in standard formats.

At the same time, product boundaries should not be bypassed in ways that weaken privacy, access control, or reliability.

## Public vs private architecture

Public documentation can explain:

- what products do
- how users move between them
- public URLs
- supported file types and workflows
- user-visible security/privacy principles
- product maturity/status

Public documentation should **not** expose:

- private service credentials
- production environment values
- internal database schemas
- admin-only implementation details
- hidden operational endpoints
- customer identifiers or datasets
- exploit-enabling infrastructure detail
- internal release credentials or signing information

That boundary is part of the product's security posture, not a lack of transparency.
