# Getting Started with PocketBI

You do not need to learn the whole ecosystem before doing useful work. Start with the smallest tool that fits the job.

## If you have one CSV or Excel file

Start with **PocketBI Workspace**.

1. Open https://pocketbi.app/Datasnap
2. Import your CSV, XLS, or XLSX file.
3. Confirm the headers and row/column counts before changing anything.
4. Review obvious quality issues such as missing values, duplicates, whitespace, inconsistent categories, or incorrect types.
5. Preview transforms before applying them.
6. Build a useful summary or chart.
7. Export the result.
8. Reopen the downloaded output and verify representative values.

That last step matters. A successful download is not the same thing as a correct result.

## If the same messy file arrives every week or month

Use **PocketClean**.

PocketClean is intended for repeatable cleanup rather than repeatedly fixing the same schema by hand.

A typical workflow is:

```text
incoming file
→ audit
→ choose deterministic cleanup
→ preview changes
→ apply
→ re-check quality
→ save/reuse workflow where supported
→ export verified result
```

## If you have an old export and a new export

Use **PocketBI Reconcile**.

Choose a stable identifier such as a customer ID, invoice ID, order ID, or another key that means the same thing in both files.

Then inspect:

- rows that were added
- rows that disappeared
- rows whose values changed
- duplicate keys
- key/type mismatches

Avoid using a display name as the match key when a stable identifier exists.

## If you only need to know what is wrong with a file

Use **PowerSnap**.

It is the shortest path for triage before deciding whether the file needs a deeper PocketClean or PocketBI workflow.

## If the data is clean and you mainly need a report

Use **PocketViz**.

Choose meaningful business dimensions and numeric measures. IDs, UUIDs, and almost-unique names usually make poor default categories.

## If you need SQL, Python, R, or JavaScript

Use **bIDE** at https://bideide.com.

bIDE is the custom-analysis exit from the point-and-click workflow. Use it when you need queries, code, notebooks, or transformations that are more naturally expressed programmatically.

## If the workflow belongs to a team or business process

Use **PocketBI Business**.

The business path is designed around organization-level repeatability rather than one person's one-off file session.

Public concepts include:

```text
Organization
→ Workspace
→ Processing workflow/profile
→ approved integration/access
→ Run
→ History / verification
```

Testing and production-oriented workflows should remain clearly separated so experimentation does not accidentally become a live business process.

## Five habits that prevent most data mistakes

1. Keep the original source file outside the application as a backup.
2. Check row and column counts before and after important changes.
3. Preview transformations whenever possible.
4. Inspect a few representative values, including blanks and unmatched records.
5. Reopen exported files independently before relying on them.

## Where to go next

- Full guide: [`USER_GUIDE.md`](USER_GUIDE.md)
- Ecosystem map: [`ECOSYSTEM.md`](ECOSYSTEM.md)
- Product status: [`STATUS.md`](STATUS.md)
- Support: [`../SUPPORT.md`](../SUPPORT.md)
