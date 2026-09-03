# PocketBI Public Roadmap

This roadmap describes **public product direction**, not an internal release schedule. It intentionally avoids private milestones, security-sensitive implementation details, exact release-candidate identifiers, and promises of specific dates.

## Near-term themes

### 1. Make repeatable work easier

The ecosystem should help users turn a successful one-off workflow into something they can repeat.

Areas of focus include:

- reusable cleaning workflows
- saved transformations/templates
- clearer workspace/file lifecycle
- less unnecessary re-uploading between products
- better continuity from cleaning to analysis to visualization

### 2. Strengthen data integrity

A correct-looking screen is not enough.

Direction includes:

- stronger row/column/value verification
- clearer change summaries
- safer join behavior
- better export verification
- more obvious handling of unmatched and null records

### 3. Improve semantic data management

Users need more than basic formatting.

Direction includes:

- clearer type management
- category/value standardization
- explicit mappings for equivalent labels
- better handling of identifiers vs numeric measures
- more understandable null/missing-value behavior

### 4. Better failure recovery

When something fails, the user should know what happened and what to do next.

Direction includes:

- useful error messages
- retry paths
- safer recovery after refresh/interruption
- better diagnostic information where appropriate
- fewer dead-end workflows

### 5. Smarter visualization defaults

PocketViz and PocketBI visualization should prioritize meaningful business fields over IDs, blanks, or nearly unique labels.

Direction includes:

- better field selection heuristics
- stronger chart recommendations
- reusable report templates
- cleaner handling of empty categories

### 6. Business repeatability

PocketBI Business is evolving toward clearer organization-level workflows.

Direction includes:

- clearer workspace concepts
- cleaner testing vs production-oriented separation
- repeatable processing configurations
- scoped integration access
- understandable run history and verification

### 7. bIDE runtime quality

bIDE continues to improve as the code-first side of PocketBI.

Direction includes:

- SQL reliability
- Python workflows
- R workflows
- JavaScript workflows
- notebook/data-file continuity
- export integrity

### 8. Native mobile readiness

PocketBI and bIDE both have native iPhone product tracks.

Direction includes:

- reliable mobile file workflows
- sensible web/native continuity
- release readiness
- data-integrity testing on real devices
- mobile-friendly account/entitlement behavior

## Longer-term direction

PocketBI is aiming for a coherent progression:

```text
bring data in
→ understand it
→ clean it
→ standardize it
→ analyze it
→ visualize it
→ compare/verify it
→ save/reuse the workflow
→ automate it when appropriate
```

The system should remain approachable for a single user while scaling into repeatable business workflows when the job demands it.

## What this roadmap is not

This roadmap is not:

- a guarantee of delivery dates
- a complete list of internal work
- a security defect tracker
- a private release plan
- a list of unreleased implementation details

Current public availability is tracked in [`docs/STATUS.md`](docs/STATUS.md).
