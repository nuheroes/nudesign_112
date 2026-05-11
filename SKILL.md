---
name: hansol-hclp-design-system
description: Use this skill when designing materials for Hansol Group's HCLP (Hansol Corporate Leadership Program), the AX MBA executive AI-transformation track, or anything labelled "한솔 HCLP / 임원 교육." Covers slide decks, training guides, schedule timelines, and program announcements in Korean and English. Embodies an atmospheric glass-morphic look — soft pastel blue→mint background, brand greens #1a7a50 / #2db88a, Pretendard typography, frosted-glass cards, restrained executive tone.
---

# Hansol HCLP Design System

## Quick start
1. Link `colors_and_type.css` — gives you every token + Pretendard webfont.
2. Wrap your slide root in `<div class="bg-gradient"></div>` to get the signature atmospheric background.
3. Use glass cards (`rgba(255,255,255,.65)` + `backdrop-filter: blur(14px)` + 1 px white border) on every floating element.
4. Use the brand 135° gradient `linear-gradient(135deg, #1a7a50, #2db88a)` only on icon chips, dots, accent rules, and the progress bar.

## When to apply
- ✅ Hansol HCLP / 임원 교육 / 임원 워크숍 decks (Korean primary)
- ✅ AX MBA curriculum docs, run-of-show, schedule pages
- ✅ Internal announcements within the program
- ❌ Hansol consumer products, marketing sites — use a different brand system
- ❌ Anything that needs semantic red/yellow/orange — this palette is greens-only

## Read first
- `README.md` for content fundamentals, visual foundations, iconography, and caveats.
- `reference/hclp_presentation.html` is the canonical source. Match its rhythm.
- `slides/` for 4 ready-made 16:9 templates (Title / Index / Content / End).

## Don'ts
- No flat or dark backgrounds. The atmospheric pastel gradient is mandatory.
- No solid white cards — always glass.
- No purple, blue, red, or warm-grey accents. Only the green ramp.
- No emoji. No italics. No exclamation points.
- Don't let English headlines outrank Korean ones.

## Asking the user
When the user requests an HCLP artifact, ask:
1. **Audience tier** — 임원 only, or 임원 + 본부장 / 팀장 level (changes the formality dial slightly)
2. **Format** — 16:9 deck / print guide / web announcement
3. **Section count** — drives whether you reach for the Index template or skip it
4. **Logo** — do they have an official Hansol logo asset to drop in, or use the `:Hansol` typographic stand-in
5. **Length** — 5–6 slides (overview) or 15+ (full curriculum)
