---
name: briefing
description: Get your latest briefing summary — what happened, what's important, what to do
---

# /briefing

Show the latest issue of a briefing, or a short overview of all of them.

Argument: [briefing topic or "all"]

## Usage

```
/protime:briefing
/protime:briefing AI regulations
/protime:briefing all
```

## Instructions

1. Call `get_briefings` (with `active: true`). Each briefing comes with its `latestIssue`.
2. No argument and exactly one briefing → use it. Several → list them and ask which one.
3. A topic is given → pick the briefing whose topic matches; or call `get_issues` with `briefingName` (fuzzy match).
4. `all` → for each active briefing read its latest issue and give 2–3 bullets per briefing.
5. Read the issue with `get_issue` (`issueId` from step 1 or `get_issues`, plus `briefingId` for a faster lookup).
6. If a briefing has no issue yet, say so and give its schedule from `get_briefings`.

## Output Format

```
[Topic] — [Date]

→ [Most important item, with what it means for the user]
→ [Second item]
→ [Third item]

Sources: [source names with links]
```

## Guidelines

- Lead with what matters most; 3–5 bullets by default, the full category breakdown only on request.
- Keep every article's source link.
- Plain language, no marketing tone.

## Related

- `/protime:search [keyword]` — find a topic across past issues
- `/protime:discover [topic]` — start tracking a new topic
