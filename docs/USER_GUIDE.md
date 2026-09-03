# PocketBI Ecosystem User Guide

This guide explains how to use the PocketBI product family without requiring knowledge of the private implementation behind it.

The exact interface may evolve. The durable ideas are: understand your source data, preview important changes, verify results, use the smallest product that solves the job, and keep repeatable work repeatable.

---

## 1. Before you start

For important work, keep an untouched copy of the original file outside PocketBI.

Before changing data, note:

- file name
- approximate row count
- column count
- expected key columns
- important totals or values you already know

This gives you a simple baseline for checking the output later.

### Supported workflow types

PocketBI products are designed primarily around common tabular data such as CSV and Excel exports. Individual products may support additional input/output formats.

Never upload passwords, API secrets, payment card data, authentication codes, or other credentials as ordinary dataset content.

---

# Part I — PocketBI Workspace

## 2. Import a file

Open:

https://pocketbi.app/Datasnap

Import a supported CSV or Excel file using the available import controls.

After import, **do not immediately start cleaning**. First verify:

1. Are the headers correct?
2. Does the row count look right?
3. Does the column count look right?
4. Did numbers remain numbers?
5. Did dates parse in a recognizable way?
6. Are blank cells actually blank rather than shifted data?
7. Do a few known records look correct?

If the import itself is wrong, later transformations will only make the wrong data more complicated.

## 3. Review data quality

Common issues include:

- missing values
- duplicate rows
- leading/trailing whitespace
- inconsistent capitalization
- inconsistent boolean values such as `Yes`, `yes`, `TRUE`, `true`
- dates represented in multiple formats
- numbers stored as text
- currency symbols mixed with numeric values
- category aliases such as `VA`, `Virginia`, and `Va.`
- duplicated or ambiguous headers

### Do not “fix” identity data by guessing

Be especially conservative with blanks in fields such as:

- customer IDs
- employee IDs
- emails
- names
- account numbers
- transaction IDs

A missing identifier should not be auto-filled from another row merely to improve a quality score.

## 4. Manage data types

Use type controls where available to distinguish concepts such as:

- text
- integer
- decimal
- currency
- date/date-time
- boolean
- categorical data

Changing a display format and changing the underlying meaning are not always the same thing.

For example, `00123` may look numeric but actually be an identifier where the leading zeros matter. Treating it as integer `123` can damage the data.

## 5. Standardize values

Semantic standardization means bringing equivalent labels to one canonical value.

Examples:

```text
Yes / yes / TRUE / true → Yes
VA / Va. / Virginia     → Virginia
Fastball / FB / fast ball → Fastball
```

Before applying a mapping:

1. Review all unique values involved.
2. Confirm the values truly mean the same thing.
3. Preview the change where available.
4. Apply the mapping.
5. Re-check counts and representative rows.

Do not merge categories merely because their text looks similar.

## 6. Transform data

Typical transformations can include:

- filtering rows
- calculated columns
- combining columns
- splitting or cleaning text
- aggregation/grouping
- sorting
- normalization
- dataset joins

### Preview vs Apply

When PocketBI offers **Preview**, treat it as temporary inspection.

Only **Apply to dataset** (or the equivalent commit action) should change the current working dataset.

A useful habit is:

```text
choose operation
→ preview
→ inspect row count / columns / sample values
→ apply
→ inspect again
```

## 7. Aggregate data

Aggregation answers questions such as:

- revenue by region
- orders by status
- average amount by category
- total units by month

A normal pattern is:

```text
Transform
→ Aggregate / Group By
→ choose grouping column
→ choose numeric measure
→ choose operation (sum/count/average/etc.)
→ preview
→ verify totals
→ apply if desired
```

Be careful with counts. `COUNT(rows)` and `COUNT(nonblank values)` can answer different questions.

## 8. Join datasets

Joins combine related tables.

Before joining:

1. Identify the key in each dataset.
2. Confirm the key type matches on both sides.
3. Check whether the key is unique where you expect it to be unique.
4. Decide what should happen to unmatched records.

For a typical LEFT JOIN:

- every row from the left table should remain
- matching right-table values should be attached
- unmatched right-side values should remain null/blank rather than inventing a match

After a join verify:

- expected row count
- expected new columns
- unmatched rows
- representative matched rows
- no unexpected value mutation

## 9. Build a chart

Choose fields based on meaning, not simply availability.

### Bar chart

Useful for comparing categories:

- sales by region
- orders by status
- revenue by product category

### Line/area chart

Useful for ordered trends:

- revenue by month
- tickets by week
- units by date

### Scatter plot

Useful for comparing two numeric measures.

### Avoid low-value chart dimensions

Usually avoid using these as automatic categories:

- UUIDs
- row IDs
- nearly unique customer names
- timestamps where nearly every row is unique
- blank categories

If labels are crowded, use filters or Top N controls where available.

## 10. Export and verify

After exporting:

1. Open the downloaded file independently.
2. Check headers.
3. Check row count.
4. Check column count.
5. Check important totals.
6. Inspect a few matched, unmatched, blank, and edge-case rows.

Do not assume that because the export button succeeded, every value is correct.

---

# Part II — PowerSnap

## 11. Use PowerSnap for fast diagnosis

PowerSnap is useful when the first question is not “How should I transform this?” but:

> “What is wrong with this file?”

A typical workflow:

1. Load a file.
2. Review structural warnings.
3. Review missing/duplicate/type/format signals.
4. Decide whether the file needs a quick correction or a deeper PocketClean/PocketBI workflow.

If a file cannot be read, retry with the original file and verify it opens in another standard spreadsheet application. If the problem persists, follow the support guidance rather than repeatedly modifying the source file at random.

---

# Part III — PocketClean

## 12. When to use PocketClean

PocketClean is intended for repeated cleanup patterns.

Use it when:

- the same vendor sends similarly messy files every week
- dates always arrive in inconsistent formats
- the same columns repeatedly need whitespace cleanup
- categories drift in predictable ways
- a recurring export needs deterministic normalization

## 13. Recommended PocketClean workflow

```text
upload
→ audit
→ understand each issue
→ choose cleanup
→ preview
→ apply
→ re-audit
→ inspect applied transformations
→ verify result
→ save/reuse workflow when supported
→ export
```

### Deterministic is important

A repeatable cleaning rule should do the same thing when given the same input.

Examples of deterministic rules:

- trim leading/trailing whitespace
- normalize recognized date formats
- standardize explicit value mappings
- convert clearly numeric text to numeric values

Be cautious with rules that infer identity or business meaning from unrelated rows.

## 14. Verify what changed

Where the product provides transformation counts or verification metadata, use them.

Useful questions include:

- How many cells changed?
- Which operation changed them?
- Did row count change?
- Did columns change?
- Were any records removed?
- Can I identify the input and output of this run later?

---

# Part IV — Reconcile

## 15. Compare two files safely

Reconcile is for identifying differences between two versions of a dataset.

Examples:

- prior month vs current month
- before cleanup vs after cleanup
- source export vs downstream export
- expected list vs received list

## 16. Choose a match key

The best match key is:

- stable
- present in both files
- intended to identify the same entity
- unique when uniqueness is expected

Good examples:

- customer ID
- invoice ID
- employee ID
- order ID

Weak examples:

- customer display name
- row number from an export
- a field that changes frequently

## 17. Interpret results

Typical result groups include:

- added records
- missing/removed records
- changed records
- duplicate keys
- records that cannot be matched cleanly

If a result seems surprising, inspect the raw key values for:

- whitespace
- leading zeros
- text-vs-number differences
- casing
- missing values

---

# Part V — PocketViz

## 18. Build reusable visual reports

PocketViz is for turning clean data into reusable visualization workflows.

Before charting, ask:

1. What business question am I answering?
2. What is the dimension/category/date?
3. What is the numeric measure?
4. What should a reader learn in five seconds?

A chart is not useful merely because it rendered successfully.

## 19. Prefer meaningful dimensions

Often useful:

- region
- state
- status
- product category
- segment
- month/quarter
- account type

Often poor defaults:

- database IDs
- UUIDs
- almost-unique names
- full timestamps
- empty categories

---

# Part VI — bIDE

## 20. When to move to code

Use bIDE when:

- the transformation is easier to express in SQL
- you need a Python data-analysis workflow
- you need R for statistical/data work
- you need JavaScript logic
- you want a notebook-like coding environment
- a point-and-click workflow would require too many manual steps

Open:

https://bideide.com

## 21. SQL workflow

A safe SQL habit is:

1. Load/identify the source tables.
2. Inspect a small sample.
3. Run simple counts.
4. Write the transformation/query.
5. Verify row and column counts.
6. Inspect unmatched/null records after joins.
7. Export only after the result is understood.
8. Reopen exported CSV independently.

### Join verification example

For a LEFT JOIN, make sure unmatched left-side records remain present with null right-side fields.

Never accept unexpected modifications to ordinary source values as normal join behavior.

## 22. Python, R, and JavaScript

Runtime availability can vary by platform and release stage.

General recommendations:

- start with a tiny test before a large workload
- confirm the runtime loaded successfully
- inspect input data types
- avoid embedding private credentials in notebooks or shared snippets
- export only the results you intend to share

---

# Part VII — PocketBI Business

## 23. From one-off work to repeatable operations

Business workflows are for cases where a process must be repeated by a team, integration, or organization.

The public conceptual model is:

```text
Organization
→ Workspace
→ reusable processing workflow/profile
→ approved integration/access
→ Run
→ History / verification
```

## 24. Sandbox/testing vs production-oriented use

Do not treat testing and production as interchangeable.

Use test/sandbox workflows to:

- validate a new schema
- test cleanup rules
- verify integrations
- inspect outputs

Only promote/use a workflow in production-oriented operations after the expected behavior is understood.

Never place live private credentials into examples, screenshots, GitHub issues, or public documentation.

## 25. Run history and verification

For repeatable business processing, useful evidence includes:

- when a run happened
- which workflow/profile ran
- whether it succeeded
- what input/output counts were observed
- whether verification information is available

Use that history to answer “What happened?” without relying on memory.

---

# Part VIII — Accounts and plans

## 26. PocketBI ID

PocketBI ID is the shared account identity used by supported PocketBI services.

If access appears wrong after signing in:

1. Confirm you are using the intended account.
2. Refresh the account/product page.
3. Sign out and sign back in if needed.
4. If a paid entitlement is missing, verify the purchase/subscription state through the appropriate platform and contact support with non-sensitive evidence.

Never send passwords, recovery codes, full payment-card information, or authentication tokens to support.

## 27. Free, paid, and Business capabilities

Exact plan limits can change. The product UI and official PocketBI site are the authoritative current references.

In general:

- **Free** is intended for useful individual workflows without forcing immediate purchase.
- **Paid individual tiers** add larger limits, saved work, additional export/report capabilities, or other premium conveniences.
- **Business** is for organization-level repeatability, access management, integrations, and operational history.

---

# Part IX — Troubleshooting

## 28. If import looks wrong

- stop before transforming
- verify the original opens correctly elsewhere
- check delimiter/format assumptions
- check headers
- inspect rows near the first visible problem

## 29. If a transformation gives an unexpected result

- undo if available
- repeat one operation at a time
- preview before applying
- compare before/after row and column counts
- inspect edge cases such as blanks and duplicates

## 30. If a join looks wrong

Check:

- key column names
- key data types
- whitespace
- leading zeros
- duplicates
- unmatched rows

## 31. If a chart is meaningless

Choose a meaningful category/date field and a numeric measure. Avoid near-unique identifiers as categories.

## 32. If Reconcile does not match records as expected

Verify the selected match key is truly stable and equivalent in both files.

## 33. If an account or subscription looks wrong

Confirm the intended PocketBI ID and refresh account status. If the problem persists, contact support without posting private billing information publicly.

## 34. If a product shows an error

Capture:

- product name
- approximate time
- browser/device
- exact user action that failed
- exact visible error message
- whether retry worked
- a sanitized sample file if the data itself is required to reproduce the issue

Do **not** include credentials or confidential production datasets in a public issue.

---

# Part X — Data verification checklist

Before trusting an important output, verify:

- [ ] expected file loaded
- [ ] correct headers
- [ ] correct row count
- [ ] correct column count
- [ ] key identifiers preserved
- [ ] numeric precision looks correct
- [ ] dates look correct
- [ ] null/blank values remain understandable
- [ ] unmatched join records behave as expected
- [ ] aggregate totals make sense
- [ ] exported file reopens successfully
- [ ] representative values match expectations

For high-value business data, this checklist is more important than whether the interface looked successful.

---

# Part XI — Getting help

See [`../SUPPORT.md`](../SUPPORT.md).

For security vulnerabilities, follow [`../SECURITY.md`](../SECURITY.md) instead of opening a public issue.

Official public site:

https://pocketbi.app
