---
name: topic-tracking
description: Track any topic with automatic source discovery and recurring AI briefings. Activates when users want to stay informed, follow a market, monitor competitors, or ask about newsletters and feeds for a topic.
---

# Topic Tracking

Protime finds the sources for a topic itself (newsletters, RSS, web) and delivers recurring AI summaries.

## When to Activate

- «Keep me updated on…», «track», «follow», «monitor», «stay on top of»
- The user wants to watch competitors, an industry, a regulation or a trend
- The user asks which newsletters or feeds cover a topic

## Workflow

1. Sharpen the topic with the user if it is broad («AI» → «EU AI Act compliance for banks»).
2. Confirm topic and an optional description (regions, angles, exclusions).
3. `create_briefing` with `topic` and `description` → source discovery runs, a `briefingId` comes back.
4. Offer schedule changes (`manage_config`) and extra sources (`manage_sources` with `add`).
5. Existing briefings: `get_briefings` lists them with their latest issue.

## Principles

- Discovery is the value — the user should not have to hunt for sources.
- Confirm before creating a briefing.
- Free tier: 1 briefing; Pro: unlimited. If the limit is hit, the tool says so.

## Swiss companies

If the topic is a Swiss company («track what happens at Muster AG»), the register is the better first stop: `check_companies` / `search_shab` show official publications with the signed PDF. A news briefing complements that; it does not replace it. See the `swiss-register` skill.

## Related

- `/protime:discover`, `/protime:briefing`, `/protime:search`, `/protime:check`
