# CLOS // Advance Tool
**Campus Legends of Saturday — Advance Day Post Generator**

A self-contained web app that handles everything needed on advance day — from the weekly advance post to the Game of the Week article, GOTW graphic prompt, and Top 25 poll. Built to be fast, repeatable, and consistent every single week.

---

## What It Does

The Advance Tool has three main modules that work together to produce every piece of content needed when a new week drops:

**01 — Advance Post**
Generates a ready-to-copy Claude request for the weekly advance post. Automatically pulls the current week, season, and week type from the sticky bar at the top and builds a tone-appropriate prompt — a kickoff week post reads completely differently from a National Championship advance.

**02 — Game of the Week**
Fill in both teams' details — coach names, records, rankings, recent results, key players, and narrative context — and the tool builds a full Claude request for a long-form immersive GOTW article formatted for Discord. Also generates a separate image prompt request that instructs Claude to look up the correct stadiums and mascots before producing a Gemini-ready vintage poster image prompt.

**03 — Top 25 Rankings**
Takes screenshots from the in-game Top 25 poll and turns them into a formatted Discord post automatically. Includes a built-in Claude primer to extract the rankings from your screenshots, then auto-calculates movement (risers, fallers, new entries, dropped out), pulls Discord handles from the Team Info Sheet, and formats the full post ready to copy and paste.

---

## How the Roster Sync Works

On load, the tool fetches coach and Discord data directly from the Team Info Sheet via an Apps Script web app. This powers the Top 25 Discord handle tagging — when a team appears in the rankings, the tool automatically appends their coach's Discord username to the line. No manual lookup required.

If the Sheet changes (new coaches, carousel moves), hit **↻ Refresh from Sheet** in the roster panel to pull the latest.

---

## Sticky Bar

The fixed bar at the top controls three global settings that feed into every module:

| Field | Purpose |
|---|---|
| **Week** | Current week number |
| **Season** | Current season number |
| **Week Type** | Determines tone guidance sent to Claude |

Set these first before generating anything. The week type selection (Week 0 through National Championship) automatically adjusts the tone of every Claude request generated — early season posts feel different from late season pressure cooker posts.

---

## Workflow

1. Set Week, Season, and Week Type in the sticky bar
2. **Advance Post** — click Build, copy the request, paste into Claude, paste the response back
3. **GOTW** — fill in both teams, click Build, copy the request, paste into Claude, paste the article back. Optionally generate the image prompt request for the GOTW graphic
4. **Top 25** — paste the Claude primer into Claude chat, upload your three screenshots, paste the returned list into the rankings field, hit Generate

---

## Files

| File | Purpose |
|---|---|
| `clos_advance_tool.html` | The advance tool — self-contained, no dependencies |
| `README.md` | This file |

---

## Dependencies

None beyond Google Fonts. The Apps Script URL for roster sync is baked into the file. No build process, no packages — just open and use.

---

*Campus Legends of Saturday // A MNY Community // CLOS Advance Tool*
