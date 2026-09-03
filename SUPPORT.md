# PocketBI Support

Official support center:

https://pocketbi.app/support

Support email:

**support@pocketbi.app**

## Before reporting a bug

For data-related problems, first confirm:

1. The original file opens correctly in a standard spreadsheet application.
2. The file format is one the product supports.
3. You can identify the exact step where the result first becomes unexpected.
4. Refreshing/retrying does not resolve a temporary loading problem.
5. You have preserved the original source file.

## What to include

A useful bug report includes:

- product: PocketBI / PocketClean / PocketViz / PowerSnap / Reconcile / bIDE / PocketBI Business / iOS app
- web or iOS
- browser/device and OS where relevant
- approximate date/time of failure
- what you were trying to do
- exact steps
- expected result
- actual result
- visible error message
- whether retry worked
- a sanitized sample file if the structure of the data is necessary to reproduce the issue

For data-integrity issues, also include expected vs actual:

- row count
- column count
- relevant headers
- representative values

## Sanitize sample data

A good reproduction file should keep the shape of the bug without exposing real business information.

For example:

```csv
customer_id,region,amount
C001,North,125.00
C002,South,80.00
C999,,40.00
```

is usually better for public debugging than uploading a real customer export.

## Do not post publicly

Never include:

- passwords
- login/recovery codes
- API keys
- access tokens
- session cookies
- payment-card numbers
- signing credentials
- private customer data
- private employee data
- confidential company datasets

## Security issues

If the problem involves authentication bypass, unauthorized data access, exposed secrets, cross-account data, or another security concern, **do not create a public issue**.

Follow [`SECURITY.md`](SECURITY.md).

## Feature requests

Feature requests are most useful when they describe the job rather than only the proposed button.

Helpful:

> “Every Monday I receive the same vendor CSV and need the same five cleanup rules before I can report on it.”

Less useful:

> “Add more automation.”

Explain:

- what you are trying to accomplish
- how often you do it
- which product you use today
- what is slow or confusing
- what a successful workflow would look like

## Documentation issues

Documentation corrections are welcome in this repository. See [`CONTRIBUTING.md`](CONTRIBUTING.md).
