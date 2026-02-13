# docs/ — Specs & Tasks

Agent guide for working in `docs/`. See root `AGENTS.md` for project overview.

---

## Structure

```
docs/specs/
└── 01-spec-wedding-website/
    ├── spec.md                    # Main spec
    ├── 01-questions-round-1.md     # Questions
    ├── 01-tasks-wedding-website.md # Task list
    └── 01-proofs/                 # Proofs per demo unit
        ├── 01-task-01-proofs.md
        ├── ...
        └── 01-task-07-proofs.md
```

---

## Naming Convention

- `NN-spec-...` — Spec folders
- `NN-questions-round-N.md` — Q&A rounds
- `NN-tasks-...` — Task lists
- `NN-task-NN-proofs.md` — Proofs for a demo unit

---

## Key Files

| File | Purpose |
|------|---------|
| `spec.md` | Full spec: user stories, requirements, design tokens, tech stack |
| `01-tasks-wedding-website.md` | Implementation tasks |
| `01-proofs/*.md` | Acceptance criteria / proofs for each demo unit |

---

## When Extending Specs

1. Add new specs in `docs/specs/` with numbered folders.
2. Add new proofs in `01-proofs/` using the same naming pattern.
3. Keep spec structure aligned with user stories and acceptance criteria.

---

## Spec vs Implementation

- **Spec** — `spec.md` defines ceremony time as 4:00 PM PT
- **Source of truth** — `edit-and-notes.txt` says 5:30 PM, arrive by 5  
  When reconciling, prefer `edit-and-notes.txt` for content updates.
