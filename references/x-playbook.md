# X / Twitter Playbook — Algorithm Optimization

Grounded in Twitter's open-source recommendation algorithm. Use when drafting or debugging
X posts for reach.

**Scope note for the automated routine:** the routine posts 3 standalone, scheduled posts
per run with no hashtags, no engagement bait, and no financial advice. The ranking models
and signal logic below all apply. Where this playbook suggests reply-bait CTAs ("drop it in
replies 👇", "like if you agree") or threads, those are MANUAL-only — the automated routine
uses an organic open question or lingering tension instead, never a bait CTA.

---

## The ranking models (what to optimize for)

**Real-graph** — predicts whether your followers will interact. Early follower engagement
widens distribution to non-followers. Write what your followers will actually engage with.

**SimClusters** — community detection. Your post spreads if it resonates inside a tight
community. Pick ONE clear topic per post, use the community's language and terminology,
be genuinely useful to that niche. Mixed-topic posts confuse the model.

**TwHIN** — maps you and your content to topics. Stay in your lane (markets/trading) so the
model keeps mapping you to the right audience. Consistency compounds topical authority.

**Tweepcred** — reputation/authority score. Higher-credibility accounts get more
distribution. Built through consistent quality posting and real engagement, destroyed by
engagement bait. Replying to and quoting high-credibility accounts lifts visibility (manual).

## Signals the system tracks

**Explicit (high weight):** likes, replies, retweets, quote tweets.
**Implicit:** profile visits, link clicks, dwell time, **bookmarks/saves**.
**Negative (heavy penalty):** block, report, mute, unfollow, fast scroll-past.

## What triggers each signal

| Want | Trigger |
|---|---|
| Likes | novel insight, memorable phrasing, a strong opinion backed by data |
| Replies | a real question, a genuine debate, an incomplete thought that invites completion |
| Retweets | useful info people want to share, representational value (it speaks for them), an information advantage (you had it first) |
| Bookmarks/saves | data and stats they will reference later, frameworks, how-it-works mechanics |

For this account, **replies are the highest-weight signal** — replies indicate genuine
engagement and debate. **Bookmarks and retweets are the priority** — data and mechanics that a
trader saves or shares. Likes are cheap. Strategy: encourage replies through open tension and
unresolved questions that traders want to complete in the thread.

## Markets-tuned application

- **Short posts with one number beat explainer chains (EMERGING — 3 weeks confirmed):**
  Under 150 chars with ONE specific number plus a divergent outcome outperforms longer
  posts on engagement rate. Week 3 top performers: "Dow ATH vs NFP miss" (18 imp, 38.9%
  eng), "Bitcoin ETF outflow reversal" (28 imp, 28.6% eng), "June payrolls 57K vs 110K
  consensus" (18 imp, 27.8% eng). Every one is a single number plus an immediate divergent
  outcome. Bias post length short over explainer-chain long.
- **Niche consistency (SimCluster + TwHIN):** every post is markets. Specific tickers,
  specific numbers, specific mechanics. "$SPCX IV is elevated into the options launch,
  dealers will hedge the gamma" beats "interesting moves in space stocks".
- **Specificity drives saves:** a precise stat or mechanic gets bookmarked. Vagueness gets
  scrolled past (negative signal).
- **First hour matters — critical 15–30 min window:** scheduled posts should land when the
  markets audience is active (US pre-market / open). Engagement velocity in the first
  15–30 minutes is the single biggest distribution lever. Early replies and bookmarks set
  the ceiling for total reach. A post with strong early velocity (1–2 replies in the first
  10 min, 3+ bookmarks by 15 min) unlocks wider distribution to non-followers.
- **Representational value drives retweets:** write the take a trader wishes they had
  posted. They retweet to represent their own view.
- **Strong first-line hooks:** every post opens with a specific number, clear implication, or
  observable tension in the very first line. This stops the scroll and improves early velocity.
  "XYZ is at [number], the highest since [date]" beats "interesting move in XYZ" on the first
  line.
- **Post scannability:** use short paragraphs and line breaks. Never dense text blocks. Traders
  scan — make the key number or tension visible in the first 1–2 lines so they can assess
  worth in a glance.
- **Open tension over bait:** the routine's 3rd/last post can end on a genuine unresolved
  question ("the divergence nobody has explained yet: ...", "the gap between the data they
  use and current reality remains..."). That earns replies organically. Never "agree? 👇".
- **Constructive framing wins long-term:** neutral or slightly constructive observations
  outperform overtly negative or combative takes, even when the negative take gets initial
  engagement. Tweepcred builds on consistency and constructiveness, not incendiary takes.

## Pitfalls (lose reach)

- Generic statements ("markets are volatile") — no community resonance, scrolled past
- Engagement bait ("like if you agree", "RT this") — Tweepcred damage over time
- Unclear audience — if it is not clearly for traders, the model will not push it
- Off-niche pivots — confuses TwHIN, dilutes distribution
- Over-posting in a burst — hurts per-post engagement rate (the routine staggers for this)
- Toxicity / report-bait — heavy negative-signal penalty
- Passive phrasing with no hook — "check out this data" underperforms the data itself
- Links in the main post — external links suppress distribution. Keep text standalone.

## Manual-only levers (not used by the automated routine)

- Threads (5-8 tweets, each adding info) often outperform single posts
- Replying to top accounts and quote-tweeting to build Tweepcred
- Direct reply-driving CTAs

## Bluesky (same craft, different algo)

Bluesky does not run Twitter's ranking models (it is feed/chronological-based), but the
CRAFT principles here transfer directly: stay in the markets niche, lead with the specific
number or mechanic, write save/share-worthy posts, no engagement bait. What does NOT
transfer: Tweepcred-style reputation scoring and reply-velocity ranking.

Bluesky specifics:
- **Hard 300-character limit. Count before posting, never exceed.**
- Dry, precise, slightly detached tone. Audience is fintech builders and quants.
- One specific data point per post. 1-2 hashtags max. No brand mentions.
- 5 standalone posts per run, each a complete observation.

## Reconciliation with routine rules

- **Standalone, not threads** for automated posts. **No hashtags on X. No engagement-bait
  CTAs.**
- **No financial advice or price targets.** Keep conviction and specificity, frame as
  observation and mechanism, never an explicit buy/sell/price call.
- Apply the account voice and the `social/SKILL.md` per-platform structure on top of this.
