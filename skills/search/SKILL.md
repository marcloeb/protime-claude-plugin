---
name: search
description: Search across your briefing issues for a topic or keyword
---

# /search

Find articles across past issues of your briefings.

Argument: [keyword to search for]

## Usage

```
/protime:search EU AI Act
/protime:search competitor pricing
/protime:search "Series B"
```

## Instructions

1. Call `search_issues` with `keyword`. It searches ACTIVE briefings; set `briefingId` to search one specific briefing, including archived ones.
2. Raise `maxIssues` (up to 10) if the user wants to go further back.
3. Present matches newest first, grouped by briefing.
4. To go deeper into a match, read the full issue with `get_issue`.
5. No matches → say so, and offer to search a specific (possibly archived) briefing or to start tracking the topic with `/protime:discover`.

## Output Format

```
[count] matches for "[keyword]":

[Briefing topic] — [Date]
  • [Article title]
    [2–3 sentence excerpt]
    Source: [name, link]
```
