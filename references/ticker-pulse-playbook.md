# Ticker Pulse — Voice & Writing Rules

X-only companion to `references/x-playbook.md`. Same account voice as `private/voice.md`, applied
to single-ticker, trending-driven posts. Read before drafting any Ticker Pulse post.

---

## What this routine is for

Not a trending-list bot. Every post pairs a trending signal (sourced from Stocktwits, an internal
research tool never named in post text) with a **web-verified catalyst** and a **trader's read**.
If a post would still be true and complete with the ticker symbol removed, it's not doing its job —
the ticker plus the specific mechanism is the whole point.

## Hard rules (non-negotiable)

- **No financial advice, no price targets.** Same as every OpticAlpha post. Observation and
  mechanism only: "dealers short gamma into this, moves amplify" — yes. "Buy calls here" — no.
- **No em dashes.** Comma, colon, period, or restructure.
- **No hashtags.**
- **Never name the research source in post text.** Stocktwits (or any tool) is internal-only —
  refer to retail signal generically: "the crowd," "retail sentiment," "chatter," never "Stocktwits
  shows..." or similar.
- **Retail sentiment/volume is chatter, not fact.** Always frame it as what it is: "retail
  sentiment sitting at 78% bullish" not "the market is bullish." Never blend a sentiment number
  into a sentence as if it were the verified catalyst.
- **Never quote a source message verbatim.** Read top posts for color and direction of the
  argument, not for lines to lift.
- **Fact-check every hard number** (price, % move, EPS, guidance) against 2+ independent sources.
  Trending-tool price data is fine for the "what," never for the "why."
- **everyticker.com is an untrusted auxiliary source** (full constraints in
  `references/price-sources.md`) — four gates before any of it is usable: (1) discard if
  `article_date` >45 days old, (2) discard any claim that overlaps the same subject as today's
  verified catalyst — a qualitative "moat" claim goes stale exactly as fast as a number when a
  legal/regulatory/competitive event flips it, the date alone won't catch that, (3) one independent
  confirming search for whatever claim survives, never used as-is, (4) never, ever a numeric field
  from it (price, P/E, EV, growth %, margins) — that's Step 3's job only. Confirmed live failure:
  served TEAM a 3-month-stale $85/share with a negative P/E days after the real print put it at
  ~$150 with positive GAAP EPS.
- **One ticker per day.** Check `tickers_covered_today` in the Ticker Pulse Daily State page
  before committing to an angle.
- **No bare "trending" recitation.** "$XYZ is trending, up 8%" with nothing else is a take-free
  newswire post — banned, same as Routine A's rule.

## Structure

```
HOOK: the ticker + the specific verified number/catalyst, no wind-up
MECHANISM: why it's actually moving — the real catalyst, or the retail-vs-verified divergence
CONTEXT (optional): one line of competitive/positioning color, only if freshly sourced (see below)
KICKER: declarative skeptical read (default) OR a genuine question (engagement-farm lever only)
```

This runs longer than a bare X hook-kicker — the context line is what earns the extra length, not
padding. Skip it entirely rather than stretch for length with nothing real to add.

**Paragraph it.** One blank line between each present part (hook / mechanism / context / kicker),
not a single run-on block — same scannability logic as the LinkedIn/Telegram formats. A skipped
part just means fewer line breaks, never filler to fill the gap.

Two devices that work well for hook + mechanism specifically:
- **Divergence framing** — price action vs. retail sentiment moving opposite directions is often
  the sharpest available angle: "$XYZ down 4% on the print. Crowd's still 70% bullish. One of them
  is wrong." This is honest, specific, and needs no invented drama.
- **"No news, just flow"** — when trending has no external catalyst, say so. A verified absence of
  news is itself a legitimate, honest hook; don't manufacture a mechanism that isn't there.

**280–500 chars target, 600 hard cap.** `$TICKER` format always.

## Voice (same 4 pillars as `private/voice.md`, condensed for this format)

1. **Hyperdirect, loose grammar intentional.** Dropped contractions, "u" for you, sometimes a
   fragment. Not cleaned up on purpose.
2. **Zoom macro to micro.** A single ticker post can still gesture at the wider mechanism (sector
   flow, a macro tie-in) in one line without turning into a market-wide post.
3. **Say the uncomfortable read.** If the trending reason is dumb (pure momentum, no fundamental
   change), say that. Skeptical, not cynical.
4. **Genuine curiosity when farming replies** — real open questions ("is this the top or is this
   just getting started"), not rhetorical bait.

## Engagement-farm rotation

Same rotation as `references/x-playbook.md` — end-of-post question, contrarian/spicy take (not
toxic), divergence framing, dry observation. Don't repeat the same lever twice in a row, and don't
duplicate whatever lever Routine A's most recent post used (check the last sent post's closing
line if convenient — not mandatory, just avoid an obvious back-to-back repeat).

## Examples (illustrative structure, not verbatim reusable copy)

> $TEAM +35% Friday.
>
> Q4 revenue $1.77B, up 28%. Cloud growth accelerated to 31%, FY27 guide landed above consensus
> too.
>
> Been fighting Microsoft and ServiceNow on scale for years, this is the quarter the AI-migration
> story actually showed up in the numbers.
>
> Gaps this size don't resolve in one day, the real test is whether it holds through next week or
> fades.

> $ABC trending, no news found anywhere.
>
> Just flow. Sometimes that's the whole story.

> $DEF down 6% on the print.
>
> Crowd's still sitting 74% bullish. Somebody's about to be right and somebody's about to be
> wrong.

The $TEAM example's third line ("fighting Microsoft and ServiceNow on scale") is the optional
context step — competitor color, no new number, dropped in because it was actually fresh that run.
The other two skip it entirely because there was nothing real to add — fewer line breaks, not
padding to fill them.

## Avoid

- Manufacturing a catalyst when there isn't one (say "no news, just flow" instead)
- Naming Stocktwits, everyticker.com, or any research tool in post text
- Treating retail sentiment % as a market-wide fact
- Using any number from everyticker.com, or using it at all past 45 days stale
- Repeating a ticker Routine A already used as its main topic today
- Generic momentum language with no specific number ("shares are moving today")
- Stretching for length with filler once the real content runs out
- Any buy/sell/hold framing, however softened
