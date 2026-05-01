# Proofwright

**Where proof meets craft — an AI-augmented writing companion for technical and scientific authors.**

Proofwright is a personal, open writing framework that pairs your domain expertise with an AI agent to produce sharper arguments, cleaner prose, and more rigorous work. From Medium blog posts to FAPESP grant proposals, from technical books to peer-reviewed papers — Proofwright helps you write better, not instead of you.

> *"wright"* — an artisan who builds things by hand.
> *"proof"* — both the rigor of science and the act of careful revision.

---

## Why Proofwright?

Writing technical and scientific content is demanding. You need clarity of argument, factual accuracy, methodological soundness, and stylistic consistency — often across very different formats. Proofwright gives you a structured set of AI-powered skills to support each stage of the writing process, while keeping you in the driver's seat.

**This project is transparent by design.** Proofwright doesn't ghostwrite — it co-writes. Every contribution is visible, reviewable, and yours to accept or reject.

## What it does

Proofwright provides reusable prompt instructions ("skills") organized around core writing activities:

- **Argumentation audit** — Checks logical structure, identifies weak claims, flags unsupported assertions, and suggests where evidence is needed.
- **Fact-checking** — Cross-references claims against known literature and flags statements that need citation or verification.
- **Scientific review** — Evaluates methodology descriptions, statistical reasoning, and adherence to disciplinary standards.
- **Structural editing** — Analyzes document organization, flow, transitions, and section balance.
- **Style & clarity** — Tightens prose, removes jargon where unnecessary, and adapts tone for the target audience (academic journal, technical blog, general public).
- **Grant & proposal review** — Assesses alignment with funding body criteria (e.g., FAPESP PIPE: innovation, commercial viability, TRL, methodology).
- **Reference companion** — Helps organize, format, and verify bibliographic references.

## Supported formats

| Format | Use case |
|---|---|
| Blog posts | Medium, Dev.to, personal sites |
| Scientific articles | Journal submissions, preprints |
| Technical books | Chapters, book proposals |
| Grant proposals | FAPESP PIPE, CNPq, FINEP |
| Technical reports | Internal docs, white papers |

## Getting started

### Prerequisites

- A coding agent with custom instructions support (e.g., Claude Code, Cursor, or similar)
- Git

### Installation

```bash
git clone https://github.com/YOUR_USERNAME/proofwright.git
cd proofwright
```

Then configure your agent to load the skills from the `skills/` directory. See [docs/setup.md](docs/setup.md) for platform-specific instructions.

### Quick example

Point Proofwright at any draft:

```
Review this draft for argumentative rigor and flag any claims that lack supporting evidence.
```

The agent will activate the relevant skills automatically and return structured feedback with specific, actionable suggestions tied to exact passages in your text.

## Project structure

```
proofwright/
├── skills/                  # Core writing skills
│   ├── argumentation/       # Logical structure & claim analysis
│   ├── fact-checking/       # Verification & cross-referencing
│   ├── scientific-review/   # Methodology & statistical reasoning
│   ├── structural-editing/  # Organization & flow
│   ├── style-clarity/       # Prose quality & audience adaptation
│   ├── grant-review/        # Proposal-specific criteria
│   └── references/          # Bibliography management
├── templates/               # Starter templates for common formats
├── docs/                    # Setup guides & documentation
├── examples/                # Sample reviews & before/after drafts
└── README.md
```

## Philosophy

- **Your expertise, augmented** — Proofwright amplifies your knowledge; it doesn't replace it. You are the author.
- **Transparent collaboration** — Every AI suggestion is explicit and traceable. No hidden rewrites.
- **Proof as craft** — Rigorous revision is a skill, not a chore. Good writing deserves a good process.
- **Format-agnostic** — The same principles of clear thinking and careful writing apply whether you're blogging or submitting to Nature.

## Roadmap

- [x] Core skill definitions
- [ ] FAPESP PIPE review template
- [ ] Scientific article review workflow
- [ ] Medium blog post writing assistant
- [ ] Integration with reference managers (Zotero, Mendeley)
- [ ] Multi-language support (PT-BR / EN)
- [ ] Evaluation suite for skill quality

## Contributing

Proofwright is a personal project, but contributions are welcome. If you write in technical or scientific contexts and want to improve the skills or add new ones, open an issue or submit a PR.

## License

MIT License — see [LICENSE](LICENSE) for details.

---

*Built with craft and rigor by a human, with a little help from an AI wright.*
