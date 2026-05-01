# Proofwright

AI-augmented writing companion for technical and scientific authors. Provides structured review skills for grant proposals, scientific articles, blog posts, and technical documents.

## What this project is

A set of prompt-based skills that act as rigorous reviewers — not assistants that soften feedback, but assessors that apply the same standards the final audience would. The goal is to surface problems before submission, not to validate drafts.

## Skills

Skills live in `.claude/skills/`. Each is invocable as a slash command in Claude Code.

| Skill | File | Use when |
|-------|------|----------|
| `/grant-review` | `grant-review.md` | Reviewing a FAPESP PIPE proposal (Fase 1 or 2) |
| `/argumentation` | `argumentation.md` | Auditing logical structure and claim support |
| `/scientific-review` | `scientific-review.md` | Peer-review style evaluation of methods and results |
| `/structural-edit` | `structural-edit.md` | Diagnosing document organization and flow |
| `/style-clarity` | `style-clarity.md` | Improving prose clarity, precision, and register |
| `/fact-check` | `fact-check.md` | Identifying unsupported or suspect claims |
| `/references` | `references.md` | Formatting and auditing bibliography |

## Recommended workflows by document type

### FAPESP PIPE proposal
1. `/structural-edit` — fix architecture before evaluating content
2. `/grant-review` — apply FAPESP PIPE assessment framework (7 dimensions)
3. `/argumentation` — strengthen innovation and market arguments
4. `/style-clarity` — tighten prose for final version

### Scientific article
1. `/structural-edit` — section balance, transitions, IMRaD compliance
2. `/scientific-review` — methodology, statistics, conclusions
3. `/argumentation` — discussion section logic
4. `/references` — citation completeness and formatting
5. `/fact-check` — verify claims with citations

### Technical blog post
1. `/argumentation` — is the central claim sound and well-supported?
2. `/style-clarity` — audience: technical peers or general public?
3. `/fact-check` — flag unsourced statistics or attributions

## Templates

Starter templates for each document type are in `templates/`. They include structural guidance and field-by-field instructions for the author.

## Real projects

Working drafts go in `real_projects/` (gitignored). Never commit actual proposal content or unpublished research to this repository.

## Skill design principles

- Skills are reviewers, not assistants. They find problems, not compliments.
- Each skill has a defined output format so feedback is structured and actionable.
- Skills are composable — use them in sequence, not in isolation.
- When a skill asks a clarifying question (e.g., "who is the target audience?"), answer before proceeding.
