# RFCs (Request for Comments)

Numbered design documents that capture significant decisions before they are implemented. RFCs are how we make architectural calls visible, debatable, and traceable.

## When to write an RFC

Write one when a change:

- Affects more than one component or has cross-cutting impact.
- Picks one option among several non-trivial alternatives.
- Locks in a contract (data model, public API, integration shape).
- Costs meaningful time or money to reverse.

If a change is small and reversible, just open a code PR — no RFC needed.

## Process

1. **Copy the template:**

   ```bash
   cp docs/rfcs/0000-template.md docs/rfcs/000X-short-slug.md
   ```

   Use the next available number; one digit per RFC, zero-padded to four.

2. **Draft.** Fill in Context, Decision, Consequences, Alternatives Considered.

3. **Open a PR** titled `RFC NNNN: <topic>`. Mark it as Draft until you want feedback.

4. **Discuss.** Reviewers leave inline comments on specific lines. Authors respond and update.

5. **Merge** when the team agrees. Status in the doc becomes `Accepted`.

6. **Implement** in code PRs that link back to the RFC.

## Status values

- `Draft` — actively being written
- `In review` — open PR, gathering feedback
- `Accepted` — merged, decision made
- `Superseded by NNNN` — replaced by a later RFC
- `Withdrawn` — closed without a decision

## Index

Update this section when a new RFC is accepted.

| # | Title | Status | Date |
|---|---|---|---|
| _none yet_ | | | |
