# Hansol HCLP Design System

A soft, modern, glass-morphic identity for **Hansol Group** corporate-leadership communications — built around the *HCLP (Hansol Corporate Leadership Program) AX MBA Track* presentation language.

## Index

- `colors_and_type.css` — design tokens (CSS variables) + base type styles. Import this and you are 90% there.
- `fonts/PretendardVariable.ttf` — brand sans (variable, 100–900). User-supplied.
- `preview/` — small specimen cards used by the Design System tab.
- `slides/` — sample 16:9 slide templates (Title / Index / Content / End). `slides/index.html` is a contact-sheet of all four.
- `reference/hclp_presentation.html` — the original source presentation this system was reverse-engineered from.
- `SKILL.md` — Claude-compatible skill descriptor.

## Sources

The system was derived from a single attached source: a 6-slide HCLP onboarding deck (`reference/hclp_presentation.html`) for Hansol's executive AI-transformation track. The user supplied **Pretendard Variable** as the brand font. No official Hansol brand kit (logo SVG, illustration set) was attached — see *Caveats*.

---

## Content fundamentals

**Voice.** Calm, executive, future-confident. Treats the reader as a peer-leader choosing a direction, not a student being instructed. Sentences are short, declarative, Korean-first.

**Casing.** Korean body uses normal sentence case. English fragments — eyebrows, tags, "Thank you" — are **UPPERCASE with wide letter-spacing**. Title-case English (e.g. "Research Agent") only inside tag pills.

**Pronoun / address.** No first or second person — the program speaks about itself in the abstract ("임원이 직접 경험하는…"). Address the *role* (임원, 팀, 한솔), not the individual.

**No emoji. No exclamation points.** Tone is restrained. Numbers ("01", "02") are used decoratively as oversized faded numerals rather than as bullets.

**Mixed scripts.** Korean and English coexist comfortably — Korean for the heart, English for taxonomy ("Research Agent · Writing Agent · Decision Agent · Process Agent"). Keep English in tag pills or eyebrows; never let an English headline outrank a Korean one.

**Concrete examples (lifted from the source):**
- Eyebrow → `Section 01`
- Title → `교육 개요 및 방향성`
- Subtitle → `AI 시대, 임원이 직접 경험하는 전환의 언어`
- Bullets → `· 시장 동향·경쟁사 정보를 자동 수집` `· 보고서 초안을 AI가 구조화하여 제공`
- Closing → `Thank you / AI와 함께, 더 빠른 한솔을 만들겠습니다.`

The closing breaks on a brand-tinted phrase (`더 빠른 한솔` in green `#1a7a50`). That move — Korean prose with one short phrase tinted in brand green — is *the* signature copy/visual gesture. Use it sparingly, once per deck.

---

## Visual foundations

**Background.** Always atmospheric, never flat. The exact recipe:
```
radial(70% 60% at 20% 10%, rgba(180,210,230,.55) → transparent 60%)   /* cool blue, top-left  */
radial(60% 70% at 85% 85%, rgba(100,185,150,.50) → transparent 55%)   /* mint, bottom-right    */
linear-gradient(135deg, #dce8f0 0% → #eef5f0 45% → #c8e8d4 100%)
```
Two corner glows over a diagonal pastel gradient — soft, oxygenated, faintly pharmaceutical. **Do not** swap for a flat or dark background; the system is calibrated against it.

**Color.** A single green walking through five stops: `#0f4a30 → #1a7a50 → #2db88a → #8fd8b8 → #c8e8d4`. The 700/500 pair (`#1a7a50` + `#2db88a`) appears as a **135° gradient** on icon chips, timeline dots, accent rules, and the progress bar. Ink is `#0f2830` with three transparency steps (.65 / .50 / .35). No other hues — no purples, no warm greys, no semantic red/yellow/blue. For "danger" or "info" use weight or position, not color.

**Type.** Pretendard Variable. Display sizes use **tight letter-spacing (`-0.02em`)** and weight **700**. Body is **300 (Light)** with relaxed line-height (1.6–1.7). Eyebrows are **11–14 px / 700 / 0.14em / UPPERCASE / brand-green**. No italics.

**Spacing.** A 4-px grid: 4, 8, 12, 16, 20, 24, 32, 40, 48, 64. Cards breathe — 24–36 px internal padding; 14–22 px gap between cards in a grid.

**Card surfaces.** All cards are **glass**: `rgba(255,255,255, .62 / .65 / .72)` + `backdrop-filter: blur(12–20px)` + `1px solid rgba(255,255,255,.85)`. Three tiers: *strong* (hero / end card), *medium* (content), *soft* (timeline / list rows). **No solid white cards.**

**Radii.** Generous and consistent. Tag `6` · badge `8` · icon chip `10–12` · timeline `14` · content card `16` · index `18` · big card `20` · hero/end card `28`.

**Shadow.** Very low elevation. `0 4 16 / .04` for soft cards, `0 4 20 / .04` for default, `0 8 40 / .06` for hero. Brand-tinted shadow `0 4 20 rgba(26,122,80,.30)` only on the primary CTA. Never combine shadows with strong drop-shadow blur — the glass blur already carries the depth.

**Motion.** Restrained and slow. Opacity-fade + tiny `translateY(10px → 0)` over 600–800 ms with staggered 100 ms delays per card. No spring physics, no parallax, no looping animations.

---

## Iconography

**Style.** Lucide-style outlines — 24×24 viewBox, **2 px stroke**, `stroke-linecap: round`, `stroke-linejoin: round`. No filled glyphs, no two-tone, no perspective. Pictograms only (no logotypes).

**Sizing.**
- On a gradient *icon chip*: 36–44 px tile with `border-radius: 10–12` and the brand gradient; SVG inside is 18–22 px, **white** stroke.
- Inline / navigation: 14–20 px, **brand-green** stroke on glass; or `currentColor` inside buttons.

**Selection.** Use abstract, system-flavored glyphs: layers, clock, people, arrow, download, search. Avoid skeuomorphic objects (briefcase, phone, calendar-with-date). Avoid AI clichés (brain, sparkles, robot heads).

**Placement.** One icon per card, top-left, with 14–18 px space before the heading. Don't repeat the same icon within a single slide.

---

## Composition rules of thumb

1. **One atmospheric background per slide.** It is the bed; everything else floats.
2. **One brand-tinted accent per slide.** A gradient icon, an eyebrow, *or* one tinted phrase — pick one focal accent, not three.
3. **Cards in grids of 2, 3, or 4.** Never odd counts; never single hero cards mixed with grid cards on the same slide.
4. **Numerals as decoration.** When numbering items (01, 02, 03), make the number **30 px / 900 / `rgba(26,122,80,.18)`** — big, faded, structural, not loud.
5. **Divider rule.** Each section title is followed by a divider — either a 1-px gradient horizontal line, or a 36×3-px gradient accent bar. Never a solid grey rule.
6. **Lower-thirds.** Bottom-left holds the `:Hansol` logo (16 px / 700 / `0.08em` tracking). Bottom-right holds the slide counter (`03 / 06`, 14 px / 300 / 45% ink).

---

## Caveats

- The system was reverse-engineered from a **single source deck**. Vocabulary outside that deck (form controls, charts, tables, data viz, error states) is **not yet defined** — extrapolate cautiously and ask the user.
- The wordmark `:Hansol` is a typographic stand-in. The real Hansol corporate logo was not provided.
- Iconography uses Lucide-family generics. No proprietary Hansol icon set was provided.
- All Korean copy in `slides/` and `preview/` is **example content** lifted from the source — replace before publishing.
- The system has been validated for **slide decks**. Marketing pages, product UI, or email templates would need additional patterns (forms, dense tables, mobile breakpoints) layered on top.
