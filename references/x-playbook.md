# X / Twitter Playbook — Algorithm Optimization

Grounded in the open-source **xai-org/x-algorithm** 13–14 Aug 2026 drop (`param.rs`,
`visibility-filtering/`, `phoenix/` training code — the first release to publish actual scoring
weights) plus 8 weeks of this account's own analytics (OpticAlpha, 2,316 posts over 43 days). Use
when drafting or debugging X posts for reach.

**Scope note for the automated routine:** each run posts **1 standalone post**, and **every 4th
run posts ONE connected thread (2–4 tweets)** chained via Buffer. No hashtags, no engagement-bait
CTAs, no financial advice. Most posts carry an **attached chart/card image**. The mechanics below
apply to every post. Where this playbook mentions reply-driving CTAs ("drop it in replies 👇",
"like if you agree"), those are MANUAL-only — the routine uses an organic question or a declarative
kicker instead of a bait CTA.

---

## The ranking spine (2026)

**Ranker = Phoenix**, a Grok-based transformer. It reads the user's engagement-history sequence and
predicts, per candidate post, probabilities/values across a 64-slot discrete action taxonomy plus
continuous dwell-time regression heads (`phoenix/README.md:257-274`). Your post's score is:

`Final Score = Σ( weight_i × predicted_i )`

Out-of-network reach runs through three sources: **Phoenix Retrieval** (two-tower embedding
similarity), **SimClusters** (live, seeded from viewer favorites — not obsolete, see below), and
TweetMixer (currently disabled). The 2023 hand-engineered features (Real-graph, TwHIN, Tweepcred)
are gone. SimClusters is not one of them — it ships in this drop as an active retrieval source
alongside Phoenix (`home-mixer/sources/simclusters_source.rs`).

**Positive signals** (push content UP): favorite, reply, repost, quote, click, video_view,
photo_expand, share (incl. via DM, via copy-link), follow_author, **continuous dwell time**.

**Negative signals** (push content DOWN): not_interested, block, mute, report, not-dwelled.

**profile_click is currently weighted 0.0.** It is tracked but contributes nothing to the score —
do not optimize for it. `follow_author` (4.0) is the real growth signal.

### Published weights (`home-mixer/params/param.rs:308-474`)

| Signal | Weight | vs. a like |
|---|---|---|
| **share via copy link** | **20.0** | **40×** |
| reply | 5.0 | 10× |
| quote | 5.0 | 10× |
| share via DM | 5.0 | 10× |
| follow author | 4.0 | 8× |
| share (generic) | 2.0 | 4× |
| repost | 1.0 | 2× |
| favorite | 0.5 | 1× |
| click | 0.4 | — |
| open link | +0.2 | — |
| photo expand / video open / VQV | 0.05 | — |
| **continuous dwell time** | **0.004 × predicted seconds** | see below |
| profile click | 0.0 | dead |
| dwell (binary "did they dwell") | 0.0 | dead |
| not interested | −43.2 | |
| block author | −31.2 | |
| mute author | −58.8 | |
| report | −234.0 | |
| not dwelled | −0.02 | |

Out-of-network posts (and, separately, in-network replies/reposts) get their final score
multiplied by **0.75**.

**Two rules for reading this table, both critical, both easy to misapply:**

1. **Every row except dwell multiplies a predicted probability, not a raw count.** A report weight
   of −234 does not mean "1 report cancels 468 likes" — the baseline probability of a report is
   >1000× lower than a like, so the weight is large precisely to let a rare, high-signal action
   move the score at all. This is stated explicitly in the code (`param.rs:279-307`) as a
   correction to a common misreading. Never do arithmetic on these numbers against engagement
   counts.
2. **Dwell time is the one exception — it multiplies seconds, not a probability.** The binary
   "did they dwell" weight is 0.0 (dead). The live channel is `ContDwellTimeWeight = 0.004`,
   applied to a *predicted dwell duration in seconds* (trained as `dwell-time-mae` over raw
   seconds, served as `predicted_dwell_sec` with no denormalization). Every other positive weight
   scales a value in the 0.001–0.05 range; dwell scales a value in the 0–30 range. At a predicted
   10s dwell the term alone (0.04) already exceeds most other single terms. **Dwell time is
   plausibly the largest positive contributor to the score for a post that holds attention** — this
   is inference from the units involved, not a published ranking, since the code doesn't publish
   baseline predicted rates.

## Original Content Rewards Program (from Sept 2026)

Replaces Revenue Sharing. Payout is on **qualified impressions**: unique views from Premium
subscribers on the Home Timeline, ≥50% of post visible, replies excluded. This is narrower than
total reach — the OON/retrieval reach mechanics below still drive growth and eligibility (needs
500+ verified followers, 500k+ verified Home Timeline impressions/90 days), but raw impression
counts in analytics will not track payout $ 1:1. Track the program's own eligibility counter
(Creator Studio → Original Content Rewards) rather than estimating from total impressions.

Growing **follow_author** (weight 4.0, currently near-zero for this account) now does double duty:
it's both a real ranking signal and a hard eligibility gate (500 verified followers).

## Reach is out-of-network

Distribution to non-followers runs through **Phoenix Retrieval** — a two-tower embedding
similarity search — plus **SimClusters**, which is seeded from the viewer's recent favorites and
queries an ANN over cluster embeddings independently of Phoenix. Your post gets an embedding; it
surfaces to users whose recent engagement embeds nearby. This account is **96.5% non-followers**,
so nearly all reach is OON — retrieval, not your follower graph, decides who sees you.

- **Discovery = your post's embedding matching what the target community (markets) engaged with.**
  This demands **ruthless topical consistency** — and it is now a coded gate, not just an
  embedding-drift argument: to be eligible for a topic's out-of-network index, **at least 50% of
  your last 15 original/quote posts must be in that category**
  (`phoenix-rankall-strato/lib/eventProcessing.strato:459-585`). Off-topic content isn't
  "diluted" — it embeds somewhere no market audience lives, and can fall outside the topic index
  entirely.
- **Retrieval index unlocks in two tiers: 1 favorite, then 32 favorites.** A brand-new post is not
  eligible for out-of-network retrieval until it earns its first like; the wider `32fav` index tier
  is a second, harder unlock. Re-indexing re-fires on **power-of-two like counts** (1, 2, 4, 8, 16,
  32…) with a 1-minute floor between updates, inside a 48-hour window
  (`phoenix-rankall-strato/columns/phoenix_rank_all/phoenixRankAllCandidateProcessor.strato:46-101`).
  **Replies and reposts are never indexed for out-of-network retrieval at all** — only originals
  and quotes are eligible.
- **Author diversity is a decaying multiplier, not a binary cap:** `(1−0.25)·0.5^k + 0.25` for the
  k-th post by the same author already in a viewer's slate — 1.0, 0.625, 0.437, 0.344, … down to a
  0.25 floor. Your 2nd post in one feed already loses 37.5% of its score.
  Burst-posting cannibalizes your own reach → **stagger posts, ~90 min minimum spacing.**
- **Hard 48-hour age cutoff** on every candidate — recency still matters, but there's no soft decay
  curve to game, just a wall.
- **`DedupConversationFilter` keeps only the single highest-scoring post per conversation in a
  given feed** — not "one branch". A whole thread collapses to whichever one tweet in it scored
  best for that viewer. Design threads as a single clean linear chain (each tweet replying to the
  previous), both because branching wastes structure the filter will discard anyway and because a
  linear chain is what earns dwell (see Threads below).

## What triggers each signal

| Want | Trigger |
|---|---|
| share via copy-link (heaviest weight, 40× a like) | content worth sending to one specific person — a stat, a table, a framework they'll actually use |
| favorite | novel insight, memorable phrasing, a strong opinion backed by data |
| reply | a real question, a genuine debate, an incomplete thought that invites completion |
| repost / quote | useful info people want to share, representational value (it speaks for them), an information edge (you had it first) |
| photo_expand | an attached chart/terminal card worth tapping into |
| **dwell (predicted seconds — the largest live weight)** | a post dense enough to hold the eye: layered numbers, a mechanism worth reading twice, a thread |
| follow_author (the real growth signal — profile_click is weighted 0.0) | a take compelling enough that they want more from you (currently our biggest gap) |

### Writing for copy-link share specifically (the single heaviest weight, 40× a like)

Copy-link share and retweet are not the same trigger, even though both look like "sharing" from
the outside. **Retweet is public endorsement** — the trigger is "I want my followers to see this
reflects on me." **Copy-link/DM share is private utility** — the trigger is "this specific thing
applies to a specific person I know." Writing for the two pulls in different directions: a hot
take optimizes for retweet, a resolved argument or a reusable reference optimizes for copy-link.

What actually gets forwarded to one person instead of broadcast to a timeline:

- **Content that settles an argument.** A post that resolves a live disagreement gets sent to
  whoever's on the other side of it. Data stated flatly, no hedge, works better here than a take.
- **A self-contained payload.** A number, table, or framework complete enough to forward alone,
  with no context needed from the sender. Half-finished takes don't get shared because the sender
  would have to explain them.
- **Reference value over reaction value.** A framework or dated calendar someone bookmarks to send
  next time it's relevant beats a hot reaction to today's move. This is the same untested lever
  flagged above under follows/bookmarks — frameworks, historical tables, dated calendars — copy-link
  share and follow_author plausibly respond to the same content type, since both are "keep this"
  behaviors, unlike retweet's "broadcast this."
- **Specificity that maps to a specific person's situation.** "If you're holding $XYZ into
  earnings" reads as forward-bait because the reader immediately thinks of who that applies to.

Hook shapes that lean into this instead of a generic take:
- "The [mechanism] explanation for why [X] happened, in one line:" — self-contained, answer-shaped
- A numbered framework or short table people screenshot-forward
- "Bookmark this for next [earnings/FOMC/OPEX]" — explicit reference framing
- Settling a live disagreement with a number, stated flat, no hedge

---

## Threads: hybrid policy — a dwell play, not a reach multiplier

Threads are no longer manual-only. **Every 4th routine run posts ONE connected thread (2–4 tweets)**
chained via Buffer; the other runs post a single standalone.

- **Why keep them:** dwell time is real and heavily weighted (0.004 × predicted seconds — plausibly
  the largest single positive term). A thread that holds attention across several tweets is a
  legitimate way to earn a large dwell prediction.
- **What they do NOT do:** a thread does not multiply your reach. `DedupConversationFilter` collapses
  the entire thread to **one slot** in any given viewer's feed — whichever tweet in it scores best.
  And tweets 2+ are replies: replies are **never** indexed for out-of-network retrieval, are
  hard-dropped from OON candidates entirely, take the same ×0.75 discount as any in-network reply,
  and are ineligible for both the mutual-follow boost and the new-author cold-start boost. **Treat a
  thread as a dwell play that costs the same one slot as a standalone** — not a way to get more
  slots.
- **Tweet 1 must stand alone.** Since it is the only tweet in the thread eligible for out-of-network
  retrieval and every boost, it has to work as a complete, retrieval-competitive post on its own —
  hook, not throat-clearing.
- **Build them linear:** each tweet replies to the previous one. No side-replies, no branching — a
  branching structure only feeds candidates that `DedupConversationFilter` was always going to
  discard down to one anyway.

## Media, links, and video

**Attach a chart/terminal-card image to most posts** (via Buffer media). The account's own data
shows posts **with** an image card get **79 vs 18 avg impressions (~4.5x more reach)**, consistent
with the photo_expand positive signal.

- **There is no ranking penalty for bare external links.** `open_link` carries a small *positive*
  weight (+0.2), and no code path downranks a post for containing a URL. What a bare link
  genuinely costs you: the URL text itself is stripped before your post is embedded for retrieval
  (`t.co` links are removed pre-embedding), so **a link with no card contributes zero semantic
  signal** to where your post gets placed for discovery. A rendered link **card** (title,
  description, thumbnail) *does* get embedded — attach a card, don't rely on the bare URL.
- The real link risk is off-ranking: a URL whose redirect chain resolves to a `LOW_QUALITY` or
  `BAD` verdict can get the whole post labeled spam, and a link plus @-mentioning a stranger who
  doesn't follow you is a specifically modeled spam pattern. Only link to sources you trust; never
  chain-mention non-followers alongside a link.
- **Video needs to clear 10 seconds** to earn any video-quality-view credit or to enter the
  immersive video retrieval index — under 10s earns nothing extra over a static image. GIFs do not
  qualify for the video index either way. video_view is a predicted positive signal and we post
  none — worth testing (short chart animations, screen-capture walkthroughs), but keep it above the
  10s floor.

## Data-backed format rules

*(from 2,316 posts over 43 days, reconciled against the dwell-time weight above)*

- **Length — bias LONGER, 280–600 chars is now the default target, 600 hard cap stays.** The
  account's own data already shows this band gets the best reach (~75 vs ~29 impressions for
  150–280), and the published dwell weight explains why: more substantive text means more time
  spent reading, which is now the single largest live positive term. There is no length feature in
  the ranker itself — length only matters through (a) dwell seconds and (b) giving the embedding
  model enough text to place your post accurately in topic space. That means the floor matters as
  much as the target: a post too thin to be topically legible (e.g. "$META longs!") produces an
  ambiguous embedding and gets nothing extra from being short. **Padding does not help** — a
  skimmed-past post trips the `NotDwelled` penalty (−0.02 × P(not dwelled), a real negative term),
  so length must be substance (a real mechanism, real numbers), not filler.
- **Paragraph it.** One blank line between the hook, the mechanism/numbers, and the kicker. A wall
  of text at 280–600 chars gets skimmed, not read — paragraphing is what turns length into actual
  dwell time instead of a bounce.
- **Hashtags: banned** — data-backed. 7 vs 35 avg impressions, 0.9% vs 4.5% ER. No hashtag boost
  exists in the ranker at all; the only hashtag-related code path is an abuse ceiling
  (`SpamHashTagAbuse`).
- **Questions: a deliberate engagement-farm lever — not every post, not banned.** Question-closes
  get lower reach (24 vs 32 imp) but farm replies, which are the growth engine. So:
  - **Reach-oriented posts** end on a **declarative one-line kicker**.
  - **Engagement-farm posts** end on a **question**. Rotate between the two.
- **Cashtags:** shown, but lower ER (1.9% vs 5.2%) in our data. No cashtag-specific handling exists
  anywhere in the ranker — but cashtag text is not stripped before embedding, so `$TICKER` text
  does function as topic vocabulary that helps place the post in retrieval. Use where genuinely
  relevant, as topic signal, not as a reach hack.
- **Reach days:** Thursday & Friday over-index. Mon/Wed weakest. Weekend ER higher, reach flat.
- **Winning format:** "Why X:" lead → 2–3 specific numbers → one-line skeptical kicker. Use a
  contrast device ("Same news. Opposite read."). **BAN take-free newswire recitation** — pure stat
  dumps with no read were the low performers.
- **Follows ≈ zero, bookmarks are unweighted — stop optimizing for bookmarks.** (27 follows + 22
  bookmarks across 43 days, mostly earned by replies under large accounts, not originals.) Bookmark
  count is a model *input feature* but carries **no weight anywhere in `param.rs`** — it is not a
  ranking signal. The actual gap to close is `follow_author` (weight 4.0): write posts compelling
  enough to earn a follow, and keep a strong bio/positioning so a profile visit converts (even
  though the profile-click step itself is weighted 0.0, the follow that might follow it is worth
  4.0). Testing whether reference content (frameworks, historical tables, dated calendars) earns
  follows on originals remains unexplored — prioritize this test.

## Engagement-farm rotation (operator-directed)

Blend these with the analytical core — they supplement it, they don't replace it. Rotate levers so
no single tactic saturates:

- **(a)** End-of-post question / rhetorical prompt.
- **(b)** "Why is the market red/green" obvious-take posts.
- **(c)** Trigger-a-group takes ("index funds suck" / "individual stocks suck") — **spicy, not
  toxic.** block/mute/report are negative signals; a take that gets you reported costs more than it
  earns. **Note:** `SpamEngagementBaiting` and `SpamEngagementFarming` are the *only* two spam
  policy types that apply regardless of account standing — there is no high-reputation exemption
  for them. Levers (a) and (c) sit closest to that line; keep them clearly organic, not formulaic
  bait phrasing.
- **(d)** Motivational posts.
- **(e)** Famous-investor quotes (Buffett etc.) — **never post the quote bare.** Under the Original
  Content Rewards Program (replaces Revenue Sharing from Sept 2026), a post's value must come
  primarily from what we add. Pair every quote with a specific market-mechanic tie-in (a number,
  positioning, trade implication) — the quote becomes supporting material, not the payload. A quote
  + generic caption reads as insufficiently transformed.

## Craft that still holds

- **Niche consistency:** every post is markets. Specific tickers, numbers, mechanics. "$SPCX IV is
  elevated into the options launch, dealers will hedge the gamma" beats "interesting moves in space
  stocks". Now enforced by a coded topical-consistency gate (≥50% of last 15 original/quote posts),
  not TwHIN — same conclusion, harder edge, and a measurable threshold to stay above.
- **First hour matters:** land when the markets audience is active (US pre-market / open). Early
  likes are what push a post through the 1-fav and 32-fav retrieval unlocks before the 48-hour
  window closes.
- **Strong first-line hooks:** open with a specific number, clear implication, or observable tension
  in the first line. "XYZ is at [number], the highest since [date]" beats "interesting move in XYZ".
- **Scannability within a longer post:** short paragraphs and line breaks, even at 280–600 chars.
  Make the key number visible in the first 1–2 lines so a scanning trader can assess worth at a
  glance, then let the paragraphed body carry the dwell time.
- **Constructive framing wins long-term:** neutral or slightly constructive observations outperform
  combative takes over time; incendiary posts risk block/mute/report.

## Pitfalls (lose reach)

- Off-topic / off-niche content — falls outside the 50%-of-last-15 topical gate, effectively
  invisible to that topic's out-of-network index.
- Hashtags — data-backed reach and ER killer; no offsetting boost exists.
- Bare external links with no card — no retrieval lift (URL text is stripped pre-embedding);
  attach a card instead.
- Take-free newswire stat dumps — lowest performers, and thin enough to trip the not-dwelled
  penalty.
- Short, thin posts written to "bias short" — actively works against the dominant dwell-time
  weight and against embedding legibility. There is no length-based ranking bonus for being short.
- Burst-posting — author diversity multiplier decays fast (0.625 by your 2nd post in one slate);
  stagger ~90 min.
- Toxicity / report-bait — direct negative signals (block/mute/report), and engagement-bait framing
  specifically has no reputation exemption.
- Branching threads — `DedupConversationFilter` keeps only the single best post per conversation
  regardless of branch structure; keep it linear so tweet 1 carries the thread on its own.
- Passive phrasing with no hook — "check out this data" underperforms the data itself.

## Manual-only levers (not used by the automated routine)

- Replying to and quote-tweeting high-reach accounts (earns clicks/replies on their surface).
- Direct reply-driving CTAs.

## Bluesky (same craft, different algo)

Bluesky does not run Phoenix (it is feed/chronological-based), but the CRAFT principles transfer:
stay in the markets niche, lead with the specific number or mechanic, write save/share-worthy posts,
no hashtags-as-bait. What does NOT transfer: Phoenix/SimClusters retrieval reach and the
positive/negative signal weighting.

Bluesky specifics:
- **Hard 300-character limit. Count before posting, never exceed.**
- Dry, precise, slightly detached tone. Audience is fintech builders and quants.
- One specific data point per post. No brand mentions.
- 5 standalone posts per run, each a complete observation.

## Reconciliation with routine rules

- **Hybrid posting:** 1 standalone per run; every 4th run posts one linear 2–4 tweet thread, framed
  as a dwell play on a single slot, not a reach multiplier.
- **Length:** 280–600 chars target (raised from the old 150–280 default), 600 hard cap, paragraphed
  into hook / mechanism / kicker.
- **Media allowed and encouraged:** attach a chart/card image to most posts (~4.5x reach in our data).
- **No hashtags on X. No engagement-bait CTAs** (the farm levers above use organic questions, not "agree? 👇").
- **No financial advice or price targets.** Keep conviction and specificity; frame as observation and
  mechanism, never an explicit buy/sell/price call.
- Apply the account voice and the `social/SKILL.md` per-platform structure on top of this.
