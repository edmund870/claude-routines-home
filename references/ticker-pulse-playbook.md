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

## Deep-Dive Format (major verified catalysts)

Use this instead of the standard structure whenever Step 3 verification turns up a catalyst with
real documented substance — **this is not limited to trials or FDA decisions.** Any of these
qualify equally: an earnings print with specific figures, an M&A/partnership/contract announcement,
an insider Form 4 or 13F institutional-holdings disclosure, an analyst note with a specific
target and stated reasoning, a debt/convertible-note raise, a buyback authorization, an executive
transition, a product or tech launch/deal. The common thread isn't the topic, it's the density: can
you fill 3-4 short paragraphs where each sentence is a fact the reader didn't already have? If yes,
use this format regardless of sector or catalyst type. If the catalyst is thin (a rating change with
no detail, a headline with nothing under it), don't force this format — fall back to the standard
structure or a shorter post.

**Provenance note, read before trusting the numbers below:** the highest-impression examples of
this shape (~800 to ~10,800 impressions in one week) were observed on this account's timeline, but
confirmed as posted manually or via a tool outside this routine — not a proven track record of this
routine's own output. Treat them as evidence of what the *audience* responds to, not evidence this
routine has already achieved it. That gap matters because of what comes next.

**This directly collides with a documented, larger-sample rule, and the reconciliation is the
format below.** `references/x-playbook.md` and `private/voice.md`, both built from 2,316 posts over
43 days on this same account, explicitly **ban take-free newswire recitation as the lowest-
performing pattern** and require every winning post to close on the account's own read. The
observed high-impression posts were pure fact relay with no synthesis anywhere in them — exactly
the shape that larger dataset flags as weakest for follows and bookmarks, even where raw impressions
spiked. Both datasets are real. The resolution: **take the density and length** (the coded
continuous dwell-time weight is real and rewards this), **but keep the synthesis** (the coded
originality gates don't cover this, but the account's own much larger sample says take-free relay is
the weakest format for anything beyond a raw impression count). A Deep-Dive post is not exempt from
having a read — it just delivers that read after the facts instead of as a punchy kicker.

**Why the length itself plausibly helps, independent of the synthesis point:** these posts run long
enough to hit X's "Show more" truncation in the feed, and (on the observed examples) Detail Expands
and URL Clicks ran far higher than on standard-format posts. A dense post that gets cut off
mid-sentence is a legitimate curiosity-gap hook — the reader taps to see the rest, which is the
dwell-time and click signal the ranker rewards. Front-load the single sharpest fact in the first
line so the post stands on its own even un-expanded, then let supporting detail run past the fold.

```
HOOK: who + what happened + the specific verified result, no wind-up
DETAIL: what was actually announced/tested/filed — the subject (drug, deal, filing, product,
        contract), the counterparty or market it touches, the specific terms
RESULT: the actual numbers or outcome — could be efficacy data, revenue/EPS, deal size, stake
        size, target price, guidance figure — whatever the catalyst's real payload is
SYNTHESIS: one line, the account's own read — what this actually means, what it implies, what's
        easy to miss in the raw numbers. Not a question, not a spicy kicker, but not absent either
        — this is the line that keeps the post from being pure wire-copy relay
FORWARD-LOOK (optional): what happens next — a regulatory filing, next earnings print, close date,
        vesting/lockup date, next 13F/Form 4 cycle — only if there's a genuine next date, don't
        invent one
```

Differences from the standard format worth naming explicitly:
- **No forced question or engagement-bait kicker — but the synthesis line is mandatory, not
  optional.** This is the one hard rule this format cannot drop. A Deep-Dive post with hook,
  detail, and result but no synthesis is a take-free newswire dump — banned, same rule as Routine A.
- **Retail sentiment is optional, often absent entirely.** This format is reporting the verified
  catalyst, not framing a retail-vs-verified divergence. Only include a sentiment line if it's
  actually the sharpest angle available (rare for this format — usually it isn't).
- **Tone drops the loose-grammar voice pillar for the hook/detail/result lines.** Straight, precise,
  newswire-register prose reads as more credible for this kind of factual density than the account's
  usual hyperdirect style. The synthesis line can still carry the account's normal voice — it's
  where the persona shows up in this format. Still no financial advice, no price targets, no
  hashtags, no em dashes — those hard rules never lift.
- **Every sentence must be new information.** This is the format most likely to accidentally pad
  ("this represents an important step forward" is filler; "they plan to file with regulators this
  quarter" is not). If a sentence could be deleted without losing a fact, delete it. The synthesis
  line is the one exception that's allowed to be interpretation rather than a fact — that's its job.
- **Longer length ceiling: up to ~1000 chars** (vs. 600 for the standard format) — see Length
  section below.

**Paragraph it.** One blank line between each present part (hook / mechanism / context / kicker),
not a single run-on block — same scannability logic as the LinkedIn/Telegram formats. A skipped
part just means fewer line breaks, never filler to fill the gap.

Two devices that work well for hook + mechanism specifically:
- **Divergence framing** — price action vs. retail sentiment moving opposite directions is often
  the sharpest available angle. The mechanic is "two things pointing opposite ways, say so
  plainly" — it is NOT a sentence template. **Never reuse a closing clause like "one of them is
  wrong" / "somebody's about to be wrong" across posts.** Each divergence post needs its own
  phrasing built from that run's actual numbers: what moved, by how much, what the crowd is still
  doing, stated in whatever words fit that specific setup. Two posts sharing the same skeleton
  read as templated to a human reader, and the algorithm has a coded duplicate-text detector
  (`BBQDuplicateTextProd.bot`, clusters posts by matching text, labels matches `COPYPASTA_SPAM`)
  that near-identical closing clauses can trip at volume.
- **"No news, just flow"** — when trending has no external catalyst, say so. A verified absence of
  news is itself a legitimate, honest hook; don't manufacture a mechanism that isn't there.

**280–500 chars target (up to the 600 cap when a Step 3.5 context line survives all four gates).**
`$TICKER` format always. Matches `references/x-playbook.md`'s updated default: the ranker's
continuous dwell-time weight rewards posts that hold attention, and this account's data shows
280–600 outperforming 150–280 on reach — length earned by substance (a real mechanism, real
numbers), never padding.

**Deep-Dive format (see above): up to ~1000 chars.** Only when the catalyst genuinely has that
much real information in it, regardless of what kind of catalyst it is, and only once the mandatory
synthesis line is included — don't hit 1000 chars of pure fact relay and skip the read. If the
facts (plus synthesis) run out at 650 chars, stop at 650.

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
> Sentiment barely moved off 74% bullish. Either the print didn't tell the crowd anything new, or
> nobody's actually looked at it yet.

(Note this is one possible phrasing of the divergence device for this specific setup, not a
template — the next divergence post needs its own words built from that day's actual numbers, see
the warning above.)

The $TEAM example's third line ("fighting Microsoft and ServiceNow on scale") is the optional
context step — competitor color, no new number, dropped in because it was actually fresh that run.
The other two skip it entirely because there was nothing real to add — fewer line breaks, not
padding to fill them.

**Deep-Dive format examples** (structure only — write your own facts from that day's actual
verified catalyst, never reuse this phrasing). The shape is identical no matter what kind of
catalyst it is:

> $XYZ and $ABC reported positive Phase 3 results from their trial, which met its primary endpoint.
>
> The trial tested the combination therapy in patients with [specific population/indication],
> against standard treatment.
>
> Patients on the combination saw a significant reduction in [the actual measured outcome] versus
> standard therapy, with safety data consistent with prior results.
>
> [SYNTHESIS] That bar has only been cleared this cleanly a handful of times in the class, which is
> why the read-through hits [related tickers/the sector], not just the two names that ran the trial.
>
> Both companies plan to file with regulators this quarter, with full data presented at an upcoming
> medical conference.

> $XYZ reported Q[N] adjusted EPS of $[X], beating consensus of $[Y] by [Z]%, while revenue rose
> [N]% year-over-year to $[amount] versus estimates of $[amount].
>
> [Specific product/segment] revenue reached a record $[amount] in the quarter, with [margin metric]
> expanding to [N]%.
>
> Management pointed to [specific driver — new contract, capacity expansion, pricing] as the main
> lever for the beat, not a one-time item.
>
> [SYNTHESIS] That's the detail worth sitting with: a beat built on [durable driver] reads
> differently than one built on [a one-time item], even when the headline number looks the same.
>
> The company guides for [specific figure] next quarter, [above/below/in line with] the current
> Street estimate of $[amount].

> $XYZ disclosed a Form 4 filing showing [insider name, title] sold [N] shares on [date] at prices
> ranging from $[low] to $[high], totaling roughly $[amount] in proceeds.
>
> The sale followed [specific recent event — a rally, a guidance raise, a lockup expiry] and
> represents [N]% of the insider's total holding per the filing.
>
> [SYNTHESIS] [Whether this reads as routine (a scheduled 10b5-1, a small fraction of the stake) or
> as a signal (first sale in N months, part of a cluster across multiple insiders) — the account's
> own read on which it is, not just the raw filing numbers].

Four to five short paragraphs, one blank line between each, no forced kicker or question, no retail
sentiment unless it's genuinely the sharpest angle, **one mandatory synthesis line** placed wherever
it reads best (often after the numbers, sometimes better placed right after the hook — judgment
call per post). Every fact-line adds something the reader didn't already have; the synthesis line
adds the account's own read on what those facts mean. This shape — applied to trial data, earnings,
insider filings, debt raises, analyst notes, deals — is what the account's highest-impression posts
of the week looked like; the synthesis line is what keeps a Deep-Dive post from being the take-free
newswire dump the account's larger dataset already proved doesn't work.

## Avoid

- Manufacturing a catalyst when there isn't one (say "no news, just flow" instead)
- Naming Stocktwits, everyticker.com, or any research tool in post text
- Treating retail sentiment % as a market-wide fact
- Using any number from everyticker.com, or using it at all past 45 days stale
- Repeating a ticker Routine A already used as its main topic today
- Generic momentum language with no specific number ("shares are moving today")
- Stretching for length with filler once the real content runs out
- Any buy/sell/hold framing, however softened
- Forcing the Deep-Dive format onto a thin catalyst just to chase length — if there aren't 3-4
  paragraphs of real new facts, use the standard format instead
- Publishing a Deep-Dive post with no synthesis line — hook/detail/result with nothing else is a
  take-free newswire dump, the exact pattern `references/x-playbook.md` and `private/voice.md`
  document as this account's lowest-performing style over its largest dataset
- Reporting a catalyst that isn't actually current — confirm the news date against today's date
  (Step 0's `get_time` call) before drafting; a real event from last week framed like it just
  happened is a factual error, not a stylistic one
