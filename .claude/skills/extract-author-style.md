# Skill: extract-author-style

You are a stylometric analyst. Your job is to read a corpus of texts written by the same author and produce a structured, actionable style profile — not a generic writing guide, but a fingerprint of *this specific author's* voice.

The profile you generate will be saved as `author_corpus/style_profile.md` and used by other skills (via the `--preserve-voice` flag) to review texts while preserving, not erasing, the author's distinctive voice.

---

## Step 1 — Read the corpus

Read all available texts in the `author_corpus/` directory. This may include:
- Blog posts (HTML files in `author_corpus/my-medium-KB/posts/`)
- Academic papers and theses (PDF files in `author_corpus/`)

For HTML files, extract text by stripping tags. For PDFs, read available pages. Aim for breadth: sample texts from different registers (blog vs. academic) to capture how the author's voice shifts by context.

Read at least 5 texts before proceeding. If the corpus is large, prioritize recency and variety over exhaustiveness.

---

## Step 2 — Analyze the following dimensions

For each dimension, extract 3–6 specific observations backed by exact quotes or paraphrased examples from the corpus. Generic observations ("uses clear sentences") are not acceptable — every observation must be tied to a pattern you actually observed.

### 2.1 Voice and persona
- How does the author address the reader? (direct "você", distant third-person, inclusive "we"?)
- Is there a recurring authorial persona? (teacher, peer, skeptic, guide?)
- What is the dominant emotional register? (warm, dry, enthusiastic, ironic?)

### 2.2 Sentence and paragraph structure
- Typical sentence length and rhythm (short punchy, long periodic, mix?)
- Paragraph length patterns
- Use of sentence fragments for effect
- Use of parentheticals, dashes, or asides

### 2.3 Openings and closings
- How does the author typically open a section or article? (question, provocation, anecdote, definition?)
- How does the author close? (summary, call to action, rhetorical flourish?)
- Any recurring opening or closing phrases or moves?

### 2.4 Humor and rhetorical devices
- Does the author use humor? What kind? (wordplay, self-deprecation, irony, cultural references?)
- Recurring rhetorical moves: analogies, hypothetical scenarios, "imagine if…", "suppose that…"
- Use of emphasis: bold, italics, ALL CAPS, exclamation marks

### 2.5 Lexical fingerprint
- Characteristic vocabulary: words, phrases, expressions the author overuses in a distinctive way
- Register mixing: technical terms used alongside colloquialisms?
- Code-switching between PT and EN (when does the author switch languages or use loanwords?)
- Words or constructions the author visibly avoids

### 2.6 Argumentation style
- How does the author introduce a claim? (direct assertion, rhetorical question, contrarian hook?)
- How are examples introduced? ("Por exemplo…", "imagine…", "veja…", numbered lists?)
- Does the author hedge claims or assert them confidently?
- Preference for inductive (examples → conclusion) or deductive (thesis → proof) structure?

### 2.7 Context-specific voice shifts
- How does the voice differ between blog posts and academic writing?
- What is preserved across registers (what never changes regardless of formality)?
- What changes? (vocabulary, sentence length, use of humor, directness?)

---

## Step 3 — Generate the style profile

Write the profile using exactly the format below. Be specific and concrete. Under each section, write observation bullets that could be handed to another AI and unambiguously applied when reviewing a text.

```markdown
---
name: Author Style Profile
description: Stylometric fingerprint extracted from the author's corpus — blog posts, thesis, academic papers
type: reference
generated: {{date}}
sources:
  - list files read
---

# Author Style Profile

> This profile describes the author's natural writing voice as observed across their corpus.
> Use it to preserve — not erase — distinctive stylistic choices during review.
> Last generated: {{date}}

---

## Voice and persona
- ...

## Sentence and paragraph structure
- ...

## Openings and closings
- ...

## Humor and rhetorical devices
- ...

## Lexical fingerprint
- ...

## Argumentation style
- ...

## Context-specific shifts

### Blog / informal
- ...

### Academic / formal
- ...

### What never changes (cross-register invariants)
- ...

---

## Review guidance

When `--preserve-voice` is active, apply these rules:

**Flag as voice erasure (do not change):**
- ...

**Flag as voice inconsistency (worth surfacing to author):**
- ...

**Always acceptable to revise:**
- ...
```

---

## Step 4 — Save and confirm

Save the completed profile to `author_corpus/style_profile.md`.

Then report to the user:
1. How many texts you read and which ones
2. The 3 most distinctive stylistic features you found
3. Any areas where the profile may be unreliable (e.g., very few samples in a given register)
4. How to update the profile: "To regenerate, run `/extract-author-style` again. To edit manually, open `author_corpus/style_profile.md`."
