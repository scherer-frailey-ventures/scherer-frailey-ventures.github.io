---
maintenance_instructions: |
  Dated history of the site's build (draft exploration, decisions reached, fixes applied), in the
  spirit of Keep a Changelog — no semver, since this site doesn't ship versioned releases. Newest
  entries first. This is where docs/DEVELOPMENT.md content lands the moment it resolves or turns
  into narrative — add an entry in the same edit that trims DEVELOPMENT.md, never let
  DEVELOPMENT.md accumulate a history waiting to be moved here. Mirrors the sibling pattern at
  `kinvergence.github.io/CHANGELOG.md`.
---

# Changelog

Dated history of the site — what changed, why, and decisions reached. `docs/DEVELOPMENT.md` stays
current-state only; this file is where its history lands.

## 2026-10-02 — The "merge the drafts" question was never answered; events overtook it

The 2026-07-09 "Open Decision: Merging the Drafts into the Live Site" entry below was still open as
of the 2026-08-28 cleanup — none of its four questions (voice approval, whether to keep the
Framework/Instance section, who decides the merge, whether the mobile-nav fix ships independently)
were ever actually resolved by the group. What happened instead: the Kinvergence separation
(2026-08-22/23) made the whole premise moot — the Framework/Instance split these drafts were
exploring became real organizations rather than a narrative section on the SFV site. The three
remaining drafts (`index1a.html`, `index3.html`, `family-ventures-framework-2.html`) were archived
rather than merged, and `index.html` was rewritten from scratch against SFV's own current charter,
vision, and verified timeline — see `docs/DEVELOPMENT.md` § Decisions in force and
`archive/README.md`. Recorded here so the 2026-07-09 questions below read as resolved-by-abandonment
rather than as still live.

Also today: `docs/DEVELOPMENT.md` was split — this changelog created to hold everything below,
leaving that file as current-state-only (structure, hard constraints, checked facts, decisions in
force), matching the pattern already in force at `kinvergence.github.io`.

## 2026-08-28 — Draft cleanup: `index1.html`, `index2.html`, `family-ventures-framework-1.html` retired

Part of the broader SFV repositioning following the Kinvergence separation
(`ed-scherer-runtime/areas/work-and-business/projects/advance-sfv-2.md`). All three files' content
was already fully accounted for elsewhere before deletion:

- **`index1.html` and `index2.html`** were superseded in-place by `index3.html`, which carries
  every improvement from both (per the tables below) plus the Framework/Instance section neither
  earlier draft had. Nothing in either file existed that `index3.html` doesn't already have.
- **`family-ventures-framework-1.html`** was one of two visually-identical mockups
  (`-1.html`/`-2.html`, differing only in color palette — purple/pink vs. teal/emerald). Its content
  was already fully documented below (§ Going a level deeper) and its actual replacement already
  exists and shipped: the real Kinvergence invitation site at
  [kinvergence.github.io](https://github.com/kinvergence/kinvergence.github.io), whose own
  `DEVELOPMENT.md` explicitly documents what it took from this mockup's structural skeleton and
  why most of the mockup's *content* (a "Core Values" section, four "pillars," the "[Qualifier]
  Family Ventures" placeholder name, the teal palette) was deliberately **not** carried forward —
  see that file's § Do not reintroduce.

`index3.html` and `family-ventures-framework-2.html` had their internal links (draft banners, the
"Preview a separated Framework site" card, and the closing CTA) repointed to the files that
survive, since both previously linked to the three retired files.

## 2026-07-10 — Mobile nav follow-up, and content redistributed from a recovered prototype

**Mobile nav follow-up: menu was invisible on real phones, and never reached the Framework
mockups.** A phone re-test of the 2026-07-09 fix below found the hamburger menu wasn't showing up
at all — two distinct problems, both fixed:

1. **`index1.html` / `index2.html` / `index3.html`: the menu was implemented correctly but hidden
   behind the draft banner.** The draft banner and the nav are both `position: fixed`, with the nav
   hard-coded to sit at `top: 36px` (and `body` given a matching `padding-top: 36px`) — an
   assumption that the banner renders as one line. On real phone widths the banner's six-link list
   wraps to two or three lines and grows well past 36px tall, but the banner's `z-index` (1100) is
   higher than the nav's (1000), so the taller banner simply covered the entire nav bar — logo,
   links, and hamburger button — leaving nothing visible or clickable underneath it. Confirmed in a
   simulated 390px-wide viewport: the banner rendered at ~96px tall, completely occluding the nav
   directly below it.

   **Fix:** the banner now has `id="draftBanner"`, and a small inline script measures its real
   rendered height on load and on resize/orientation-change, writing it to a `--banner-h` CSS custom
   property. The nav's `top` and the body's `padding-top` both reference `var(--banner-h, 36px)`
   instead of the hard-coded value, so the nav always sits directly below the banner regardless of
   how many lines the banner text wraps to.

2. **`family-ventures-framework-1.html` / `family-ventures-framework-2.html`: the menu was never
   built, exactly as flagged as a follow-up in the 2026-07-09 entry below.** Mobile CSS was just
   `.nav-links { display: none; }` with no toggle button, no JS, and no `.nav-toggle` styles at
   all — so below 768px the nav links vanished with nothing to replace them.

   **Fix:** both mockups now carry the same hamburger pattern as the SFV drafts — `.nav-toggle`
   button styles, a proper mobile dropdown (`.nav-links.open`), the toggle button markup
   (`#navToggle` / `#navLinks`), the open/close JS, and the same `--banner-h` fix from item 1 above
   (they share the identical banner/nav markup pattern, so the same overlap bug applied here too,
   once a menu existed to overlap).

Verified all five pages (`index1`, `index2`, `index3`, `family-ventures-framework-1`,
`family-ventures-framework-2`) in a simulated 390×844 mobile viewport: banner renders, nav sits
immediately below it with no overlap, hamburger button is visible and clickable, and tapping it
opens/closes the full link list.

**Redistributing content recovered from `index1a.html`.** A git conflict (see the 2026-07-09 entry
below on `index1a.html`) surfaced better copy from the unpulled March 2026 prototype than what the
July drafts started from. Rather than adopt that prototype wholesale — it baked the Framework pitch
directly into the SFV site, a direction superseded by the May 4 Demo Day split — its improvements
were distributed piece by piece:

| Content | Landed in | Notes |
|---|---|---|
| New "Our Mission" section (Julia / Charter / Derek candidate mission statements) | `index1.html`, `index2.html`, `index3.html` | New nav link + section; SFV-specific, not generic, so not added to the Framework mockups |
| Improved Story prose + Derek's pull-quote | `index1.html`, `index2.html`, `index3.html` | The prototype's closing "living proof / adopt, adapt" pitch paragraph was **not** ported — redundant with the Framework mockups' own CTA |
| Refined "How It Works" pillars (Weekly Heartbeats / Monthly Demo Days / Shared Tools & Transparency / Identity & Purpose Work, replacing Skill Sharing) | All five files | SFV versions keep a self-referential "us/our" voice without asserting the "Family Ventures" brand name; Framework versions use the brand name and third person |
| Updated stats (5.5+ years / 285+ Heartbeats / 65+ Demo Days / 4 Ventures) + refreshed impact cards | `index1.html`, `index2.html`, `index3.html` | Also updated the Instances-section citation of these same numbers in both Framework mockups |
| Improved Values copy (Family as Foundation / Integrity & Transparency / Mutual Support & Flourishing / Purpose-Driven Growth) | All five files | Framework versions re-voiced to third person ("members," "a family") since no single family is speaking there |
| Richer, identity-driven member bios + one-line quotes | `index1.html`, `index2.html`, `index3.html` | Kept **both** bio styles side by side — `[draft option 1]` (today's public-site-sourced bios) and `[draft option 2]` (the prototype's identity/MTP-driven bios) — since each member should pick their own preferred version at review rather than have one chosen for them. The prototype's quote line was added above both options in each card. |
| Founding date specificity ("September 2020") | Footer copyright line in `index1.html`, `index2.html`, `index3.html`; "running since" line in both Framework mockups | Confirmed accurate, not just inherited from the prototype |

`index1.html` / `index2.html` CTAs were deliberately left untouched (still the pre-Framework-split
copy) — that's intentional, showing the state of affairs before the Framework was factored out;
only `index3.html` has the reworked hand-off CTA.

## 2026-07-09 — Draft exploration for Demo Day prep

*Ideas explored ahead of the July 2026 Demo Day. Not committed — for group discussion. Nothing here
changed `index.html`; each idea lived in a sibling draft file so the live site was never at risk.
(Superseded 2026-10-02 — see entry above.)*

**Why these drafts existed.** A cross-system review of Ed's documented [online-presence user
journeys](https://github.com/ed-scherer/ed-scherer-os/blob/main/docs/reference/online-presence-user-journeys.md)
found that the member cards in the **Ventures** section were the pivot point for two visitor
journeys (a referral who meets a member first, and a stranger curious about SFV itself) — but the
cards were thin: name, role tag, and one or two bare links, no sense of who each person is. The
pattern below was proposed as something any member could apply to their own card; each draft only
touched presentation, never repo/org structure.

**Draft files:**

| File | Added on top of `index.html` | Status at the time |
|---|---|---|
| `index1.html` | A one-to-two sentence bio per member under the Ventures header, sourced from each member's own public site; the member's primary personal link visually distinguished as the "start here" link | Draft — needed each member's review |
| `index2.html` | Everything in draft 1, plus a small circular initials avatar per card (e.g., "ES", "JS") | Draft — placeholder only |
| `index3.html` | Everything in draft 2, plus a new "One Instance of a Replicable Framework" section reusing the Framework/Instance language already presented at the 2026-05-04 Demo Day (see `commons/docs/presentations/2026-05-04-demo-day-sfv-vision/`) | Draft — narrative preview only |

**`index1a.html` — recovered March 2026 prototype.** A `git pull` surfaced a merge conflict:
`index1.html` had also been used, independently, by an earlier session on another machine back on
2026-03-02 (the chat transcript for that session is in `.github/chats/`). That earlier prototype had
been pushed to `origin/main` months ago but never pulled down or promoted to `index.html`, so this
pass's drafts were built without it and collided on the filename.

That prototype pursued a different direction — baking the "Family Ventures product" pitch directly
into the SFV site itself (title: *"A Family Ventures Deployment"*), rather than the
instance/framework separation later agreed at the 2026-05-04 Demo Day. Superseded as a whole, but
preserved as **`index1a.html`** (byte-identical to the conflicting `origin/main` version) because a
couple of its sections — the "Why We Exist" / "Our Mission" framing and the "Our Journey" / "From
Isolated to Inspired" narrative — were better-written than these drafts and worth reusing (see the
2026-07-10 entry above for how that played out).

Each draft carried a `noindex` meta tag and a dismissible banner at the top so it was unmistakable
as exploration, not the live site.

**Bio sourcing (needed member confirmation before anything shipped).** Bios were summarized from
each member's own public site, not invented:

- **Derek Scherer** — from `derekscherer.com` (AI/automation/simulation consulting; the *Bot Leader* book)
- **Julia Scherer** — from `juliascherer.com` (Sheer Joy Piano Studio; Cognichine Outreach Manager)
- **Ed Scherer** — from his own approved brand material (`introductions.md`, professional/networking variant)
- **Jason Frailey** — from `jasonfrailey.com`, which read as a sculpture/creature-effects portfolio (Labyrinth, The Dark Crystal, God of War pieces) rather than the site's then-current "Content Creator & Developer" tag — the draft bio tried to bridge both, flagged for Jason to confirm or correct since it was inferred from the portfolio, not from anything he'd said about himself.

No role tags were changed for anyone but Ed — only bios were added underneath the existing tags.

**Avatar note.** Drafts 2/3 used plain initials in a colored circle, not real photos — the site was
icon-only by design at the time; adding a photo for one member without the others would have been
visually inconsistent, and using anyone's photo without asking first wasn't appropriate.

**The bigger "Family Ventures Framework" idea (Draft 3 only).** Since 2020 SFV quietly served two
purposes: a specific family's collaborative (**the instance**) and a potentially replicable model
other families could adopt (**the framework**). This was presented to the whole group at the
2026-05-04 Demo Day (`commons/docs/presentations/2026-05-04-demo-day-sfv-vision/`) and agreed
conceptually — but the follow-through (new GitHub org, template repos, a distinct Discord server, a
qualified name) hadn't happened; it had been back-burner for months.

**Assessment at the time:** standing up the actual framework organization (new GitHub org + template
repos + Discord rename + a settled qualified name like "Aligned Family Ventures") was judged *not* a
quick win — it would touch shared infrastructure four people depend on and deserved its own working
session. The quick, safe win was the narrative-only preview in `index3.html`: a short section naming
the framework/instance split in plain language, with zero infrastructure risk.

Open questions carried forward from the 2026-05-04 presentation at the time: what qualifying word or
name for the general framework (`family-ventures.com` was taken; candidates already brainstormed:
Aligned / Collaborative / Connected / Open Family Ventures, Family Ventures Collective/Network,
Venture Families); whether/when to stand up the separate GitHub org and template repos; whether/when
to rename the SFV Discord server; whether member bios should become a standing per-member
convention. **All superseded by the actual Kinvergence separation, 2026-08-22/23.**

**Going a level deeper: concrete Framework mockups (`family-ventures-framework-1.html`, `-2.html`).**
These two mockups went further than Draft 3's narrative section and actually showed what a
*separated* Framework homepage could look like — content factored out of the SFV site into
something SFV-neutral, with SFV itself listed as the first example instance. No real hosting, repo,
or Discord — everything lived in these two sibling files, purely to give the group something
concrete to react to at Demo Day.

| File | What it showed |
|---|---|
| `family-ventures-framework-1.html` | Content factoring only: generic "Model" narrative, "How It Works" (unchanged — already generic), an "Instances" section listing Scherer-Frailey Ventures as the flagship example plus a "Your Family Here" placeholder card, and a "Get Started" CTA. Used the same visual palette as the SFV site. |
| `family-ventures-framework-2.html` | Identical content to mockup 1, but with a **distinct color palette** (teal/emerald instead of SFV's purple/pink) — demonstrating the case for why the framework brand probably shouldn't look identical to any one instance's brand. |

Both mockups used `[Qualifier] Family Ventures` as a placeholder name throughout (matching the
bracket notation already used in the 2026-05-04 DSL/vision materials) — no name had been chosen.
What moved to the Framework mockup vs. stayed SFV-specific: the "isolated → inspired" narrative arc,
"How It Works" practices, and the four Values all read as reusable as-is (a useful observation in
itself — most of the site's substance was *already* framework-level content); the specific
5-year/260-sync/60-demo stats and the member Ventures cards stayed SFV-specific, surfaced in the
mockup as a single "Scherer-Frailey Ventures" example-instance card instead.

**Re-voicing the SFV drafts as "our instance," now that the Framework had its own mockups.** Once
the Framework had its own mockups, the SFV site no longer needed to carry the "this could work for
your family too" pitch — that job belonged to the Framework mockups. `index1.html`, `index2.html`,
and `index3.html` were re-voiced accordingly:

| Element | Before | After |
|---|---|---|
| Hero `h1` | "Your Family Could Be Your Greatest Team" | "Our Family Is Our Greatest Team" |
| Hero subtitle | "...an unstoppable support network—**and how you can do it too**." | "Since 2020, formalized collaboration has turned four independent entrepreneurs into an unstoppable support network." |
| Meta `description` | "...Discover how formalized family collaboration can empower **your** ventures." | "Scherer-Frailey Ventures — our family's entrepreneurship collaborative, fostering innovation, accountability, and mutual support since 2020." |
| Founding paragraph | "...a family entrepreneurship collaborative. **A framework** where individual ventures thrive..." | "...a family entrepreneurship collaborative — **our own operating rhythm**, where individual ventures thrive..." |
| How It Works badge | "⚙️ The Framework" | "⚙️ How We Operate" |

That last pair fixed a term collision: the page used lowercase "framework" generically (SFV's own
operating model) while "Framework" now also named the separated artifact — reserving capital-F
"Framework" for the one thing it names avoided Demo Day confusion. Applied to all three drafts.
`index3.html` additionally reworked its bottom CTA from "✨ You Can Build This Too" to "✨ This Works.
See the Framework Behind It." (primary button linking to `family-ventures-framework-1.html`) and
tightened its "A Bigger Idea" section with explicit mockup links.

**Mobile navigation fix.** A journey-fitness review against `online-presence-user-journeys.md`
(Actor 1 — Julia Referral, and Actor 7 — SFV-curious Stranger) surfaced a real bug: there was no
mobile navigation menu anywhere on the site — the nav links were simply `display: none` below 768px
with no replacement. This mattered specifically because both journeys' entry point is a QR code
scan, almost always a phone. Fixed in `index1.html`, `index2.html`, and `index3.html` with a
hamburger toggle (see the 2026-07-10 follow-up above for why it still wasn't visible on real
phones).

**Fixed: SFV-specific leakage into the Framework mockups' "Get Started" CTA.** A review of the two
Framework mockups against their own premise ("this is the Framework, not the SFV instance") found
the "Start Your Own [Qualifier] Family Ventures" section had leaked SFV-specific content into what
should have been a neutral call to action:

| Element | Before (leaked) | After |
|---|---|---|
| Primary button | "Visit Scherer-Frailey Ventures" → `index.html` | An inert, visually-disabled "[Qualifier] Family Ventures GitHub Organization *(coming soon)*" — honest that the framework org didn't exist yet |
| Secondary button | "SFV GitHub Organization" → `github.com/scherer-frailey-ventures` | "See an Existing Instance" → scrolls to the `#instances` section already on the same page |
| Meta `description` | "...distilled from Scherer-Frailey Ventures..." | "...distilled from one family's experience..." |

**Nav/section label: "Ventures" → "Members."** Walking a live-fire version of the journey —
*"Julia mentioned one of the members; I want to find them"* — surfaced a real gap: the nav link and
section badge both said "Ventures," a business/project word, when the visitor is scanning for a
*person's name*. Fixed in `index1.html`, `index2.html`, and `index3.html` (nav link, section badge,
footer link, and the `index3.html`-only Bigger Idea cross-reference).

**Open question raised: does SFV need its own documented user journeys?** Raised by generalizing
Ed's own Julia Referral journey beyond Ed specifically to any of the four members — is Ed's journey
model sufficient for SFV's own needs, or does SFV warrant its own documented set of user journeys,
scoped to all four members? Not decided at the time. A lightweight starting point exists at
`docs/member-journey-mapping-exercise.md` — a disposable 20-minute worksheet for each member to
self-walk their own "someone remembers me" journey.

**Open Decision (at the time): Merging the Drafts into the Live Site.** Everything above was
proposed, reviewed by Ed, and approved by Ed — but not yet decided on by the group, and not yet
live. Open questions before any of it would ship to `index.html`: did the group approve the "our
instance" re-voicing and the per-member bio pattern (including Jason's bio, specifically)? Did the
group want the "A Bigger Idea" Framework/Instance section on the live site at all? Who would decide
when/how the merge happened? Would the mobile-nav fix ship independently, since it was a bug fix
rather than a content decision? **See the 2026-10-02 entry at the top of this file for how this
actually resolved — none of these questions were ever answered; the Kinvergence separation overtook
the whole premise.**
