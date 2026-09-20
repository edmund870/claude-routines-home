# Pinterest Playbook — 2026

Pin title/description sizing, board SEO, and image requirements. Posted via Buffer
(`channelId` `6aaf878dea19ca0bde93b997`, board "OpticAlpha" `boardServiceId`
`1082904741591713128`).

**Scope note for the automated routine:** posted via Buffer, 1 pin per run, reusing Step 2's
rendered terminal pane image directly (same asset as the Bluesky post that run) — no
separate portrait render step. Aspect ratio is not gated on; post as-is.

## Pin Title

| Rule | Guideline |
|---|---|
| Length | Up to 100 chars; first 40 visible in feeds |
| Keyword | Primary keyword in the first 40 chars |
| Business name | In the first sentence → 54% higher email signup conversion |

## Pin Description

| Rule | Guideline |
|---|---|
| Length | 220-232 chars optimal |
| Keywords | Main keyword + 2-3 related, natural placement (not stuffed) |
| CTA | Clear, actionable → 70% signup boost, 6% sales lift |
| Price | State it when relevant → 28% sales increase |

Set via Buffer: `text` (the post's description) and `metadata.pinterest.title` (the pin
title, separate field). Keep them distinct — title is the short headline, description is
the 220-232 char body with the CTA.

## Destination link

Every pin should carry `metadata.pinterest.url` (shows as "Website" in Pinterest's edit UI)
set to **`https://opticalpha.net/pinterest`** — a pin with no destination link is a dead
end; Pinterest is a discovery-to-click platform, the link is how it converts. Set it at
creation (`create_post`), not after — Buffer's API does not allow editing a post once it has
been published (`editPost` is not in its `allowedActions` post-publish, confirmed via a
403 "Access denied"). Fix it in Pinterest's own UI directly if a pin ships without it.

## Board SEO

- Board name and description are ranking factors — Pinterest's search/recommendation engine
  reads them, not just pin-level text.
- The **first save** to a board shapes how Pinterest categorizes the whole board going
  forward — pin something clearly on-topic first, not a stray test image.
- Use keywords in both the board title and its description, same sizing logic as pin
  keywords (primary term first, natural language, not a keyword dump).

## Post via Buffer

```
Buffer:create_post
  channelId: "6aaf878dea19ca0bde93b997"
  text: "{220-232 char description with CTA, business name early}"
  assets: [{ image: { url: "{portrait image URL}", metadata: { altText: "..." } } }]
  metadata: { pinterest: { boardServiceId: "1082904741591713128", title: "{pin title, ≤100 chars, keyword in first 40}", url: "https://opticalpha.net/pinterest" } }
  dueAt: "{ISO 8601 UTC}"
  mode: "customScheduled"
  schedulingType: "automatic"
```

## Pre-publish checklist

- [ ] Title ≤100 chars, primary keyword in the first 40.
- [ ] Business name ("OpticAlpha") appears in the first sentence of the description.
- [ ] Description 220-232 chars, main keyword + 2-3 related, natural placement.
- [ ] Clear CTA in the description.
- [ ] Price/number stated when the pin's claim has one.
- [ ] Board name/description still on-topic for what's being pinned.
- [ ] `metadata.pinterest.url` set to `https://opticalpha.net/pinterest` at creation (can't be added after the pin publishes).
