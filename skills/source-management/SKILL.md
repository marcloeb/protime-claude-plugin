---
name: source-management
description: Manage briefing sources and settings — add or remove URLs, change the schedule or categories, pause or resume a briefing. Activates when users share a feed or newsletter URL, or want to change how a briefing runs.
---

# Source Management

## When to Activate

- The user shares a URL (newsletter, RSS feed, blog) for a briefing
- The user wants to see, add or remove sources
- The user wants to change the schedule or categories, or pause / resume a briefing

## Workflow

### Sources

- **List:** `manage_sources` with only `briefingId`.
- **Add:** `manage_sources` with `add: [URLs]`. Duplicates are skipped; report `added` and `duplicatesSkipped`.
- **Remove:** list first, confirm with the user, then `manage_sources` with `remove: [source IDs]`.
- Several briefings → ask which one the source belongs to (`get_briefings` gives the IDs).

### Settings

- **Show:** `manage_config` with only `briefingId` → schedule, categories, sources, stats.
- **Change:** `manage_config` with `updates`:
  - `schedule`: `daily`, `weekly` or `monthly`
  - `categories`: list of category names
  - `active`: `false` pauses the briefing, `true` resumes it

## Principles

- Adding a source should be one step: URL in, confirmation out.
- Always say which briefing was changed.
- Pausing stops new issues; nothing is deleted. There is no delete tool — to remove a briefing for good, the user does it in the Protime web app.
- If a tier limit is hit, relay the tool's message as written.
