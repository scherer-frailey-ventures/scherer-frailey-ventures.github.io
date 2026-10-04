---
title: "Development"
description: "Working notes for the SFV website — current-state only: structure, hard constraints, checked facts, decisions in force, do-not-reintroduce list"
date_created: "2025-11-03"
last_updated: "2026-10-03"
maintenance_instructions: |
  Repo-local build detail only — current-state, not narrative. Project-level tracking (task list,
  session-by-session progress) lives in `advance-sfv-2.md` (ed-scherer-runtime, Ed's personal
  project file) — do not duplicate that here, and do not let this file's own history accumulate;
  when something here is resolved, dated, or turns into "how we got here" narrative, that belongs
  in the project file's Progress Log, not this file. Mirrors the sibling pattern already in force at
  `kinvergence.github.io/DEVELOPMENT.md` — when in doubt about what belongs here versus there, check
  how that file draws the line.
---

# Development

Working notes for the site. Read this before changing copy.

## Structure

One page, no build step: `index.html`. Styles and script are inlined — unlike `kinvergence.github.io`,
this site has never been split into multiple pages. A shared `assets/` folder was added 2026-10-02
(favicon, apple-touch-icon, emblem, OG image only — page styling stays inlined). Sections, in
order: Hero → Mission → Story (including "Why It Holds," the four members' 2026-03 purpose quotes)
→ How We Work (the three Kinvergence practices) → The Shape Of It (dated-fact stats) → Kinvergence
(relationship + cross-link) → Members (ventures + business-card one-liners) → closing CTA → footer.

**If this page keeps growing, split it** — `kinvergence.github.io`'s own experience is the
precedent: two rounds of sentence-level trimming only got it to 86% of its original length; moving
whole sections to dedicated pages is what actually worked. No secondary pages exist for this site
yet; the first candidate, if/when, is SFV's fuller story (founding, the twenty informal months, the
first Demo Day almost not happening — all already written up with evidence grades in
`commons/docs/sfv-timeline.md`, just not yet adapted into site copy).

## Hard copy constraints

| Rule | Source |
|---|---|
| **No cumulative counts** — no "5.5+ years," "285+ heartbeats," "65+ Demo Days." Checked against `sfv-timeline.md` and found unreliable. Prefer dated events and bounded phrasing ("almost every week since 2022-08") | `advance-sfv-2.md` Quality Gates; see § Checked facts below |
| **Real cadence names** — Heartbeat, Demo Day, Stewardship. Never "Weekly Sync," "Monthly Demonstration," or other generic placeholders | Same source as above |
| **No emoji** — not as decoration, not as icons. Matches `kinvergence.github.io`'s own hard constraint; this site previously had them throughout | `kinvergence.github.io/DEVELOPMENT.md` § Hard copy constraints, applied here 2026-10-02 |
| **No unratified "Core Values" section.** SFV's values are genuinely unselected — three candidates, not yet picked (`commons/docs/values-development.md`) — asserting a settled list would misrepresent that. This is the single worst thing to reintroduce, same as the equivalent warning in `kinvergence.github.io/DEVELOPMENT.md` | See § Do not reintroduce below |
| **No FVF-era branding** — "Family Ventures Framework," "[Qualifier] Family Ventures." Superseded by Kinvergence, 2026-08 | — |
| **De-instance as you go** — framework-level description (what a Heartbeat or Demo Day *is*, in the abstract) belongs in `kinvergence-core/docs/practices/`, not restated here. This site states SFV's own instance facts and links out for the abstraction | Same convention as both orgs' profile READMEs |
| **Mission statement is load-bearing, not decorative** — the provisional line in the Mission strip must stay word-for-word in sync with `commons/docs/charter.md` § Mission and `commons/docs/mission-development.md`'s "Provisional Selection" entry | — |

## Checked facts

Verified against SFV's own archives. The reconstruction, with an evidence grade on every row, is
[`sfv-timeline.md`](https://github.com/scherer-frailey-ventures/commons/blob/main/docs/sfv-timeline.md).

| Claim | Status |
|---|---|
| Founded **September 11, 2020** | Verified |
| Standing Monday meeting proposed **2022-05**; name "Heartbeat" first used **2022-06-06** | Verified |
| Demo Day proposed 2022-06-27 for 2022-08-01; **first actually held 2022-08-08** (postponed, Derek was sick) | Verified |
| "Almost every week since August 2022" | Verified — 163 of 212 weeks, six short gaps (≤3 weeks) in four years |
| Demo Day — "unbroken monthly record since October 2023" | Verified — complete thread ledger from Oct 2023 |
| Four 2026-03 member purpose quotes (Julia, Ed, Derek, Jason) | Verified against each member's own `commons/docs/member-profiles/` material, word-for-word |
| Derek's business-card one-liner, "I venture into the chaos..." | Verified — `member-profiles/derek-scherer/2026-02-28-sfv-profile-material.md`, "Business Card Version" |
| Ed's and Jason's one-liners | Verified against their own profile material; corrected two small misquotes inherited from the archived drafts (Ed: "find it!" not "find it."; Jason: "into the party" not "to the party") |
| Derek's "making a way for people to emulate what we do" | Verified — Feb 2026, quoted in `commons/docs/2026-03-02-demo-day-sfv-report.md` and the SFV introduction/vision presentation |

**If a new claim needs a number, check it against the timeline first, and prefer a dated event.**

## Brand

**Provisional, low-quality placeholder.** The mark is `assets/emblem/sfv-growth-emblem-v1.png` — a
static copy of `commons`' master file
([`assets/identity/emblem/master/`](https://github.com/scherer-frailey-ventures/commons/tree/main/assets/identity/emblem/master)),
itself just the old org avatar renamed, not a purpose-built mark. **No SVG master exists yet** —
unlike Kinvergence's tri-spiral-blades mark — and the PNG has no alpha channel (opaque white
background baked in), which constrains where it can be placed; see below.

**Referenced, not inlined** — from the nav brand and the favicon (`favicon.ico` plus
`assets/apple-touch-icon.png`, both copies of files already built by `commons`' own generator
script in
[`assets/identity/emblem/generated/`](https://github.com/scherer-frailey-ventures/commons/tree/main/assets/identity/emblem/generated)).
There is no build step here — if the master changes, re-copy the files by hand.

**Deliberately not on the hero.** The hero background is the purple/blue gradient
(`--gradient-1`); the emblem's opaque white backdrop would show as a visible box on top of it. Nav
placement works because the nav background is near-white (`rgba(255,255,255,0.95)`), so the
emblem's own white backdrop blends in. Revisit hero placement once a transparent or vector master
exists.

## Open Graph preview

Added 2026-10-02. One `assets/og-image.png` (1200×630, the OG standard ratio) backs the single
page. **Design:** pure white (`#FFFFFF`) background — chosen specifically so the emblem's own
opaque white backdrop disappears into the canvas instead of rendering as a box — with the emblem
centered above the "Scherer-Frailey Ventures" wordmark (`--text-dark`, Segoe UI Bold), both
centered on both axes, same vertically-stacked lockup convention as Kinvergence's (survives a
square center-crop, not just the 1.91:1 ratio Facebook/LinkedIn render directly). No tagline baked
in — `og:title`/`og:description` carry that as real text.

**Tags:** `og:type`, `og:site_name`, `og:url`, `og:title`, `og:description`, `og:image` (plus
`width`/`height`/`alt`), `twitter:card=summary_large_image`, `twitter:title`,
`twitter:description`, `twitter:image`, and `<link rel="canonical">`.

### Regenerating `assets/og-image.png`

Only needed if the master emblem changes. Requires ImageMagick (`magick`) and the `Segoe UI Bold`
font (ships with Windows; swap the `-font` value on another OS).

**Gotcha:** a plain `xc:"#FFFFFF"` canvas is all gray-valued pixels (R=G=B), so ImageMagick's PNG
writer auto-optimizes it to an actual grayscale PNG on write — and compositing a color mark onto
that canvas then flattens the mark's own color to grayscale too, not just the canvas. Every write
below passes `-define png:color-type=2` to force real RGB (truecolor) storage and avoid this.

```powershell
$emblem = "assets\emblem\sfv-growth-emblem-v1.png"
$out    = "assets\og-image.png"
$work   = Join-Path $env:TEMP "sfv-og"
New-Item -ItemType Directory -Force -Path $work | Out-Null

$canvasW = 1200; $canvasH = 630
$markSize = 260; $gap = 28; $fontPointsize = 72

magick -size "${canvasW}x${canvasH}" xc:"#FFFFFF" -define png:color-type=2 "$work\base.png"
magick "$emblem" -resize "${markSize}x${markSize}" -define png:color-type=2 "$work\mark.png"
magick -background none -fill "#1A202C" -font "Segoe-UI-Bold" -pointsize $fontPointsize label:"Scherer-Frailey Ventures" -trim +repage "$work\word.png"

$markInfo = (magick identify -format "%w %h" "$work\mark.png") -split " "
$wordInfo = (magick identify -format "%w %h" "$work\word.png") -split " "
$markW = [int]$markInfo[0]; $markH = [int]$markInfo[1]
$wordW = [int]$wordInfo[0]; $wordH = [int]$wordInfo[1]

$totalH = $markH + $gap + $wordH
$topY   = [math]::Floor(($canvasH - $totalH) / 2)
$markX  = [math]::Floor(($canvasW - $markW) / 2)
$wordX  = [math]::Floor(($canvasW - $wordW) / 2)
$wordY  = $topY + $markH + $gap

magick "$work\base.png" "$work\mark.png" -geometry "+$markX+$topY" -composite -define png:color-type=2 "$work\step1.png"
magick "$work\step1.png" "$work\word.png" -geometry "+$wordX+$wordY" -composite -define png:color-type=2 "$out"
```

Check the result at actual size before committing — font metrics shift slightly between machines, and verify with `magick identify -format "%[png:IHDR.color_type]" $out` that it reads `2 (Truecolor)`, not `0 (Grayscale)`.

## Decisions in force

| Element | Decision |
|---|---|
| **Draft pile** | `index1a.html`, `index3.html`, `family-ventures-framework-2.html` archived (not merged, not deleted) 2026-10-02 — each still carried a "Family Ventures Framework" section (now Kinvergence's content) plus the unverified cumulative stats. See `../archive/README.md` |
| **Values** | Deliberately absent from the site. Real candidates exist (`commons/docs/values-development.md`) but are unselected — publishing any of them now would overstate where that work actually stands |
| **Vision.md content** | `commons/docs/vision.md` is an unreviewed proposal to the other three partners (status: proposal, dated 2026-08-29). Its Mission line is already in force here (independently corroborated, pre-dates Kinvergence). Its "What we refuse to become" / "What we do not know" sections are genuinely strong, honesty.html-grade material — **held off the site until after partner review**, consistent with the document's own stated purpose |
| **Palette** | Unchanged gradient/indigo scheme inherited from the original Nov 2025 mockup — a separately-arrived-at scheme with no more authority than Kinvergence's own pre-brand-pass palette had. Not reconciled with Kinvergence's brand assets; a future brand pass could do that, same as Kinvergence's own deferred full brand pass |
| **Cross-links** | `#kinvergence` section plus footer link to `kinvergence.org`; GitHub org link in the footer and closing CTA |

## Do not reintroduce

- **A "Core Values" section asserting a settled list.** Values are genuinely unselected — see above.
- **Cumulative counts** ("5.5+ years," "285+ heartbeats," "65+ Demo Days") — checked and found unreliable; use dated events instead.
- **Generic placeholder cadence names** ("Weekly Sync," "Monthly Demonstration," "Skill Stack Sharing") — these were never SFV's actual practice names.
- **Emoji**, anywhere, as icon or decoration.
- **FVF-era branding** or a dedicated "Family Ventures Framework" section — that content now belongs to Kinvergence.
- **Invented job-title subtitles** under member names ("Entrepreneur & Innovator," etc.) — speculative, not sourced; dropped 2026-10-02 in favor of each member's own real one-liner.

## History

Dated history of the site — what changed, why, and decisions reached — lives in
[`CHANGELOG.md`](../CHANGELOG.md), not here. The July 2026 draft-exploration pass (`index1`–`index3`,
the Framework mockups) and their 2026-08-28/2026-10-02 retirement are recorded there.

