# Reflection routing and compound to-do splitting

Lessons from correction sessions where a user reviewed Groundwork outputs after confirming to-dos and a solo reflection.

## Compound to-dos

When a confirmed item contains multiple separable physical or cognitive actions, split it before writing to the to-do app. Preserve the user's wording where possible, but separate by ownership, context, or outcome.

Examples:
- `Check storage for the bigger suitcase and buy/bring swim trunks` should become:
  - `Check storage for the bigger suitcase.`
  - `Buy or bring additional swim trunks for the trip.`
- `Ask someone to handle an announcement, give them a short script, and get the song too` should become:
  - `Ask someone to handle the announcement and give them a short script.`
  - `Choose/get the song for the announcement.`

Heuristics:
- Split on `and` when actions can be done independently, have different contexts, or one could be completed while the other remains open.
- Keep together when the second phrase is merely the method or payload needed to complete the first task; for example, `ask someone to handle an announcement and give them the script` can stay together because the script is part of making the ask actionable.
- Treat parenthetical additions such as `need song too` as candidate separate tasks unless they are clearly assigned to the same person and share the same completion moment.
- After splitting an already-created reminder, delete the combined reminder, add the split reminders, verify, and record the correction in Groundwork state so backfills do not recreate the combined item.

## Solo reflection routing

A first-person solo reflection should create a journal entry first. A topical or living note can receive a concise durable synthesis only when the reflection contributes a reusable idea, decision frame, or recurring theme.

Important distinction:
- Journal: the user's first-person reflective record, lightly edited, timestamped, prose-only. This is the primary home for solo reflections, including career-direction reflections or comparisons between possible life/work paths.
- Living topical note: compact synthesis of durable insight, sourced to the session, not a replacement for the journal.

If a reflection was incorrectly routed only to a topical note, correct it by:
1. Creating or appending the appropriate `Journal/YYYY-MM-DD.md` entry.
2. Removing or reducing the topical-note entry if it was merely a journal substitute or duplicated the same reflection.
3. Recording the routing correction in the local Groundwork state.
4. Leaving immutable session notes unchanged.
