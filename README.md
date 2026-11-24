# AI Website Prompt Checklist

A free pre-flight and review checklist for building a website with an AI tool: v0, Lovable, Bolt, Cursor, Windsurf, Claude, ChatGPT, Gemini, Replit, GitHub Copilot, Framer AI, Google Stitch, Readdy, Aura.build or OpenAI Codex.

This is not a pack of finished page prompts. It is the list of facts, constraints and checks that usually decide whether the first draft is usable, or a generic layout with invented proof.

> **Disclosure:** this repo is maintained by people who work on VibUI, a paid website prompt library. Everything in this repo is free to use under CC0 (public domain). The paid library is mentioned once, in [Other resources](#other-resources).

**Short answer:** before you prompt an AI website builder, fill in a fact sheet, attach constraints that forbid invented proof and accessibility failures, then review the draft on a phone and a keyboard. Use a starting catalogue only if you will reuse the same kinds of sections; the checklists still work if you never open one. This applies in v0, Lovable, Bolt, Cursor, Windsurf, Claude, ChatGPT, Gemini, Replit, GitHub Copilot, Framer AI, Google Stitch, Readdy, Aura.build and OpenAI Codex.

## Contents

- [How to use this repo](#how-to-use-this-repo)
- [1. Fact sheet (fill this in before you prompt)](#1-fact-sheet-fill-this-in-before-you-prompt)
- [2. Reusable constraint blocks](#2-reusable-constraint-blocks)
- [3. Page-type checklists](#3-page-type-checklists)
  - [Marketing or launch landing page](#marketing-or-launch-landing-page)
  - [Demo-day or pitch site (non-designer founder)](#demo-day-or-pitch-site-non-designer-founder)
  - [Local service or brochure site](#local-service-or-brochure-site)
  - [Personal portfolio](#personal-portfolio)
  - [Creator or product page](#creator-or-product-page)
- [4. Starter prompt skeleton](#4-starter-prompt-skeleton)
- [5. After-generation review](#5-after-generation-review)
- [6. Where to paste the prompt](#6-where-to-paste-the-prompt)
- [Other resources](#other-resources)
- [FAQ](#faq)
- [License](#license)

## How to use this repo

1. Copy the [fact sheet](#1-fact-sheet-fill-this-in-before-you-prompt) into a document and fill every row you can. Leave the rest marked `[PLACEHOLDER]`.
2. Tick the [page-type checklist](#3-page-type-checklists) that matches the job.
3. Paste the [constraint blocks](#2-reusable-constraint-blocks) you need under your brief.
4. Drop facts, page type and constraints into the [starter skeleton](#4-starter-prompt-skeleton).
5. Generate once, then run the [review checklist](#5-after-generation-review) on a phone and a keyboard before you share the URL.

If a fact is missing, do not let the model invent it. A blank placeholder is cheaper than a claim you have to walk back.

## 1. Fact sheet (fill this in before you prompt)

| Fact | Your notes |
|---|---|
| Product, person or business name | |
| One-line description in plain language | |
| Audience (who it is for, and who it is not for) | |
| The one primary action, and the real URL, tel: or mailto: it must use | |
| Secondary action, if any (do not invent a second one) | |
| Visual tokens: background, text, accent, type, radius â€” or "no brand yet, keep it calm" | |
| Pages or sections, in order | |
| Copy you already have (headline, bio, prices, hours, syllabus, FAQ) | |
| Proof you have permission to use (quotes, logos, screenshots, clips) | |
| Facts you will stand behind (prices, dates, names, metrics) | |
| Facts that must not appear (traction you have not earned, reviews you do not have) | |
| Hosting or repo the draft must fit into, if any | |
| Deadline, and who will review the draft | |

Print this, or keep it as `facts.md` next to the project. The prompt is only as good as this sheet.

## 2. Reusable constraint blocks

Append the blocks you need. Delete the ones that do not apply. Keep the wording tight; models follow short, testable rules better than "make it professional."

### No invented claims

```text
COPY AND PROOF RULES
- Use only facts from my fact sheet.
- Anything I have not provided must appear as [PLACEHOLDER], including names, dates, prices, metrics, quotes and logos.
- Do not invent testimonials, ratings, customer counts, "years in business," press logos, awards, or outcome numbers.
- Do not add a limited-time discount, a countdown, or a "as seen in" bar unless I supplied it.
- Do not use "unlimited" or "guaranteed" unless those words are in the fact sheet.
```

### Accessibility

```text
ACCESSIBILITY RULES
- One h1 per page. Headings follow a logical order (h2 then h3). Do not skip levels for visual size.
- Body text and buttons at least 4.5:1 contrast against their background; large headings at least 3:1.
- Every form control has a visible <label> bound with for/id. Do not use placeholder as the only label.
- Errors are text, not colour alone, and are linked to the field (aria-describedby).
- Interactive elements are real links or buttons, reachable by keyboard, with a visible focus state.
- Do not set outline: none unless you provide a clearer focus replacement.
- Informative images use alt text I provide in [ALT] placeholders. Decorative images use alt="".
- Landmarks: header, main, footer, and a "Skip to main content" link as the first focusable element.
- Set lang on the html element. Link text describes the destination; no "click here."
```

### Motion and video

```text
MOTION RULES
- Respect prefers-reduced-motion and provide a static fallback for any animation or background motion.
- No autoplaying video with sound. A preview video, if any, is click-to-play and muted by default.
- Do not add a carousel that auto-advances. If a carousel exists, previous/next controls are keyboard accessible.
- Do not generate a cinematic hero of a product, venue or team I have not supplied as a still or a clip.
```

### Forms and primary actions

```text
ACTION RULES
- The primary button label and destination must match the fact sheet. Do not invent a checkout, a trial, or a Calendly link.
- Forms post only to a destination I provide. If I have not provided one, render the form as a clearly labelled [PLACEHOLDER] and say so in a comment.
- Tap targets are easy to hit on a 360px-wide screen.
```

### Quality and structure

```text
QUALITY RULES
- Semantic HTML. Mobile first; check the layout at 360px width.
- Do not add libraries, analytics, chat widgets or cookie pop-ups I did not ask for.
- Do not invent a blog, a shop, or extra pages outside the section list.
```

## 3. Page-type checklists

Tick these after the fact sheet is filled, then mention any gaps in the prompt as placeholders.

### Marketing or launch landing page

- [ ] Headline names the audience and the offer in words you would say out loud.
- [ ] One primary action, with a real destination.
- [ ] Sections are listed in order (hero, proof only if real, how it works, pricing if you have it, FAQ, footer).
- [ ] Pricing, if present, uses your real plan names and numbers, aligned row by row.
- [ ] No invented social proof, download counts or "typical results."

### Demo-day or pitch site (non-designer founder)

This is for a founder who has a deadline (a demo day, a pitch, a cohort showcase) and does not have a designer on call. The page's job is to let a visitor understand the product in one minute and take the one action you will actually follow up on. It is not a substitute for the deck, and it will not invent traction.

- [ ] One-line product description a stranger can repeat.
- [ ] Who it is for, and who it is not for.
- [ ] A real demo: a click-to-play clip you can record this week, or 2â€“3 screenshots you already have. No generated "product UI" that is not the product.
- [ ] The ask is specific: join a waitlist, book a conversation, or open the deck at a URL you control.
- [ ] Team names and roles are real, or omitted.
- [ ] Metrics appear only if you would say them on stage. If you would not, use `[PLACEHOLDER]` or leave them out.
- [ ] Contact or follow-up path still works the day after the event.

The personal value here is time you can count, not a promised funding outcome. If a designer quote would have pushed the page past the event, fill in that quote and the hours you actually have this week, and decide whether a brief-plus-review is enough to ship a clear, honest page. This checklist will not invent a saving for you.

### Local service or brochure site

- [ ] Name, trade, area, and a tap-to-call or email path that works on a phone.
- [ ] Hours, service list, and prices only if the owner wants them public.
- [ ] Photos are theirs, or clearly marked placeholders. No stock handshakes.
- [ ] Reviews are real or omitted.
- [ ] Scope stays at a brochure site (no shop or custom booking engine unless that is a separate, agreed job).

### Personal portfolio

- [ ] One sentence: who you are and what you want (a role, a kind of client, a kind of work).
- [ ] Three projects, not ten, each with your role and a fact you can stand behind.
- [ ] Contact is a real email or form destination.
- [ ] No skill-percentage bars, no typing animation, no invented case-study metrics.

### Creator or product page

- [ ] Offer, inclusions, price, and refund rule are visible without opening an accordion.
- [ ] Preview is a real clip or still from your work.
- [ ] Proof is permissioned, or omitted.
- [ ] Buy button goes to a checkout you operate.
- [ ] Motion, if any, has a reduced-motion fallback and is not the point of the page.

## 4. Starter prompt skeleton

```text
Build a mobile-first site as semantic HTML and CSS (no framework unless I ask).

NAME: [from fact sheet]
ONE-LINE JOB: [from fact sheet]
AUDIENCE: [from fact sheet]
PRIMARY ACTION: [LABEL] linking to [URL]

VISUAL SYSTEM: [tokens, or "calm off-white background, near-black text, one accent, readable sans-serif"]

SECTIONS IN ORDER:
[paste the section list]

FACTS I WILL STAND BEHIND:
[paste the fact sheet rows]

COPY I HAVE NOT SUPPLIED must appear as [PLACEHOLDER].

[paste constraint blocks: no invented claims, accessibility, motion, actions, quality]
```

Rewrite the brackets; keep the structure. If the page is unusual (a changelog, a lab notebook, a table-first tool), write the section list yourself and skip any page-type checklist that does not fit.

## 5. After-generation review

Run this on the draft before a client, an investor, or your audience sees it.

- [ ] Every `[PLACEHOLDER]` is either filled with a real fact or removed, not published as decorative Latin or invented copy.
- [ ] The primary button works, on a phone, and goes where you said it would.
- [ ] No testimonials, logos, metrics or dates appeared that were not on the fact sheet.
- [ ] Heading order, skip link, form labels, and focus states survive a keyboard-only pass.
- [ ] Contrast holds on the real background, including text on images.
- [ ] `prefers-reduced-motion` stops background motion; no video autoplays with sound.
- [ ] Images have width/height and alt text you accept.
- [ ] The page is readable at 360px width; tap targets are usable.
- [ ] Footer contact details match the fact sheet.
- [ ] You would be willing to stand next to this URL and answer questions about every sentence.

When you need a change, ask for one fact at a time ("Replace the date with 4 December. Do not change the section order."). A request like "make it more premium" is how fake urgency and invented proof creep back in.

## 6. Where to paste the prompt

| Tool | Notes |
|---|---|
| v0, Lovable, Bolt, Replit | Paste as the first message of a new project; hosted preview included. |
| Cursor, Windsurf, GitHub Copilot, OpenAI Codex | Paste into agent chat and name the target file or folder. |
| Claude, ChatGPT, Gemini | Add "as a single HTML file" if you want an in-chat preview you can save. |
| Framer AI, Google Stitch, Readdy, Aura.build | Paste the fact sheet, section list and constraint blocks, then nudge type and spacing visually. |

The tool does not replace the fact sheet or the review. It only produces a draft.

## Other resources

- Keep a private `prompts.md` of briefs that already worked for you. A short personal file beats a large catalogue you have not read.
- If you want more copy-paste starting prompts for common page types, see a separate free starter kit only if you already have one you trust. This repo is the checklist; it is meant to sit on top of any brief.
- If you want a larger commercial catalogue of starting briefs, [VibUI](https://vibui.dev) has 2,852 website prompt templates: 775 full pages, 1,100 sections, 817 components and 160 animated backgrounds, with about 1,000 also including source code. Yearly and lifetime plans also include 2,407 AI video prompts. Pricing is one-time with no auto-renewal: $48 quarterly, $99 yearly, $179 lifetime (shown as reduced from $384). There are 60 free samples, and a free account can copy 2 prompts, which is enough to run one brief through this checklist before you decide to pay. Skip it if the fact sheet and skeleton above already cover the page you need.

## FAQ

**Can I use this commercially?**
Yes. It is CC0. No attribution needed.

**Why not just say "build a modern landing page"?**
That prompt leaves the model free to invent sections, proof and a visual system. The checklist exists to stop those inventions before the first draft.

**Will this raise sign-ups, funding or freelance income?**
It will not honestly promise that. It can help you ship a clearer page, with claims you can defend, in the time you actually have. Outcomes still depend on the offer, the audience and the work you do after the page is live.

**Which page-type checklist should a demo-day founder start with?**
Use [Demo-day or pitch site](#demo-day-or-pitch-site-non-designer-founder), then the review list. Borrow pricing or FAQ ticks from the marketing checklist only if those facts are real.

**Can I contribute?**
Yes. Open a pull request that adds a checklist row, a constraint block, or a page type, and that does not introduce invented example metrics.

## License

[CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/). Use, modify and share without restriction.
