# CLOS // Wheel of Fortune
**Campus Legends of Saturday — Coaching Carousel Live Show Tool**

A self-contained web app that powers the CLOS Wheel of Fortune — the live coaching carousel show run at the end of every dynasty cycle. Coaches spin for job offers by tier, tiebreakers resolve automatically on screen, and the whole thing is built to run live on stream.

---

## How It Works

Eligible coaches submit their stats through a Google Form. An Apps Script reads those submissions, calculates each coach's tier, and serves the data to this app automatically. When the wheel loads, it pulls the latest coach list and occupied schools in real time — no manual setup required.

The show runs in three phases:

- **Setup** — confirms loaded coaches and occupied schools, with manual override available
- **Show** — live spin phase with animated slot machine, tiebreaker resolution, and running assignments panel
- **Results** — full board showing every coach's complete offer package by tier

---

## Spin Order

The show is structured to build toward the T1 reveal as the main event:

| Group | Spins |
|---|---|
| T5 coaches | T5 offer only |
| T4 coaches | T5 → T4 |
| T3 coaches | T5 → T4 → T3 |
| T2 coaches | T5 → T4 → T3 → T2 |
| T1 coaches | T5 → T4 → T3 → T2 → T1 |

---

## Tier Criteria

Tiers are calculated automatically based on coach career stats:

| Tier | Criteria |
|---|---|
| **T1** | 2 NC appearances, 1 NC win, or 5 CFP wins |
| **T2** | 2 CFP wins or 3 CFP appearances |
| **T3** | 2 conf title wins, 4 winning seasons, or 1 CFP win |
| **T4** | 3 winning seasons, 1 conf title win, or 1 CFP appearance |
| **T5** | 2 winning seasons |

---

## Tiebreaker Resolution

If two coaches land on the same school, the tiebreaker fires automatically and resolves in this order:

1. Coach Prestige (letter grade)
2. Overall Win %
3. Top 25 Wins
4. Coin flip

The resolution reason is displayed clearly on screen. The losing coach receives a re-roll only if the conflict occurred at their highest eligible tier.

---

## Setup & Dependencies

**Required:**
- Google Form connected to the Form Response Sheet
- Apps Script deployed as a web app (URL baked into the HTML file)
- Team Info Sheet with coach assignments in Column C

**No build process required.** This is a single HTML file. Upload it to GitHub Pages and it's live.

---

## Files

| File | Purpose |
|---|---|
| `clos_wheel_of_fortune.html` | The wheel app — self-contained, no dependencies |
| `README.md` | This file |

---

*Campus Legends of Saturday // A MNY Community // CLOS Wheel of Fortune*
