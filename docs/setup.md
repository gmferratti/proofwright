# Setup Guide

## Using Proofwright with Claude Code

Proofwright skills live in `.claude/skills/` and are automatically available as slash commands in Claude Code.

### Installation

```bash
git clone https://github.com/YOUR_USERNAME/proofwright.git
cd proofwright
```

Open the project in Claude Code. Skills are immediately available.

### Using a skill

Type the skill name as a slash command followed by your text or a file reference:

```
/grant-review

[paste your proposal text here]
```

Or reference a file:

```
/grant-review

Review the proposal in @minha-proposta.md
```

### Available skills

| Command | Use when |
|---------|----------|
| `/grant-review` | Reviewing a FAPESP PIPE proposal draft |
| `/argumentation` | Checking logical structure and claim support |
| `/scientific-review` | Peer-review style evaluation of methods and results |
| `/structural-edit` | Diagnosing document organization and flow |
| `/style-clarity` | Improving prose clarity and precision |
| `/fact-check` | Identifying claims that need citations or verification |
| `/references` | Formatting and auditing bibliography |

### Combining skills

Skills are composable. A typical workflow for a grant proposal:

1. `/structural-edit` — fix the overall architecture first
2. `/grant-review` — evaluate against FAPESP PIPE criteria
3. `/argumentation` — strengthen the innovation and market arguments
4. `/style-clarity` — tighten the prose for the final version

---

## Using with other agents (Cursor, etc.)

Copy the contents of the relevant `.claude/skills/*.md` file into your agent's system prompt or custom instructions panel. Skills are plain text and work with any instruction-following model.
