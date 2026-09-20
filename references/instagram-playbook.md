# Instagram Playbook — 2026

Caption hook formulas, hashtag sizing, and ranking heuristics for Instagram. Sourced from
the `instagram-skills` plugin bundle (hook-formulas.md, hashtag-strategy.md,
algorithm-heuristics.md, voice-rules.md), adapted to this account.

**Scope note for the automated routine:** the routine posts at most ONE single-image feed
post per day via Zernio, at a randomized slot, reusing that day's already-rendered terminal
pane (see box instructions Step 4 → Instagram section). It never posts carousels, Reels, or
Stories. IG1-IG4 (caption-first formulas) are what the routine actually uses. IG5-IG10
(carousel and Reel formulas) are kept here for reference only, in case a human ever manually
posts a carousel or Reel from this account — the automated routine does not use them.

---

## Timing

| Audience | Best window (local) |
|---|---|
| US creators / consumers | weekdays 11 AM-1 PM and 7-9 PM, plus Sun evening |
| B2B / trading audience | Tue-Thu mid-morning and lunch |
| Global mixed | post when your specific audience is online (check insights) |

Consistency beats raw frequency: 3-5 high-quality posts a week outperforms a daily dump of
filler. This account posts at most 1/day (often fewer) for exactly this reason, and the slot
is randomized day to day rather than fixed — see the box instructions for why (automation
detection).

## Signal weights (relative reach impact, reported)

| Signal | Relative weight | Note |
|---|---|---|
| **Send / share** (DM to a friend, or reshare to story) | highest positive | "sends per reach" is the metric Instagram leans on hardest in 2026 |
| **Save** | high | "I will come back to this" — drives reach for how-tos, lists, frameworks |
| **Comment** (esp. with author reply back) | high | real conversation is a strong quality signal |
| **Profile visit then follow** | high | the growth signal |
| **Like** | low | cheap affirmation, light reach |
| **Negative** (not interested, unfollow, hide, report) | heavy penalty | one report outweighs many likes |

Before posting: would a viewer send this to one specific friend, or save it to use later? If
it only earns a passive like, sharpen it.

## Reach suppressors (avoid)

- Engagement bait ("comment YES", "tag 3 friends", "double tap if") — explicitly downranked.
- All-hashtag captions (20-30 tags crammed at the top) — reads as spam, no reach benefit.
- Posting on an obviously rigid/frequent automated schedule — triggers automation detection
  ("Instagram blocked your request").
- Identical caption/hashtag blocks repeated across posts — reads as automated behavior.

## Hashtag sizing (3-5, not 30)

| Tier | Post count | Role | How many |
|---|---|---|---|
| **Niche** | under 50k | where a small/mid account can actually rank for hours | 2-3 |
| **Mid** | 50k-500k | sweet spot: real audience, beatable competition | 1-2 |
| **Broad** | 500k-5M+ | brief touch of a big audience, minutes not hours | 0-1 |

2-3 niche + 1-2 mid + at most 1 broad = 3-5 total. Match every tag to the actual content —
an off-topic broad tag mistrains Instagram's recommendation engine and lowers reach. Place
the set in `platformSpecificData.firstComment` (keeps the caption clean; reach is the same
as end-of-caption). **Rotate the set per post** — an identical 5-tag block posted every time
reads as automated behavior. Examples for this account's niche: `#optionsflow`,
`#0dtetrading`, `#gammaexposure` (niche); `#optionstrading`, `#macrotrading`,
`#daytrading` (mid); `#trading`, `#stockmarket` (broad, use at most one).

## Caption hook formulas

Caption hook = the first ~125 characters, before Instagram's "more" fold. It has to earn the
tap on its own; everything after is for a reader already hooked.

### IG1 — Number-First Result (goal: saves)
```
{Specific number result} in {timeframe}.

Here is the exact thing that changed.
```
A hard, odd-precision number (47 minutes, not "fast") in the first 125 chars stops the
scroll and promises a repeatable method — the most-saved caption shape. Never invent the
number.

### IG2 — Contrarian Truth (goal: shares)
```
{Common belief in the space} is wrong.

{What actually works, stated flatly.}
```
A screenshot-ready opinion gets sent to friends and reshared to stories. Only ship claims
you would defend in the comments.

### IG3 — Relatable Cold-Open (goal: comments)
```
{One specific line dropping the reader into a feeling the audience knows.}
```
Recognition is instant; specific beats generic. This is the most-copied genre on Instagram,
so the specificity is the whole job.

### IG4 — Mini-Story / Mechanism Confession (goal: comments and follows)
```
{Time marker or setup}: {what happened, including the part everyone gets wrong}.

{The one line of meaning that makes it worth the read.}
```
Transparency and a real mechanism reveal out-pull polish and out-pull a pure news recap.

*(IG5-IG10 — Listicle Carousel, Before/After Carousel, Myth-Buster Carousel, Steal-This
Framework Carousel, Pattern-Interrupt Reel, How-I Reel Teardown — are carousel/Reel formulas.
Reference only; the automated routine does not post carousels or Reels.)*

## Hook micro-rules

- First 125 chars carry the caption. Everything after the fold is for a reader already
  hooked.
- "How I" beats "How to" — first-person results carry proof.
- One specific number in the hook raises saves and shares. "47 minutes" beats "fast".
- Lead with the mechanism/reframe, not a bare news recap — a pure recap is the weakest
  performing shape.

## Voice rules (on top of this account's own — see box instructions Writing Rules)

1. Em dashes capped at ~1 per 100 words (1-2 per caption); use a comma, colon, parentheses,
   `..`, or a line break instead of stacking more.
2. Specific numbers beat adjectives: "$873 saved" beats "saved money".
3. One idea per caption — a caption arguing three points reads as a blog post.
4. Don't hard-sell OpticAlpha; Instagram buries overtly promotional captions.
5. Line breaks are punctuation — white space controls pacing, a wall of text gets scrolled
   past.
6. 0-3 emoji, placed with intent, never sprinkled.
7. Close on a landing line, not a dead "what do you think?" — a specific save/share reason
   ("save this before OPEX Friday") beats a generic question.

## Pre-publish checklist

- [ ] First 125 chars stop the scroll on their own.
- [ ] Em dashes at or under ~1 per 100 words; no en dashes or double dashes.
- [ ] No AI vocabulary cluster (leverage, fundamentally, delve, foster, etc.).
- [ ] At least one odd-precision number with a named referent.
- [ ] 3-5 sized hashtags (2-3 niche + 1-2 mid + ≤1 broad) in `firstComment`, not the caption.
- [ ] Hashtag set is not a repeat of the last post's set.
- [ ] 0-3 emoji, placed with intent.
- [ ] Media supplied (mandatory — Instagram rejects text-only posts) and within the 4:5 to
      1.91:1 aspect range.
- [ ] Close is a landing or a specific save/send ask, not "what do you think?".
- [ ] No engagement bait ("comment YES", "tag a friend", "double tap if").
- [ ] Caption and hashtags are a fresh rewrite this run, not copy-pasted from another
      platform's post for the same story.

## Post writer workflow (automated routine)

1. Reuse Step 2's pane/story for the day — no separate research for Instagram.
2. Pick the caption formula from IG1-IG4 based on the story (number-led result → IG1;
   contrarian/mechanism take → IG2; relatable moment → IG3; mechanism confession/reveal →
   IG4).
3. Draft the caption in this account's voice (box instructions Writing Rules + the Voice
   rules above). Front-load the hook into the first 125 chars.
4. Build the 3-5 sized hashtag set, rotated from the last post's set.
5. Self-audit against the pre-publish checklist above.
6. Publish via `zernio:posts_create_post` (see box instructions Step 4 code block) with the
   pane image and the hashtag set in `platformSpecificData.firstComment`.

## Never do

- Post more than once per day, or on a fixed/predictable slot.
- Repeat the same hashtag set or caption shape back to back.
- Stuff 20-30 hashtags at the top of the caption.
- Bait engagement ("comment YES", "double tap if..").
- Post text-only (Instagram's API rejects it — media is mandatory).
- Give financial advice or price targets, even inside a hook skeleton.
