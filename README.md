# Groundwork

**Record your day. Ask your agent anything about your life.**

Most of your life happens out loud and disappears. The restaurant a friend swore by. The thing your doctor told you in the last two minutes of the appointment. The idea you talked through on a walk and never wrote down. What you promised someone you’d send them.

Groundwork keeps it. Run [Granola](https://granola.ai) on your phone throughout your day, hand this skill to your AI agent, and it turns your recordings into notes you can actually use - then answers things like:

> *“I’m seeing Sam tonight - what’s going on in his life?”*
> *“What gift ideas has my partner dropped in the last few months?”*
> *“What did the doctor say about the dosage?”*
> *“What did I promise people this week that I haven’t done?”*

## What you get

- **A profile of everyone in your life that writes itself.** Their new job, their move, their favorite wine - mentioned once in passing, saved forever.
- **A journal you never sat down to write.** Think out loud on a walk; it becomes a real entry, in your voice, rambles smoothed out but nothing rewritten.
- **To-dos you said out loud** and would have forgotten. Sent to you for one-tap approval before anything hits your task list.
- **What the doctor actually said.** Instructions, medications, follow-ups - filed where you can find them.
- **Patterns you can’t see from inside.** You’ve talked about quitting in six different conversations. It noticed.

## How it works

```
Granola records your day (phone in your pocket)
        ↓
Your agent checks for new sessions every hour
        ↓
Pulls out what matters: people · to-dos · journal · health · projects
        ↓
Texts you one short digest: "saved these, confirm those?"
        ↓
Files everything as plain markdown in your Obsidian vault
```

That’s it. No app to check. No notes to take. You talk, you live your day, and your agent quietly gets smarter about your life.

Granola covers your work meetings. Groundwork covers everything else - and it reads your work meetings too, so the meeting and the walk home where you processed it land in the same place.

## The rules it follows

This thing handles your real life, so it’s deliberately careful:

1. **It never guesses.** Unclear who was talking? Not sure if you meant it? It asks instead of saving.
1. **Nothing hits your to-do list without a yes.**
1. **Daily records are never edited after they’re written.** You can always see exactly what was captured.
1. **“That was wrong” works.** Corrections stick, and corrected facts stop appearing in answers.
1. **Sensitive stuff waits for your approval** - money, health, family, anything negative about someone. Nothing touchy gets saved silently.
1. **Everything is plain markdown in a folder you own.** No database, no lock-in. Open it in Obsidian, grep it, sync it, leave anytime.

## Setup

**You need:**

- [Granola](https://granola.ai) installed and recording (this skill processes recordings; it doesn’t make them)
- A folder for your notes - the skill will create one, and [Obsidian](https://obsidian.md) is the nicest way to read it
- An AI agent that can read Granola (API-key MCP), write files, and message you - Claude, OpenClaw, Hermes, or similar

**Install:**

Give your agent a link to this repo and ask it to install. That’s the whole thing:

```
Install this skill and set it up for me:
https://github.com/kylemccollom/groundwork/blob/main/SKILL.md
```

Your agent walks you through connecting Granola, picking your vault, and choosing your to-do app. Then say *“check granola”* once and review the first digest before turning on the hourly schedule.

**Recording tip:** Use Granola on your phone - that’s what makes this cover your whole life, not just your desk. The lock-screen widget starts a session in one tap. Granola is session-based, so you may need to start and stop sessions every hour or so (some people automate this with iOS Shortcuts; others just restart a long session a few times a day).

## Privacy

- The skill never stores raw transcripts - Granola stays the source of record
- Passwords, account numbers, and anything credential-like heard in a recording are scrubbed and never written anywhere
- Sensitive content requires your confirmation before it’s saved - you can loosen this if you want
- Your interpretation of relationships is kept separate from facts about people, and only ever sourced from your solo reflections
- Everything lives in markdown files on your machine, in a folder you control

**Recording other people:** You’re responsible for following your local consent laws. Many places require everyone’s consent to record a conversation.

## FAQ

**Why not just use Granola’s notes?** Granola is for work meetings. Groundwork is for everything that would never have been captured at all - the dinner, the walk, the errand, the appointment - and it auto-processes all of it into the right places: people profiles, journal entries, to-dos, health notes.

**Is this a memory system for agents?** It’s the part those projects skip: deciding what your day actually meant. Which sentence is a fact about a friend, which is a to-do, which was a hypothetical that should never be saved. The output is plain markdown - point any tool you like at it.

**Does this replace note-taking?** It captures what you were never going to write down anyway. The dinner conversation. The parking-lot amnesia after a doctor visit. The shower thought you said out loud in the car.

**What agent does this work with?** Anything that can run skills and has the tool access above. Tested with Claude (via MCPs) and personal agents like OpenClaw and Hermes.

## Repo structure

```
SKILL.md    ← the skill: agent instructions only
README.md   ← this file: human setup + philosophy
```

-----

*The best journal is the one you never had to write.*
