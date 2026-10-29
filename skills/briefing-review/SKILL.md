---
name: briefing-review
description: Review, search and discuss briefing content. Activates when users ask about their briefings, want a summary of what happened, or need to find something across their tracked topics.
---

# Briefing Review

Help users get the most out of their Protime briefings: summarize what matters, find specific items, and answer questions from the collected content.

## When to Activate

- «What's in my briefing?», «What happened today?», «Catch me up»
- The user wants a summary or an update on a tracked topic
- The user searches for a keyword across their briefings
- The user asks a question the briefing content can answer («What are the trends in X?»)

## Workflow

### Latest issue

1. `get_briefings` → topics, schedule, `latestIssue` per briefing.
2. One briefing → read it. Several → ask which one, or summarize all briefly.
3. `get_issue` with the `issueId` (and `briefingId`) → categories and articles with title, summary, source, URL.
4. Default to 3–5 bullets, most important first; the full breakdown on request.

### Search

1. `search_issues` with `keyword` (add `briefingId` to include an archived briefing; `maxIssues` up to 10 to go further back).
2. Present matches newest first with title, excerpt, source and date.
3. Read the full issue with `get_issue` when the user wants more.

### History

1. `get_issues` with `briefingId` or `briefingName` (fuzzy), `limit` up to 20.
2. Read selected issues with `get_issue` and compare how the topic developed.

## Principles

- Always keep the source link of an article.
- Answer from the issue content; say so when the briefings do not cover a question rather than filling the gap from memory.
- Connect items across articles and issues when it helps the user.

## Related

- `/protime:briefing`, `/protime:search`, `/protime:discover`
