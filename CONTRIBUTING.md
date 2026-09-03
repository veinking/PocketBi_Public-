# Contributing to PocketBI Public Documentation

Thanks for helping improve the public PocketBI documentation.

This repository is primarily for:

- product documentation
- user guides
- public product status
- examples using synthetic data
- public roadmap communication
- support information
- public-facing issue reproduction

It is **not** the repository for the proprietary production source code of the PocketBI commercial products.

## Good contributions

Examples:

- fixing documentation typos
- clarifying a confusing workflow
- improving synthetic examples
- correcting a broken public link
- improving accessibility of documentation
- documenting a reproducible public-facing bug without confidential data
- suggesting a clearer explanation of a product concept

## Do not contribute

Do not add:

- credentials or environment values
- customer data
- private screenshots containing sensitive information
- copied proprietary source from private repositories
- private deployment configuration
- internal release SHAs/build artifacts that are not intended for public release
- privileged API details
- exploit instructions for an unresolved vulnerability

Security problems must follow [`SECURITY.md`](SECURITY.md).

## Documentation style

Prefer documentation that is:

- task-oriented
- plain-language
- explicit about data verification
- conservative about unreleased features
- clear about what is Free, paid, beta, or Business when that distinction matters
- durable even if minor UI labels move

## Examples

Use synthetic data whenever possible.

Good:

```csv
order_id,customer_id,amount
O001,C001,40.00
O002,C002,85.50
```

Avoid examples copied from real customer or employer data.

## Product status changes

When updating [`docs/STATUS.md`](docs/STATUS.md):

- do not mark a feature Live because it exists only in source
- do not publish private TestFlight/build/release-gate details
- use dates for meaningful status snapshots
- distinguish beta/pre-release from general availability

## Pull requests

Keep changes focused and explain:

1. what public documentation problem is being fixed
2. what changed
3. whether the change makes any product-status claim
4. whether any screenshot/sample data has been sanitized

## Proprietary product source

Public contribution to this repository does not grant access to private PocketBI product repositories or imply that the commercial product source is open source.
