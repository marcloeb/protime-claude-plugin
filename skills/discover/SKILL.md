---
name: discover
description: Start tracking a new topic — Protime finds the sources automatically
---

# /discover

Create a briefing for a topic. Protime discovers newsletters, RSS feeds and web sources itself and schedules recurring AI summaries.

Argument: [topic to track, e.g. "AI regulations in Europe"]

## Usage

```
/protime:discover AI safety
/protime:discover climate tech in DACH
/protime:discover competitor moves in Swiss private banking
```

## Instructions

1. If the topic is broad («AI», «finance»), suggest 2–3 sharper versions and let the user pick. A sharp topic gives better sources.
2. Confirm the final topic (3–100 characters) and an optional description of what matters (max. 500 characters: regions, angles, what to leave out).
3. Call `create_briefing` with `topic` and `description`. It runs source discovery and returns the `briefingId`.
4. Show what was set up. Then offer:
   - another schedule (`daily`, `weekly`, `monthly`) → `manage_config` with `updates.schedule`
   - extra sources the user already reads → `manage_sources` with `add`
5. If the tier limit is reached, the tool says so. Pass the message on as written.

## Output Format

```
Your briefing "[topic]" is set up.

Schedule: [schedule]
Sources: [count] found automatically
First issue: [when, per the tool's message]

Add a source anytime: "add [URL] to my [topic] briefing"
```

## Guidelines

- Confirm before creating; do not create a briefing from an ambiguous request.
- Do not promise a delivery time the tool did not return.
