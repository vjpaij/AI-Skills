---
name: sn-report-format-discovery
description: "Used when the user wants a recommendation for the final research deliverable format, or when the final format cannot be directly inferred from requirements. Resolves the requirement into a concise format string without creating schema or proposal files."
---

# Final Deliverable Format Recommendation

Determines a request-level `format` string based on user requirements. Like `language`, this string is passed only within the execution context of the current run and is never written to disk.

## Inputs

- Original research query `query`
- Request-level `language`
- Explicit final format specified by the user (if any)

## Rules

1. When the user explicitly specifies a deliverable format, prioritize the user's name.
2. When unspecified, select a concise name based on the primary reading task; if uncertain, default to `report`.
3. Common values include `report`, `paper`, `table`, `memo`, `timeline`, `faq`, but this is not a closed enumeration.
4. `format` denotes only the delivery medium and structure type. It does not carry chapter breakdowns, abstracts, tables of contents, structural preferences, or style guidelines; those remain in the original query.
5. Do not query external format specifications, generate candidate objects, or produce `format_proposal.json`, `format.json`, or any schema definition.
6. Do not modify the user's research question, scope, language, or workflow mode.

## Output

Return exactly one line:

```text
format: <a concise, non-empty string>
```