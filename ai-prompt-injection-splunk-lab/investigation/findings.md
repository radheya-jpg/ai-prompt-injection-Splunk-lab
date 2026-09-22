# Findings

## Key Findings

- The poisoned RAG document successfully influenced the model in one trial.
- The successful session invoked both `file_read` and `web_fetch`.
- The retrieved prompt context exposed the indirect injection.
- Other trials produced refusals or malformed/incorrect tool calls and did not complete the same chain.
- Session-level correlation was useful for separating an actual successful chain from isolated failed attempts.

## Detection Logic

A session that invokes both:

- `file_read`
- `web_fetch`

is treated as suspicious because the combination indicates local data access followed by external network interaction.

This is a lab-specific behavioral detection, not proof that every occurrence represents malicious activity.
