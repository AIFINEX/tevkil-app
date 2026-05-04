# tevkil-app

> Project workspace — code + docs + decisions, all in one place.

## Layout

```
tevkil-app/
├── docs/                          # Specs, RFCs, decisions, meeting notes
│   ├── overview.md                # Product vision and scope
│   ├── tech-stack.md              # Stack choices and rationale
│   ├── requirements/              # Versioned requirement docs
│   ├── rfcs/                      # Design decisions (numbered)
│   └── meetings/                  # Meeting notes (date-stamped)
└── (code lives at the root once we start building)
```

## How we work

**Every non-trivial change goes through a Pull Request** — code, requirements, RFCs alike. PRs are how we discuss and decide. The Git history is the decision log.

1. Create a branch off `main`.
2. Make your changes (write a doc, edit an RFC, add code).
3. Open a PR. Use the PR template.
4. Request review from the relevant teammates.
5. Iterate via inline comments.
6. Merge when approved.

## Adding a new RFC

```bash
cp docs/rfcs/0000-template.md docs/rfcs/000X-short-slug.md
# edit, then PR
```

See [`docs/rfcs/README.md`](docs/rfcs/README.md) for the RFC process in detail.

## Working with AI on docs

We use Claude Code to draft, review, and refine docs. AI edits go through PRs the same way human edits do — every commit ends up reviewed by a teammate before merge.
