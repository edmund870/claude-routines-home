# X / Twitter Playbook — Algorithm Optimization

Grounded in the open-source **xai-org/x-algorithm** rewrite (May 2026) plus 8 weeks of this
account's own analytics (OpticAlpha, 2,316 posts over 43 days). Use when drafting or debugging
X posts for reach.

**Scope note for the automated routine:** each run posts **1 standalone post**, and **every 4th
run posts ONE connected thread (2–4 tweets)** chained via Buffer. No hashtags, no engagement-bait
CTAs, no financial advice. Most posts carry an **attached chart/card image**. The mechanics below
apply to every post. Where this playbook mentions reply-driving CTAs ("drop it in replies 👇",
"like if you agree"), those are MANUAL-only — the routine uses an organic question or a declarative
kicker instead of a bait CTA.

---

## The ranking spine (2026)

The 2023 stack (Real-graph, SimClusters, TwHIN, Tweepcred) is **obsolete**. The May 2026 rewrite
eliminated all hand-engineered features — do not optimize for those models, they no longer exist.

**Ranker = Phoenix**, a Grok-based transformer. It reads the user's engagement-history sequence and
predicts probabilities for 15 candidate actions. Your post's score is:

`Final Score = Σ( weight_i × P(action_i) )`

**Positive signals** (push content UP): favorite, reply, repost, quote, click, profile_click,
video_view, photo_expand, share, **dwell** (time spent on the post), follow_author.

**Negative signals** (push content DOWN): not_interested, block, mute, report.

**On weights:** xAI does **not** publish weight values for the current Phoenix ranker. Optimize for
signal *direction* — which signals fire and whether they're positive or negative — never for
specific multipliers. Third-party figures floating around ("replies 27x", "report 369x", "velocity
1000x") trace back to the **2023 heavy-ranker** release, a real but now-obsolete system — treat them
as historically directional at best, not current Phoenix weights, and never cite as fact.

## Original Content Rewards Program (from Sept 2026)

Replaces Revenue Sharing. Payout is on **qualified impressions**: unique views from Premium
subscribers on the Home Timeline, ≥50% of post visible, replies excluded. This is narrower than
total reach — the OON/retrieval reach mechanics below still drive growth and eligibility (needs
500+ verified followers, 500k+ verified Home Timeline impressions/90 days), but raw impression
counts in analytics will not track payout $ 1:1. Track the program's own eligibility counter
(Creator Studio → Original Content Rewards) rather than estimating from total impressions.

Growing the **follow_author** gap (see below — currently near-zero) now does double duty: it's
both the biggest untapped ranking signal and a hard eligibility gate (500 verified followers).

## Reach is out-of-network

Distribution to non-followers runs through **Phoenix Retrieval**, a two-tower embedding
similarity search. Your post gets an embedding; it surfaces to users whose recent engagement
embeds nearby. This account is **96.5% non-followers**, so nearly all reach is OON — retrieval,
not your follower graph, decides who sees you.

- **Discovery = your post's embedding matching what the target community (markets) engaged with.**
  This demands **ruthless topical consistency**. Off-topic content is not "diluted" — it embeds
  somewhere no market audience lives, so it is effectively **invisible**.
- **Author Diversity Scorer** attenuates repeated appearances from the same author in a feed.
  Burst-posting cannibalizes your own reach → **stagger posts, ~90 min minimum spacing**.
- **AgeFilter** — recency still matters. Post into your audience's active window.
- **DedupConversationFilter** shows only ONE branch of a conversation. Design threads as a single
  clean linear chain (each tweet replying to the previous), not a branching tree.

## What triggers each signal

| Want | Trigger |
|---|---|
| favorite | novel insight, memorable phrasing, a strong opinion backed by data |
| reply | a real question, a genuine debate, an incomplete thought that invites completion |
| repost / quote | useful info people want to share, representational value (it speaks for them), an information edge (you had it first) |
| photo_expand | an attached chart/terminal card worth tapping into |
| dwell | a post that holds the eye — a thread, a layered read, a number that makes them stop and think |
| profile_click / follow_author | a take compelling enough that they want more from you (currently our biggest gap) |

---

## Threads: hybrid policy

Threads are no longer manual-only. **Every 4th routine run posts ONE connected thread (2–4 tweets)**
chained via Buffer; the other runs post a single standalone.

- **Why:** threads earn **dwell** (a positive signal) by holding attention across tweets, and drive
  bookmarks/shares of reference content.
- **Cost:** threads sacrifice initial reach (the first tweet must carry retrieval on its own). So
  treat threads as a **rotation lever for dwell/bookmarks**, not the default posture for a
  reach-starved account.
- **Build them linear:** each tweet replies to the previous one (DedupConversationFilter shows only
  one branch). No side-replies, no branching.

## Media, not links

**Attach a chart/terminal-card image to most posts** (via Buffer media). This is a reversal of the
old "links suppress distribution" rule — the account's own data shows posts **with** an image card
get **79 vs 18 avg impressions (~4.5x more reach)**, consistent with the photo_expand positive
signal.

- Prefer **attached media** over bare external outbound URLs. A raw link with no media still adds
  nothing to retrieval — attach a card instead.
- **Video is an untapped lever** — video_view is a predicted positive signal and we post none.
  Worth testing (short chart animations, screen-capture walkthroughs).

## Data-backed format rules

*(from 2,316 posts over 43 days)*

- **Hashtags: banned** — now data-backed. 7 vs 35 avg impressions, 0.9% vs 4.5% ER. They hurt reach.
- **Questions: a deliberate engagement-farm lever — not every post, not banned.** Question-closes
  get lower reach (24 vs 32 imp) but farm replies, which are the growth engine. So:
  - **Reach-oriented posts** end on a **declarative one-line kicker**.
  - **Engagement-farm posts** end on a **question**. Rotate between the two.
- **Length** (bias short for ER; go long only when a mechanism needs it *and* media is attached):
  - `<100 chars` → ~50 imp
  - `100–150` → ~24 imp but **highest ER (12.7%)**
  - `150–280` (89% of posts) → ~29 imp
  - `280–600` → ~75 imp (best reach, lowest ER — works **only** with a chart/link attached)
  - **600 hard cap** stays.
- **Cashtags:** shown, but lower ER (1.9% vs 5.2%). Use where genuinely relevant; not as a reach hack.
- **Reach days:** Thursday & Friday over-index. Mon/Wed weakest. Weekend ER higher, reach flat.
- **Winning format:** "Why X:" lead → 2–3 specific numbers → one-line skeptical kicker. Use a
  contrast device ("Same news. Opposite read."). **BAN take-free newswire recitation** — pure stat
  dumps with no read were the low performers.
- **Follows + bookmarks ≈ zero** (27 follows + 22 bookmarks across 43 days, mostly earned by replies
  under large accounts, not originals). This is the explicit gap to close: write posts compelling
  enough to earn a **profile_click / follow_author**, and keep a strong bio/positioning so the click
  converts. Testing whether reference content (frameworks, historical tables, dated calendars) earns
  saves on originals remains unexplored — prioritize this test.

## Engagement-farm rotation (operator-directed)

Blend these with the analytical core — they supplement it, they don't replace it. Rotate levers so
no single tactic saturates:

- **(a)** End-of-post question / rhetorical prompt.
- **(b)** "Why is the market red/green" obvious-take posts.
- **(c)** Trigger-a-group takes ("index funds suck" / "individual stocks suck") — **spicy, not
  toxic.** block/mute/report are negative signals; a take that gets you reported costs more than it
  earns.
- **(d)** Motivational posts.
- **(e)** Famous-investor quotes (Buffett etc.) — **never post the quote bare.** Under the Original
  Content Rewards Program (replaces Revenue Sharing from Sept 2026), a post's value must come
  primarily from what we add. Pair every quote with a specific market-mechanic tie-in (a number,
  positioning, trade implication) — the quote becomes supporting material, not the payload. A quote
  + generic caption reads as insufficiently transformed.

## Craft that still holds

- **Niche consistency:** every post is markets. Specific tickers, numbers, mechanics. "$SPCX IV is
  elevated into the options launch, dealers will hedge the gamma" beats "interesting moves in space
  stocks". (Now enforced by retrieval, not TwHIN — same conclusion, harder edge.)
- **First hour matters:** land when the markets audience is active (US pre-market / open). Early
  engagement velocity feeds AgeFilter and seeds retrieval.
- **Strong first-line hooks:** open with a specific number, clear implication, or observable tension
  in the first line. "XYZ is at [number], the highest since [date]" beats "interesting move in XYZ".
- **Scannability:** short paragraphs and line breaks. Make the key number visible in the first 1–2
  lines so a scanning trader can assess worth at a glance (helps dwell without a wall of text).
- **Constructive framing wins long-term:** neutral or slightly constructive observations outperform
  combative takes over time; incendiary posts risk block/mute/report.

## Pitfalls (lose reach)

- Off-topic / off-niche content — embeds away from the markets community, effectively invisible.
- Hashtags — data-backed reach and ER killer.
- Bare external links with no media — no retrieval lift; attach a card instead.
- Take-free newswire stat dumps — lowest performers.
- Burst-posting — Author Diversity Scorer attenuates you; stagger ~90 min.
- Toxicity / report-bait — direct negative signals (block/mute/report).
- Branching threads — DedupConversationFilter hides all but one branch; keep it linear.
- Passive phrasing with no hook — "check out this data" underperforms the data itself.

## Manual-only levers (not used by the automated routine)

- Replying to and quote-tweeting high-reach accounts (earns clicks/replies on their surface).
- Direct reply-driving CTAs.

## Bluesky (same craft, different algo)

Bluesky does not run Phoenix (it is feed/chronological-based), but the CRAFT principles transfer:
stay in the markets niche, lead with the specific number or mechanic, write save/share-worthy posts,
no hashtags-as-bait. What does NOT transfer: Phoenix retrieval/embedding reach and the
positive/negative signal weighting.

Bluesky specifics:
- **Hard 300-character limit. Count before posting, never exceed.**
- Dry, precise, slightly detached tone. Audience is fintech builders and quants.
- One specific data point per post. No brand mentions.
- 5 standalone posts per run, each a complete observation.

## Reconciliation with routine rules

- **Hybrid posting:** 1 standalone per run; every 4th run posts one linear 2–4 tweet thread.
- **Media allowed and encouraged:** attach a chart/card image to most posts (~4.5x reach in our data).
- **No hashtags on X. No engagement-bait CTAs** (the farm levers above use organic questions, not "agree? 👇").
- **No financial advice or price targets.** Keep conviction and specificity; frame as observation and
  mechanism, never an explicit buy/sell/price call.
- Apply the account voice and the `social/SKILL.md` per-platform structure on top of this.
