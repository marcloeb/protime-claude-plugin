# Protime

Swiss commercial register and news briefings for Claude, by blueSky Information GmbH.

**Register.** Look up any Swiss company in the Swiss Official Gazette of Commerce (SHAB) back to 2002: registrations, mutations, deletions, bankruptcies with creditor filing deadlines. Ask who signs for a company, which audit firm checks its books, count bankruptcies across a canton, check a list of companies at once, or search building applications in 13 cantons. Every answer links its signed source document. Company-size figures are estimates and marked as such. Not an official register extract.

**Briefings.** Track any topic: Protime finds newsletters, feeds and web sources and delivers recurring AI summaries you can read, search and manage from Claude.

## Skills

| Skill | Use |
|---|---|
| `/protime:check` | Check one or more Swiss companies |
| `/protime:briefing` | Latest issue of a briefing |
| `/protime:search` | Search past briefing issues |
| `/protime:discover` | Start tracking a new topic |
| `swiss-register`, `claim-check`, `briefing-review`, `source-management`, `topic-tracking` | Load automatically when relevant |

## Connector

The plugin connects to `https://mcp.protime.ai/mcp`. On first use you sign in with your Protime account (OAuth). See `CONNECTORS.md`.

## License and service terms

The plugin files (skills, configuration) are MIT-licensed — see `LICENSE`. The Protime service they connect to is not: its use is governed by the Protime terms of service (https://protime.ai/de/terms-of-service), including usage limits beyond which a paid plan is required.

## Data use

Information about persons from the commercial register is for business purposes only. See https://registerbuch.ch/nutzungsbedingungen and https://protime.ai/de/privacy-policy.
