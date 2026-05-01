# Skills Guide

## How skills work

Each skill is a structured reviewer prompt. When you invoke a skill, it applies a specific analytical lens to your text and returns structured feedback with:
- A verdict per dimension (Forte / Adequado / Fraco / Ausente)
- Specific findings tied to exact passages
- Concrete actions required

Skills don't soften feedback. A weak section gets called weak.

---

## Skill reference

### `/grant-review` — FAPESP PIPE Proposal Review

**What it does:** Applies the full 7-dimension FAPESP PIPE assessment framework, simulating an ad hoc assessor's evaluation. Scores each dimension and identifies problems that would cause rejection.

**When to use:** After you have a draft with all sections present (even if rough). Don't use it on a half-written proposal — run `/structural-edit` first.

**Key dimensions assessed:**
- Research project (objectives, methodology, timeline)
- Team qualifications (Principal Researcher is the #1 factor)
- Commercial viability (market, competition, go-to-market)
- Budget adequacy and eligibility
- IP landscape and freedom to operate
- TRL alignment with the requested phase
- Prior phase results (Fase 2 only)

**Common output:** A list of blocking issues (would cause rejection) vs. relevant issues (would weaken the proposal), and a prioritized action list.

---

### `/argumentation` — Logical Structure Audit

**What it does:** Maps claims, checks whether each is supported, identifies logical fallacies, and flags internal inconsistencies.

**When to use:**
- Discussion sections of scientific articles
- Innovation and market justification sections of grant proposals
- Any text where you're making a case for something

**Not for:** Methodology descriptions (use `/scientific-review`) or prose quality (use `/style-clarity`).

---

### `/scientific-review` — Peer Review Simulation

**What it does:** Evaluates research design, methodology, statistical reasoning, and conclusions using peer-review standards. Returns a recommendation (Accept / Minor revision / Major revision / Reject).

**When to use:** Scientific articles, technical reports, methodology sections of grant proposals.

**Ask yourself first:** Is the document empirical (has data, methods, results)? If yes, use this skill. If it's argumentative or conceptual, use `/argumentation` instead.

---

### `/structural-edit` — Document Architecture

**What it does:** Produces a structural map of the document (section-by-section verdict), identifies misplaced or redundant sections, and proposes a rewrite plan.

**When to use:** Always first, before content-level skills. Fixing a structural problem after polishing prose wastes time.

**Output includes:** A section map, list of structural issues by severity, and a prioritized rewrite plan (what to move, cut, expand, or split).

---

### `/style-clarity` — Prose Quality

**What it does:** Identifies clarity issues, imprecise language, unnecessary wordiness, jargon mismatches, and register inconsistencies. Suggests specific revisions.

**When to use:** Final pass before submission. Don't use it early — if the structure changes, prose edits are wasted.

**Important:** Tell it the target audience before running. A text for journal reviewers gets different feedback than one for a Medium post.

---

### `/fact-check` — Claim Verification

**What it does:** Classifies each substantive claim as Verified / Plausible but uncited / Requires verification / Suspect / Unverifiable. Flags statistics, attributions, and empirical claims that need sources.

**Limitation:** It does not fabricate sources. If it can't verify a claim, it flags it for the author to verify independently.

**When to use:** Before submission, after `/argumentation`. Run it on sections with statistics, citations, and factual claims.

---

### `/references` — Bibliography Management

**What it does:** Checks coverage (in-text vs. reference list), formatting consistency, field completeness, and citation quality. Can reformat references from one style to another.

**When to use:** Near-final draft. Not worth running early.

**Cannot do:** Verify that a reference exists or says what the author claims — use `/fact-check` for that.

---

## Combining skills effectively

Skills are composable. The order matters:

**Wrong order:** `/style-clarity` → `/structural-edit`
You'll polish prose in sections that might get moved or cut.

**Right order for most documents:**
1. Structure first (`/structural-edit`)
2. Content and argument (`/grant-review` or `/scientific-review` + `/argumentation`)
3. Facts and sources (`/fact-check` + `/references`)
4. Prose last (`/style-clarity`)

---

## Interpreting feedback

- **Blocking issue**: would cause rejection or major revision. Fix before submission.
- **Relevant issue**: weakens the proposal but wouldn't alone cause rejection. Fix if time allows.
- **Minor issue**: polish. Address in final pass.

When a skill gives you a long list, work top-down by severity. Don't fix minor issues while blocking ones are open.
