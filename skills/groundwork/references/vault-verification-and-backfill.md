# Vault verification and onboarding backfill

Use this reference when Groundwork is being set up, when the vault path changes, or when the user says Obsidian on their phone/desktop does not show the notes Groundwork wrote.

## Failure mode to avoid

Do not blindly use a fallback path such as `~/Documents/Obsidian Vault` if the user has provided a different real vault path. But do not turn cross-device mismatch into a blocker by default: users may intentionally proceed with a local/fallback vault and fix sync later. The key is to label the active target clearly and keep outputs easy to migrate.

## Verification checklist

Before a first backfill or after any vault mismatch report:

1. Ask/confirm the vault name/path when it is not already known.
2. Compare against the local candidate path when easy:
   - vault directory name
   - visible top-level folders
   - rough file/folder counts
   - presence of `.obsidian/` when available
3. If these do not match, explain the mismatch and ask whether to proceed locally or wait for the correct path only when the next write would be large, destructive, or hard to migrate.
4. If the user explicitly says to proceed with the local/fallback vault anyway, continue in that vault, but say clearly that it is a temporary/local target and keep the output easy to migrate later. Do not repeatedly re-litigate the mismatch after the user has made this override.
5. Once the correct path is available, update `groundwork-state.json` before replaying or moving notes.
6. If notes were already written into a provisional vault, treat them as generated artifacts to migrate/replay into the correct vault structure later; continuing locally is fine when the user has explicitly approved it.

## Routing adaptation examples

If the user's vault uses numbered PARA-style folders, map Groundwork outputs into it rather than creating parallel roots:

- Session notes / daily logs → `1 Daily/` or the user's chosen daily/session subfolder
- People notes → `2 People/`
- Project notes → `3 Projects/`
- Health, household, travel, preferences, reference material → usually `4 Areas/` or `7 Reference/`, depending on the existing vault convention
- Inbox captures / unclassified pending items → `0 Inbox/`

When uncertain, ask for the mapping once, then store it in `groundwork-state.json` so future runs are automatic.

## Backfill default

For newly onboarded users, run a Granola catch-up before hourly incremental processing:

- Default: last 7 days
- Offer/perform last 30 days when the user wants a fuller backfill or has meaningful existing Granola history
- Batch the digest: counts first, living notes updated next, confirmations/to-dos last
- Mark considered sessions processed/skipped only after the correct vault path has been verified
