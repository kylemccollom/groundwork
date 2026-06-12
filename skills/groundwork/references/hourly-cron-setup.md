# Hourly cron setup for Groundwork

Use this during first-run onboarding and whenever the user asks whether Groundwork is already checking Granola automatically, or asks to check every hour.

Onboarding rule: the agent should proactively verify/create this job as part of setup. Do not rely on the user remembering to ask for hourly checking later. Setup is only complete when an enabled hourly job exists, a paused equivalent has been intentionally left paused, or the user explicitly chose manual-only mode.

## Verify before creating

Always list existing cron jobs first. Do not assume the hourly job exists just because the skill mentions hourly operation.

Look for a job like:
- name: `Groundwork hourly Granola check`
- schedule: `every 60m` or hourly cron
- skills include `groundwork` and usually `obsidian`
- deliver target is the origin/current user channel

If an equivalent enabled job exists, report that it is already set up and include the next run time. If an equivalent paused/disabled job exists, ask or resume/update it rather than creating a duplicate.

## Good default job shape

Schedule: `every 60m`
Name: `Groundwork hourly Granola check`
Skills: `groundwork`, `obsidian`, and the user's to-do skill if configured, e.g. `apple-reminders`.
Deliver: origin/current conversation unless the user specifies another channel.

Prompt should be self-contained and include:

```text
Run the Groundwork hourly check for Kyle.

Use the loaded Groundwork skill. Read `/Users/mervagent/.hermes/groundwork-state.json` first. Use Granola MCP tools to fetch sessions since `last_processed_created_at` / last check. Process only new, unprocessed sessions. Skip sessions under 2 minutes or clear junk, but mark considered session IDs in state. Write session notes and safe living-doc updates to the Obsidian vault configured in state. Do not create Apple Reminders without explicit user confirmation. Batch any confirmations into one concise iMessage digest. If there is nothing notable and no confirmations, stay silent / produce no user-facing message beyond a minimal internal final. Do not schedule other cron jobs.
```

Avoid hard-coding a vault path in the cron prompt unless the state file has been verified recently. Prefer “vault configured in state” so a later vault migration only needs a state update.

## Confirmation style

After creating or verifying the job, answer briefly:

- “It was already set up: next run …”
- or “It wasn’t set up yet; I created it. It runs hourly and only pings when something useful or a confirmation is needed.”
