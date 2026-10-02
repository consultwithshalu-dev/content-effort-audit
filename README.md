# Content Effort Audit — a Claude Skill

A [Claude skill](https://www.anthropic.com/news/skills) that scores a piece
of writing the way Google's own public documentation describes "effort" —
not word count, not keyword density, but whether a real person visibly did
meaningful work to produce it.

## Background

In 2024, an automated bot accidentally pushed thousands of pages of
Google's internal Search API documentation to a public GitHub repo. Google
confirmed the documents were real. Several independent SEO analysts who
went through the leak reported the same field: `contentEffort`, described
internally as *"LLM-based effort estimation for article pages."*

There's no public API or dashboard for that real signal — nobody outside
Google can see or reproduce it. What this skill does instead is apply the
same standard Google's own public **Search Quality Rater Guidelines**
already describe to human reviewers: whether a page shows visible evidence
of real work, and whether it says something genuinely original rather than
restating what's already findable on ten other sites.

This is an independent estimate built from public documentation, **not**
Google's real internal score, and not a ranking guarantee.

## What it does

Give Claude a draft and ask it to run a content effort audit. It returns:

- An overall score out of 100, with a plain-language band (Low / Medium /
  High effort)
- A breakdown across five criteria: thoughtful curation, original
  contribution, visible evidence of work, going beyond common knowledge,
  and depth of discussion
- 3–5 specific, actionable gaps — quoting the draft where it helps show
  the problem

## Install

**In Claude Cowork / the Claude desktop app:**
Customize → Skills → Create skill → Upload a skill → select `SKILL.md`
from this repo.

**In Claude Code:**
Drop `SKILL.md` into your project's `.claude/skills/content-effort-audit/`
directory (create the folder if it doesn't exist).

**As a plugin marketplace source (Claude Desktop → Customize → Plugins):**
Add this repository's URL as a marketplace source, then sync.

## Usage

Once installed, just paste a draft into a conversation and ask something
like:

> Run a content effort audit on this draft.

No API key, no setup, no external calls — the skill is plain-text
instructions Claude follows using its own reasoning.

## License

MIT — use it, fork it, adapt the rubric, no attribution required.
