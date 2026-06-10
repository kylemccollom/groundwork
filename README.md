# Groundwork

**A personal memory layer built from your real life - powered by [Granola](https://granola.ai), your AI agent, and Obsidian.**

Granola is memory for your professional life. Groundwork is memory for your *actual* life.

Run Granola all day - conversations, walks where you think out loud, dinners with friends, doctor appointments - and Groundwork turns those recordings into organized, durable, queryable memory:

- **People files** that fill themselves in. Every fact you learn about someone in passing - their move, their new job, their favorite restaurant - accumulates into a living profile. A personal CRM with zero data entry.
- **A journal you never sat down to write.** Talk to yourself on a walk; Groundwork turns it into cohesive first-person prose in your voice, preserving the uncertainty you actually felt.
- **To-dos you said out loud** and would have forgotten, surfaced for one-tap confirmation.
- **Health, household, and project context** routed to the right living documents - your doctor's instructions, your plant care schedule, your project decisions.
- **Recurring themes** - the decision you've circled in six different conversations without noticing.

Then ask your agent things like:

> *"What do I know about Sam?"*
> *"What did that friend tell me about the slow carb diet?"*
> *"What have I been coming back to lately?"*
> *"What did I commit to last week that I haven't done?"*

## How it works

This isn't an app. It's a **skill** - an operating manual you hand to an AI agent that already has tool access (Claude with MCPs, OpenClaw/Hermes, or any agent that can read Granola, write files, and message you).

```
Granola records your day
        ↓
Your agent checks for new sessions (hourly + on demand)
        ↓
Classifies each session: conversation / solo reflection / junk
        ↓
Extracts: people facts · to-dos · journal prose · health · household · projects
        ↓
Writes immutable session notes + journal entries
        ↓
Messages you ONE digest: "here's what I saved, confirm these few things?"
        ↓
Updates living documents in your Obsidian vault
```

## The design principles that make it trustworthy

1. **Session notes are immutable.** The raw record of each session is written once and never edited. Everything is auditable.
2. **Living documents are synthesized.** People files, health docs, themes - continuously updated from sessions, never written by hand.
3. **Corrections are append-only retractions.** "That was wrong" never deletes - it appends a retraction. Retracted facts vanish from answers but stay in the log.
4. **The agent never guesses when uncertain.** Unclear speaker? Ambiguous name? Sensitive claim? It asks. A missed fact is recoverable; a confident wrong fact poisons trust.
5. **To-dos always require your confirmation.** Nothing lands in your task app without a yes.
6. **Nothing empty is ever created.** The vault grows organically - no scaffolding of blank folders.

## Setup

**You need:**
- [Granola](https://granola.ai) installed and recording (the skill processes recordings; it doesn't make them)
- An Obsidian vault - or just a folder; the skill will help you create one ([Obsidian](https://obsidian.md) itself is optional, it's just the nicest way to read the output)
- An AI agent with: Granola MCP access (API-key based), file read/write, and a way to message you

**Install:**
1. Copy `skills/groundwork/SKILL.md` into your agent's skills directory
2. Tell your agent: *"set up groundwork"* - it will walk you through connecting Granola, locating or creating your vault, and choosing your to-do app
3. Run *"check granola"* once manually and review the first digest before enabling the hourly schedule

**Recording tip:** Use Granola on your phone - that's what makes this work for your whole life, not just your desk. The lock-screen widget starts a session in one tap. Note that Granola is session-based, so you may need to start and stop sessions every hour or so throughout the day (some users set up hourly iOS Shortcut automations to handle this; others just start a long session in the morning and restart it a few times during the day).

## Privacy

- Raw transcripts are never persisted by the skill - Granola remains the source record
- Credentials (passwords, keys, account numbers) heard in any recording are redacted and never written anywhere
- Sensitive content (money, legal, health, family tension, negative claims about others) defaults to requiring your confirmation before it's saved - you can loosen this
- Your interpretation of relationships is kept separate from facts about people, and only ever sourced from your solo reflections
- Everything lives in plain markdown files in a folder you own

**Recording other people:** You are responsible for complying with your local consent laws when recording conversations. Many jurisdictions require all parties' consent.

## FAQ

**Why not just use Granola's own notes?** Granola is built around discrete meetings. Groundwork is built around people and time - it synthesizes *across* sessions into living documents, catches recurring themes, and writes your journal. Different product, same recordings.

**Does this replace my note-taking?** No - it captures what you'd never have written down anyway. The conversation at dinner. The thought on the walk. The thing your doctor said that you forgot in the parking lot.

**What agent does this work with?** Any agent that can run skills and has the required tool access. Tested with Claude (via MCPs) and personal agents like OpenClaw and Hermes.

## Repo structure

```
skills/groundwork/SKILL.md   ← the skill: agent instructions only
README.md                    ← this file: human setup + philosophy
```

---

*Built on the idea that capture should be passive and memory should compound. The best journal is the one you never had to write.*
