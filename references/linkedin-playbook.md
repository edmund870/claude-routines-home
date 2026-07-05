# LinkedIn Playbook — 2026

Reach heuristics + hook formulas for LinkedIn. Sources: 360Brew paper (arXiv 2501.16450),
AuthoredUp 2026 reach data, Trust Insights Q1 2026 guide, Social Media Today on LinkedIn's
anti-pod measures.

**Scope note for the automated routine:** the routine posts ONE text post per weekday via
Zernio_2. Format-multiplier, carousel, native-video, and engagement-pod sections below are
for manual posting and the human manager. The post-craft rules (length, hook cutoff,
hashtags, close mechanics, hook micro-rules, pre-publish checklist) apply to every post,
automated or manual.

---

## Timing

| Audience | Best window (local) |
|---|---|
| US B2B / founders | Tue 8:00 AM ET, Wed 10:00 AM ET |
| EU decision-makers | Tue/Wed 7:00-8:30 AM CET |
| Global mixed | Tue/Wed/Thu 7:30-9:00 AM, audience timezone |

Avoid: Mon before 9 AM, Fri after 2 PM, Sat/Sun (30-50% reach cut for B2B).

## Format reach multipliers (relative to single image)

| Format | Multiplier |
|---|---|
| Document carousel (PDF) | 1.7-2.3x |
| Native video (<90s, captioned, vertical 9:16) | 1.4-1.8x |
| Text-only | 1.0-1.3x |
| Poll | 1.1x |
| Single image | 1.0x (baseline) |
| External link in body | 0.4-0.6x |

## Length

- Sweet spot: **900-1,300 chars** (~150-220 words)
- Hook cutoff: **first 210 chars** desktop, **~140 chars** mobile ("… see more" line).
  Write for the 140-char mobile line; the desktop window is a bonus.
- Long-form (1,500-1,900) works only with line breaks every 1-2 sentences and a narrative
  payoff
- Avoid <400 chars unless you are an established voice with punchy observations

## Hashtags

- **0 hashtags** performs equal to or better than 5+ in 2026 (360Brew uses semantic
  embeddings, not tag matching)
- **1-3 niche hashtags** (<50k posts) give marginal lift (~5%)
- **5+ hashtags** correlate with spammy-account patterns (negative signal)
- Placement: end of post, never mid-sentence

## Link placement

- **Link in first comment:** ~2.1x impressions vs in-body link
- **In-body:** suppressed 40-60%
- **Workaround phrasing:** "Source below ↓", "Dropped the piece in comments"

## Signal weights (reported, not officially confirmed)

- Save = **5x a like**, 2x a comment
- In-depth comment (paragraph-length) > one-word reaction by 4x
- Comment-to-comment threading (user↔user replies) = strong quality signal
- Dwell time sweet spot: **31-60 seconds**
- "See More" expand + fast abandon (<3s) = clickbait penalty
- First 1-2 sentences scored for topic relevance before the user scrolls

## First 60 minutes

- 60-90 min "Momentum Window" determines ~80% of total reach
- Author reply to every comment within 90 min = required to hit the ceiling
- 3+ substantive comments in the first 30 min = second testing boost

## Penalties

- Comment pods: claimed 97% detection (unconfirmed). Penalty: shadowban 3-14 days, reach
  cut 60-90%.
- TOS: "We may limit how many comments a member can make in a time period."
- Recycled reply templates on your own post: lexical-similarity detection downranks.
- Over-posting: 2+ posts/day triggers cannibalization (360Brew deprioritizes accounts
  posting 2+/day). The routine posts 1/day max for this reason.

## Native articles

- Lift is real but modest: ~1.2-1.4x vs regular text post
- Long-tail SEO via Google indexing (bonus)
- Use for evergreen/reference, not timely takes

## 2026 AuthoredUp format benchmarks (absolute engagement)

| Format | Engagement rate / reach |
|---|---|
| Multi-image (3-4 personal photos) | **6.60%** (highest of all formats) |
| Carousel (doc, 6-9 slides, <12 words/slide) | ~6x engagement, ~4x reach vs text-only |
| Poll | +206% reach vs average |
| Single image | 0.7x (now underperforms text-only by ~30%) |
| Native video (30-90s, captioned) | reach -35% YoY in 2026, still viable with strong hook |

## Native video rules (manual)

- Length 30-90s. Captions mandatory (85% watch without sound). Native upload only
  (YouTube links kill reach). Hook visually in first 3s. Vertical 9:16.

## Close mechanics

- A specific closing question ("What's your experience with X?") boosts engagement
  **20-40%** vs generic "Thoughts?"
- Name the topic inside the CTA. Generic CTAs do not trigger replies.

## Save ratio

- 200 saves ≈ **4x the reach** of 1,000 likes
- Checklists, frameworks, templates are save-bait. Optimize for save, not like.

## Engagement benchmarks by follower count

| Follower count | Expected engagement rate |
|---|---|
| 1K-5K | 4-8% |
| 5K-10K | 3-5% |
| 10K-50K | 2-4% |
| 50K+ | 1-3% |

Use to calibrate whether a post underperformed before blaming the algorithm.

## External-link penalty

- External link in body: ~60% reach reduction (move to first comment)
- Engagement-bait CTAs ("Agree? Comment below!") are now actively suppressed, not just
  ignored
- Viewer tolerance score: if users scroll past your posts without dwelling, distribution
  progressively collapses even for followers

## Edit-safety window

- Edits within the first **3 hours** trigger re-evaluation
- Restructuring >20% of text resets distribution entirely
- Typo fixes safe after the 90-min momentum window

## Post-publish engagement windows (manual)

| Phase | Window | Action |
|---|---|---|
| Warm-up | 15 min BEFORE publishing | 3-5 substantive comments on others' posts |
| Critical | First 30 min AFTER | Reply to every comment within minutes |
| Seeding | 15-30 min after | 3-5 bonus comments on your own post for thread depth |
| Visibility bump | Reply within 1st hour | +35% visibility lift |

## Pre-publish checklist

- [ ] Hook fits in first 140 chars (mobile), 210 max (desktop)
- [ ] No em dashes, en dashes, double dashes
- [ ] No AI vocabulary blacklist (leverage, fundamentally, delve, etc.)
- [ ] At least 1 specific number per 100 words
- [ ] At least 1 named entity (person, company, product)
- [ ] At least 1 first-person concrete detail
- [ ] No external links in body
- [ ] 0-2 hashtags at end
- [ ] Length 900-1,300 for medium, 1,500-1,900 for long
- [ ] Line breaks between ideas, not every sentence
- [ ] One moment of real stakes
- [ ] Close is a named-topic question or a clean landing (not "what do you think?")

---

# 10 Hook Formulas

Each formula has a skeleton, why it works, and a reference engagement number from the post
that defined it.

## F1 — Platform Risk Anaphora (ref 4,240 eng)

```
{Platform1} can {restrict|shadowban|throttle} you {timing}.
{Platform2} can {bad thing} for {reason}.
[4-5 more anaphoric lines, escalating specificity]
You don't own {audience}. You don't own {feed}. You're renting {attention}.
[Concrete horror anecdote with a real number]
Here's what most people miss: [reframe — what the real asset is].
So I changed how I work:
— [tactic 1]
— [tactic 2]
— [tactic 3]
[Metaphor close]
[Product mention as natural conclusion, one sentence, no pitch verbs]
[Personal-audit question]
```
Why: loss aversion stacked 5x, identity threat, solution list earns the close.
Note: do not use F1 to frame LinkedIn itself as inferior (algo penalty on LinkedIn).

## F2 — R.I.P. Category Obituary (ref 3,822 eng)

```
R.I.P. {category}.
Cause of death: {specific mechanism + numbers}.
[Concrete evidence, 2-3 paragraphs with dates and stats]
I defended {old thing} publicly through most of 2025.
It worked. Until [pivotal event + date].
Here's what actually changed under the hood:
1. [Change 1 with stat] ... 6. [Change 6 with stat]
The winners in 2026 aren't {old-winner-type}. They're {new-winner-type}.
[One-line philosophical close]
```
Why: status-threat + relief. Reframes "I'm behind" as "the game changed."

## F3 — Year-over-Year Pivot (ref 494 eng, 3.74x baseline)

```
In {last year}, I {humble benchmark}.
In {this year}, I'm {transformational goal}.
Here's what actually changed.
[Vulnerable truth + specific numbers]
[Identity reframe: "the shift wasn't tools, it was identity"]
[3-beat imperative close]
[Mirror question: "What's your {last}→{this} pivot? One line below."]
```
Why: two-line hook carries 80% of the weight. Mirror CTA compounds engagement.

## F4 — Time-Anchor Confession (ref 1,519+ eng)

```
{N} {days|months|years} ago, I stopped {behavior}.
Here's what happened.
[2-year backstory of why the old behavior worked: concrete numbers]
[The quiet cost]
So in {month} I stopped. [New behavior, 2-3 lines]
[Metric dropped by N%. Expected worse.]
What surprised me: [counterintuitive upside, specific wins]
[One-line reframe]
[Mirror question]
```
Why: confession earns the room. Specific numbers kill the "vibes" energy.

## F5 — Self-Proving Meta (ref 1,082 eng / 435 comments)

```
Most LinkedIn posts die in the first 30 minutes.
Not because {common reason}. Because {real reason}.
[Reveal the metric]
So here's the test. For the next 24 hours, I will {specific commitment}.
You do two things: 1. [Low-bar action] 2. [Verification action]
If the thesis is right, {outcome}. If it's wrong, I owe you a post admitting it.
```
Why: claim validated by reader action. Only use if you will actually keep the promise.

## F6 — Comment-Gate Lead Magnet (ref 717-3,008 eng)

```
[Authority number]
[Pattern observation the authority earned]
So I turned that workflow into {N named items}.
What's inside: — [Item 1] ... — [Item 12]
Free. No email wall. [Light scarcity]
Comment "{keyword}" below + connect with me and I'll send the bundle.
```
Why: capped reach, huge DM conversion. WARNING: this is engagement bait. Ship only when
the goal is list-building, not thought leadership, and at most once per month.

## F7 — Odd-Precision Money Ledger (ref 1,755 eng, 9.4x baseline)

```
{Odd, specific dollar number — "$873.47"}
[1-line context]
Here is every line item, from the ledger, nothing rounded:
- {tool 1}: $X.YZ ...
[What the total replaces]
[The thing that surprised you]
[Identity reframe close]
```
Why: non-rounded numbers signal real accounting. Screenshot-bait. Never use made-up numbers.

## F8 — Paid-vs-Free Reversal (ref 550 eng, 19.64x baseline, highest multiplier)

```
I charge {audience} $X for {service}.
Screw it. Today it's free.
Below is the exact {N-step} teardown I run before I'll take a client. It's the {NAMED-FRAMEWORK}.
1. {STEP-1-NAME} — [actionable instruction] ... 7. {STEP-7-NAME} — [actionable]
That's the {framework}. Run it today.
[Soft scarcity close]
```
Why: price→free pattern interrupt. Named framework signals proprietary thinking. Checklist
drives saves (5x likes).

## F9 — Curiosity-Gap Teaser (ref 306 eng, 4.25x baseline)

```
Yesterday, our {system} did something.
Something we didn't program it to do.
[One sensory anchor]
[Specific reveal, not a platitude]
[Reframe: what it means for the category]
[Sensory detail]
[Philosophical close ending with a question]
```
Why: incomplete line 1 + deepening line 2 = scroll-lock. Sensory anchor beats the AI-slop
detector.

## F10 — Contrarian + Historical Receipts (ref 3,083 eng)

```
{Sacred cow} has been dying since {year}.
{Month Year} — {event}. "{Death prediction.}"
[6-9 total dated entries]
Every cycle: the same obituary.
Here's the counterpunch.
[Hard stat with source] [Second stat]
What actually died wasn't {X}. It was {specific subset}.
What's thriving: {opposite subset with specifics}.
If you're still {losing behavior}, you already lost.
If you're {winning behavior}, you already won.
[Provocative question]
```
Why: receipt list is a dwell-time machine. Binary close forces side-picking.

## Signal #3 — Mechanism Reveals Beat Recaps (ACTIVE RULE — 7+ posts confirmed)

Options/macro posts that reveal a mechanism (how/why, not just what) outperform pure news
recaps **3-7x on impressions**. Confirmed across posts #1, #3, #6, #7, #12, #29, #30
(avg ~97 imp) vs recap posts #22, #27, #28 (avg ~23 imp). Reference wins: "Gamma exposure —
SPY $3.6M put loss at 740 strike, max pain $746, QQQ $2.5M puts at 700" (138 imp). "87%
gross margin on Micron HBM — $11.52B data center unit at software-grade margins" (484 imp).

**Rule:** Never post a pure recap ("Fed held rates, dot plot hawkish"). Always reveal the
mechanism causing the number, then the market implication. Recap-only posts are the single
strongest negative signal found in the data so far.

## Choosing which formula

| Topic type | Best formula |
|---|---|
| Platform/category argument | F1 Anaphora |
| Industry era ending | F2 R.I.P. / F10 Contrarian |
| Personal year recap | F3 Year-over-Year / F4 Confession |
| Product demo in public | F5 Self-Proving Meta |
| Big authority giveaway | F6 Comment-Gate / F8 Paid-vs-Free |
| Founder build-log | F7 Odd-Precision Money |
| Emergent/surprise story | F9 Curiosity-Gap |

## Hook micro-rules

- **"How I" beats "How to".** First-person experience outperforms generic instruction by
  2-3x. Swap every "How to" to "How I" unless the post is a pure framework with no narrator.
- **Specific number in the first sentence** raises expand-rate ~35%. $873.47 beats $900.
- **Real failure in the first 3 lines** outperforms polished framing by ~8.5x. Lead with
  what broke.

## Never do

- Blend two hooks in one post
- Use F5 if you won't keep the promise
- Use F6 more than once per month
- Pair F7 with made-up numbers
- Use F1 to frame LinkedIn as inferior

## Note for this account's context

This account is markets-focused, not a personal-brand creator. Confessional and
money-ledger formulas (F4, F7) rarely fit. The strongest fits for market commentary are
**F2 (category obituary), F9 (curiosity-gap on a market event), and F10 (contrarian +
historical receipts)** — all data-forward and side-picking. Never give financial advice or
price targets, even inside a hook skeleton.

---

# Post Writer Workflow

When drafting a LinkedIn post from scratch:

1. **Gather inputs.** Topic, angle, any draft ideas, audience, target length (short
   300-500 / medium 900-1,300 / long 1,500-1,900 chars).
2. **Pick the formula.** If unspecified, suggest 2-3 that fit and show each one's reference
   engagement number. For market commentary, default to F2 / F9 / F10.
3. **Draft.** Fill the skeleton in the account voice. Respect the algorithm rules: hook in
   the first ~140 chars (mobile) / 210 (desktop), 900-1,300 char sweet spot, double
   line-breaks between ideas, 0-2 hashtags at end, no external links in body.
4. **Humanizer pass.** Strip em dashes, AI vocab, rule-of-three, generic openers. Add at
   least 1 specific number, 1 named entity, and 1 first-person concrete detail per 100 words.
5. **Self-audit** against the pre-publish checklist above.
6. **Approval card.** Show: formula used, full draft, char count, suggested posting window,
   likely reactions. (Manual flow only; the automated routine schedules without approval.)
7. **On approval / automated run.** Schedule via `zernio_2:posts_create` (LinkedIn account).

## Skill-specific hard rules

- Never frame LinkedIn as inferior in a LinkedIn post (algo penalty).
- One product mention max, and only when it is the natural conclusion, never the pitch.
- Include at least one moment of real stakes. Pure insight posts do not land in 2026.
- Vary sentence length aggressively. Mix 3-word sentences with 25-word sentences.

## Anti-patterns (refuse to ship)

- All-caps first line ("THIS CHANGED EVERYTHING.")
- Em dashes, en dashes, or double dashes anywhere
- "In today's fast-paced world" style openers
- Rule-of-three lists without receipts
- "Game-changer", "deep dive", "leverage", "fundamentally"
- External links in the body
- Reused engagement-bait closers ("tag someone who needs this", "agree?")
