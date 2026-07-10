# Public Website Development Notes

## Project: scherer-frailey-ventures.github.io

### Design Direction (November 3, 2025)

#### Core Purpose
Showcase how a formalized, extended-family-based collaborative organization can support individual ventures and personal growth. Inspire others to create similar structures within their own families.

#### Target Audience
1. Independent entrepreneurs who miss team environments
2. People interested in team collaboration frameworks (even family-based)
3. Media/storytellers looking for positive family collaboration stories
4. General public curious about strong family structures

#### Design Choices
- **Style**: Modern & tech-forward
- **Layout**: Single-page scrolling
- **Visuals**: Abstract/icon-based (no photos for now)
- **Effects**: Animated sections, hover effects
- **Colors**: Tech-forward palette (current avatar may be replaced)

#### Content Strategy
- **Tone**: Mix of inspirational, practical, and story-driven
- **Key Messaging**: 
  - Collaboration
  - Family
  - Accountability
- **Visual Enhancement**: Unicode pictographic characters throughout
- **Metrics to Highlight**:
  - 5 years running (since 2020)
  - Weekly syncs
  - Monthly demos
  - Number of family members/ventures

#### Featured Ventures & Members
Current ventures to showcase:
- Derek Scherer: https://www.derekscherer.com/
  - Cognichine: https://cognichine.com/
- Julia Scherer: https://juliascherer.com/
- Protizmo: https://www.protizmo.com/
- Jason Frailey: https://www.jasonfrailey.com/
  - Twitch: https://www.twitch.tv/jasonfrailey

#### Future Enhancements (Deferred)
- [ ] Contact form functionality
- [ ] "Getting Started Guide" for others to form similar organizations
- [ ] Charter template downloads
- [ ] Multi-page navigation as content grows
- [ ] Member photos/avatars
- [ ] Updated organization icon/logo
- [ ] Resources section for replication
- [ ] Step-by-step implementation guide
- [ ] Success stories/case studies
- [ ] Testimonials from members
- [ ] Blog/updates section
- [ ] Event calendar integration
- [ ] Project showcase gallery with filtering
- [ ] Interactive mermaid diagram from README

#### Technical Notes
- Single HTML file for simplicity
- Self-contained CSS (no external dependencies initially)
- Responsive design (mobile-first)
- Fast loading, minimal dependencies
- Accessibility considerations

#### Content Sections (Planned)
1. Hero - Bold statement about family collaboration
2. The Story - Journey from individual to collaborative
3. How It Works - Weekly syncs, monthly demos, skill sharing
4. Our Approach - Accountability, innovation, transparency
5. Impact/Achievements - Stats and milestones
6. Ventures - Showcase member projects
7. Values - What drives us
8. Call to Action - "You can do this too"

#### Design Inspirations
- Tech startup landing pages
- Modern SaaS product sites
- Community/collaboration platforms
- Family office websites (but more accessible/inspiring)

---

### Draft Exploration — Demo Day Prep (July 2026)

*Ideas explored ahead of the July 2026 Demo Day. Not committed — for group discussion. Nothing here changes `index.html`; each idea lives in a sibling draft file so the live site is never at risk.*

#### Why these drafts exist

A cross-system review of Ed's documented [online-presence user journeys](https://github.com/ed-scherer/ed-scherer-os/blob/main/docs/reference/online-presence-user-journeys.md) found that our member cards in the **Ventures** section are the pivot point for two visitor journeys (a referral who meets a member first, and a stranger curious about SFV itself) — but today the cards are thin: name, role tag, and one or two bare links, no sense of who each person is. The pattern below is proposed as something any member could apply to their own card; each draft only touches presentation, never repo/org structure.

#### Draft files

| File | Adds on top of `index.html` | Status |
|---|---|---|
| `index1.html` | A one-to-two sentence bio per member under the Ventures header, sourced from each member's own public site; the member's primary personal link visually distinguished as the "start here" link | Draft — needs each member's review |
| `index2.html` | Everything in draft 1, plus a small circular initials avatar per card (e.g., "ES", "JS") | Draft — placeholder only |
| `index3.html` | Everything in draft 2, plus a new "One Instance of a Replicable Framework" section reusing the Framework/Instance language already presented at the 2026-05-04 Demo Day (see `commons/docs/presentations/2026-05-04-demo-day-sfv-vision/`) | Draft — narrative preview only |

#### `index1a.html` — recovered March 2026 prototype (2026-07-09)

A `git pull` today surfaced a merge conflict: `index1.html` had also been used, independently, by an earlier session on another machine back on 2026-03-02 (the chat transcript for that session is in `.github/chats/`). That earlier prototype had been pushed to `origin/main` months ago but never pulled down or promoted to `index.html`, so today's drafts were built without it and collided on the filename.

That prototype pursued a different direction than today's drafts — baking the "Family Ventures product" pitch directly into the SFV site itself (title: *"A Family Ventures Deployment"*), rather than the instance/framework separation later agreed at the 2026-05-04 Demo Day. It's superseded as a whole, but it's preserved here as **`index1a.html`** (byte-identical to the conflicting `origin/main` version) because a couple of its sections — the "Why We Exist" / "Our Mission" framing and the "Our Journey" / "From Isolated to Inspired" narrative — are better-written than what's in today's drafts and worth reviewing for possible reuse in `index1.html`/`index2.html`/`index3.html`. Not itself a candidate for `index.html`; a source to draw from during the drafts' next revision pass.

Each draft carries a `noindex` meta tag and a dismissible banner at the top so it's unmistakable as exploration, not the live site.

#### Bio sourcing (needs member confirmation before anything ships)

Bios were summarized from each member's own public site, not invented:

- **Derek Scherer** — from `derekscherer.com` (AI/automation/simulation consulting; the *Bot Leader* book)
- **Julia Scherer** — from `juliascherer.com` (Sheer Joy Piano Studio; Cognichine Outreach Manager)
- **Ed Scherer** — from his own approved brand material (`introductions.md`, professional/networking variant)
- **Jason Frailey** — from `jasonfrailey.com`, which currently reads as a sculpture/creature-effects portfolio (Labyrinth, The Dark Crystal, God of War pieces) rather than the site's current "Content Creator & Developer" tag. The draft bio tries to bridge both; **Jason should confirm or correct this** — it's inferred from the portfolio, not from anything he's said about himself.

No role tags were changed for anyone but Ed — only bios were added underneath the existing tags.

#### Avatar note

Draft 2/3 use plain initials in a colored circle, not real photos. The site is currently icon-only by design (see "Design Choices" above); adding a photo for one member without the others would be visually inconsistent, and using anyone's photo without asking first isn't appropriate. Initials are a safe placeholder — swap in real photos only if/when each member is asked and agrees.

#### The bigger "Family Ventures Framework" idea (Draft 3 only)

Since 2020 SFV has quietly served two purposes: a specific family's collaborative (**the instance**) and a potentially replicable model other families could adopt (**the framework**). This was presented to the whole group at the 2026-05-04 Demo Day (`commons/docs/presentations/2026-05-04-demo-day-sfv-vision/`) and agreed conceptually — but the follow-through (new GitHub org, template repos, a distinct Discord server, a qualified name) never happened; it's been back-burner for months.

**Assessment:** standing up the actual framework organization (new GitHub org + template repos + Discord rename + a settled qualified name like "Aligned Family Ventures") is *not* a quick win — it touches shared infrastructure four people depend on and deserves its own working session. What *is* a quick, safe win is the narrative-only preview in `index3.html`: a short section naming the framework/instance split in plain language, using words already shared and agreed at Demo Day, with zero infrastructure risk. It gives visible progress on something that's stalled for months without pre-committing anyone to the org-level work.

**Open questions carried forward (unchanged from the 2026-05-04 presentation):**
- What qualifying word or name for the general framework (`family-ventures.com` is taken; candidates already brainstormed: Aligned / Collaborative / Connected / Open Family Ventures, Family Ventures Collective/Network, Venture Families)
- Whether/when to actually stand up the separate GitHub org and template repos
- Whether/when to rename the SFV Discord server to remove the "Family Ventures" ambiguity
- Whether member bios (Draft 1) should become a standing convention every member maintains for their own card

#### Going a level deeper: concrete Framework mockups (`family-ventures-framework-1.html`, `-2.html`)

Draft 3's narrative section names the framework/instance split in a sentence. These two mockups go further and actually show what a *separated* Framework homepage could look like — content factored out of the SFV site into something SFV-neutral, with SFV itself listed as the first example instance. Still no real hosting, repo, or Discord — everything lives in these two sibling files in this same repo, purely to give the group something concrete to react to at Demo Day rather than an abstraction.

| File | What it shows |
|---|---|
| `family-ventures-framework-1.html` | Content factoring only: generic "Model" narrative, "How It Works" (unchanged — it was already generic), an "Instances" section listing Scherer-Frailey Ventures as the flagship example plus a "Your Family Here" placeholder card, and a "Get Started" CTA. Uses the same visual palette as the SFV site. |
| `family-ventures-framework-2.html` | Identical content to mockup 1, but with a **distinct color palette** (teal/emerald instead of SFV's purple/pink). Demonstrates the case for why the framework brand probably shouldn't look identical to any one instance's brand — otherwise visitors can't tell the two organizations apart. |

Both mockups use `[Qualifier] Family Ventures` as a placeholder name throughout (matching the bracket notation already used in the 2026-05-04 DSL/vision materials) — no name has been chosen. What moved to the Framework mockup vs. stayed SFV-specific:

- **Moved (generic):** the "isolated → inspired" narrative arc, "How It Works" practices, and the four Values — all read as reusable as-is, which is itself a useful Demo Day observation: most of the site's substance is *already* framework-level content, not SFV-specific.
- **Stayed SFV-specific:** the specific 5-year/260-sync/60-demo stats, and the four members' Ventures cards — these belong to the instance, not the framework. The mockup surfaces them as a single "Scherer-Frailey Ventures" example-instance card instead.

This is still just a UI exercise — no actual separate website, repo, or org. If the group wants to pursue it further, the next real steps are the ones already listed above (naming, GitHub org, template repos, Discord).

#### Re-voicing the SFV drafts as "our instance," now that the Framework is factored out (2026-07-09)

Once the Framework has its own mockups, the SFV site no longer needs to carry the "this could work for your family too" pitch — that job now belongs to `family-ventures-framework-1.html` / `-2.html`. Leaving the old pitch copy in place on the SFV side would duplicate (and eventually contradict) what the Framework mockups say. `index1.html`, `index2.html`, and `index3.html` were re-voiced accordingly:

| Element | Before | After |
|---|---|---|
| Hero `h1` | "Your Family Could Be Your Greatest Team" | "Our Family Is Our Greatest Team" |
| Hero subtitle | "...an unstoppable support network—**and how you can do it too**." | "Since 2020, formalized collaboration has turned four independent entrepreneurs into an unstoppable support network." |
| Meta `description` | "...Discover how formalized family collaboration can empower **your** ventures." | "Scherer-Frailey Ventures — our family's entrepreneurship collaborative, fostering innovation, accountability, and mutual support since 2020." |
| Founding paragraph | "...a family entrepreneurship collaborative. **A framework** where individual ventures thrive..." | "...a family entrepreneurship collaborative — **our own operating rhythm**, where individual ventures thrive..." |
| How It Works badge | "⚙️ The Framework" | "⚙️ How We Operate" |

That last pair of changes fixes a term collision spotted during this pass: the page used lowercase "framework" generically (SFV's own operating model) in two places, while "Framework" now also names the separated artifact. Reserving capital-F "Framework" for the one thing it names avoids Demo Day confusion.

These five changes were applied to **all three drafts** (`index1`/`index2`/`index3`) since they don't depend on the Framework section existing. Two further changes were **`index3.html`-only**, since only that draft has introduced the Framework concept:

- **Bottom CTA reworked** from "✨ You Can Build This Too" (a direct replication pitch — now redundant with the Framework mockups' own "Get Started" CTA) to "✨ This Works. See the Framework Behind It." — a hand-off, with its primary button now linking to `family-ventures-framework-1.html` instead of restating the pitch.
- **"A Bigger Idea" section tightened** and given explicit "Preview a separated Framework site →" / "mockup 1 · mockup 2" links, so a Demo Day viewer can click straight from the nod into the concrete mockups instead of just reading about them.

**Deliberately left unchanged:** the live `index.html` — same reasoning as everywhere else in this section: it's real production copy, and this re-voicing should go live only after SFV members have actually discussed and approved the framework/instance split. Until then, `index.html` keeps the original all-purpose copy and the three drafts carry the proposed new voice for review.

#### Mobile navigation fix (2026-07-09)

A journey-fitness review against `online-presence-user-journeys.md` (Actor 1 — Julia Referral, and Actor 7 — SFV-curious Stranger) surfaced a real bug, not just a draft-copy question: **there was no mobile navigation menu anywhere on the site** — the nav links were simply `display: none` below 768px with no replacement. This matters specifically for these two journeys because their entry point is a QR code scan, which is almost always a phone; with Ventures now five sections down the page, a mobile visitor whose "primary interest is Ed rather than SFV" had no way to jump there without a long scroll.

Fixed in `index1.html`, `index2.html`, and `index3.html`: a small hamburger toggle button appears in the nav bar below 768px, opening a full-width dropdown of the same nav links (closes automatically on link tap). This predates all of this session's copy changes — it was a pre-existing gap in the live site too — so it's **not yet applied to `index.html`**, consistent with holding all drafted changes for group review. The same gap likely exists on `family-ventures-framework-1.html` / `-2.html` as well (not yet fixed there — flagging for a follow-up pass if those mockups get taken further).

#### Mobile nav follow-up: menu was invisible on real phones, and never reached the Framework mockups (2026-07-10)

A phone re-test of the 2026-07-09 fix above found the hamburger menu wasn't showing up at all — assessment found two distinct problems, both now fixed:

1. **`index1.html` / `index2.html` / `index3.html`: the menu was implemented correctly but hidden behind the draft banner.** The draft banner and the nav are both `position: fixed`, with the nav hard-coded to sit at `top: 36px` (and `body` given a matching `padding-top: 36px`) — an assumption that the banner renders as one line. On real phone widths the banner's six-link list wraps to two or three lines and grows well past 36px tall, but the banner's `z-index` (1100) is higher than the nav's (1000), so the taller banner simply covered the entire nav bar — logo, links, and hamburger button — leaving nothing visible or clickable underneath it. Confirmed in a simulated 390px-wide viewport: the banner rendered at ~96px tall, completely occluding the nav directly below it.

   **Fix:** the banner now has `id="draftBanner"`, and a small inline script measures its real rendered height on load and on resize/orientation-change, writing it to a `--banner-h` CSS custom property. The nav's `top` and the body's `padding-top` both reference `var(--banner-h, 36px)` instead of the hard-coded value, so the nav always sits directly below the banner regardless of how many lines the banner text wraps to.

2. **`family-ventures-framework-1.html` / `family-ventures-framework-2.html`: the menu was never built, exactly as flagged as a follow-up above.** Mobile CSS was just `.nav-links { display: none; }` with no toggle button, no JS, and no `.nav-toggle` styles at all — so below 768px the nav links vanished with nothing to replace them.

   **Fix:** both mockups now carry the same hamburger pattern as the SFV drafts — `.nav-toggle` button styles, a proper mobile dropdown (`.nav-links.open`), the toggle button markup (`#navToggle` / `#navLinks`), the open/close JS, and the same `--banner-h` fix from item 1 above (they share the identical banner/nav markup pattern, so the same overlap bug applied here too, once a menu existed to overlap).

Verified all five pages (`index1`, `index2`, `index3`, `family-ventures-framework-1`, `family-ventures-framework-2`) in a simulated 390×844 mobile viewport: banner renders, nav sits immediately below it with no overlap, hamburger button is visible and clickable, and tapping it opens/closes the full link list.

---

### Open Decision: Merging the Drafts into the Live Site

*Recorded here because this file is the shared, easily-updatable place for open SFV site questions — unlike Ed's Personal OS project files, which only he maintains.*

Everything in the "Draft Exploration" section above (`index1`–`index3`, `family-ventures-framework-1`/`-2`) is proposed, reviewed by Ed, and approved by Ed — but **not yet decided on by the group, and not yet live**. Open questions before any of it ships to `index.html`:

- Does the group approve the "our instance" re-voicing and the per-member bio pattern (including each member's own bio text — see the sourcing note above, especially Jason's)?
- Does the group want the "A Bigger Idea" Framework/Instance section on the live site at all, and if so, at what level of detail?
- Who decides when/how the merge into `index.html` happens — one PR reviewed by all four members? A Demo Day live walkthrough followed by a merge? Something else?
- Does the mobile-nav fix (above) ship independently/sooner, since it's a bug fix rather than a content decision?

No answers assumed here — just flagging that this decision hasn't been made yet, so it doesn't get lost between now and Demo Day.

#### Fixed: SFV-specific leakage into the Framework mockups' "Get Started" CTA (2026-07-09)

A review of the two Framework mockups against their own premise ("this is the Framework, not the SFV instance") found that the "Start Your Own [Qualifier] Family Ventures" section had leaked SFV-specific content into what should be a neutral call to action:

| Element | Before (leaked) | After |
|---|---|---|
| Primary button | "Visit Scherer-Frailey Ventures" → `index.html` | An inert, visually-disabled "[Qualifier] Family Ventures GitHub Organization *(coming soon)*" — honest that the framework org doesn't exist yet, instead of substituting SFV's real org as a stand-in |
| Secondary button | "SFV GitHub Organization" → `github.com/scherer-frailey-ventures` | "See an Existing Instance" → scrolls to the `#instances` section already on the same page, where the real SFV link correctly lives as the labeled example |
| Meta `description` | "...distilled from Scherer-Frailey Ventures..." | "...distilled from one family's experience..." — kept the SEO-only description consistent with the page's own generic voice |

Audited the rest of both mockups for the same pattern — nothing else found. The Instances section's SFV card, the stats within it, and the draft-banner nav links are all intentional (the first two are the labeled example; the banner is scaffolding, not page content). The footer's "Mockup Note" pointing at the `scherer-frailey-ventures.github.io` repo was left as-is — it's honestly disclosing where the mockup file currently lives, not presenting SFV as part of the Framework's own content.

#### Nav/section label: "Ventures" → "Members" (2026-07-09)

Walking a live-fire version of the journey — *"Julia mentioned one of the members; I want to find them"* — surfaced a real gap: the nav link and section badge both said **"Ventures"**, a business/project word, when the visitor is scanning for a *person's name*. The `<h2>` heading itself was already correct ("Our Members & Their Ventures"), but that "Members" cue never reached the nav the visitor scans first. This applies to all four members, not just Ed — it's a general SFV site gap, not an Ed-specific one.

Fixed in `index1.html`, `index2.html`, and `index3.html` (`index.html` untouched, same as everywhere else in this doc):

| Element | Before | After |
|---|---|---|
| Nav link | "Ventures" | "Members" |
| Section badge | "🚀 Active Ventures" | "👋 Meet the Members" |
| Footer Quick Link | "Ventures" | "Members" |
| (`index3.html` only) Bigger Idea section cross-reference | "...Everything in the **Ventures** section below is us, in action." | "...Everything in the **Members** section below is us, in action." |

The `<h2>Our Members & Their Ventures</h2>` heading and the `#ventures` anchor ID were left unchanged — only the shorter, scanned labels needed the fix; the fuller heading already carried both nouns correctly once a visitor arrives.

#### Open question: does SFV need its own documented user journeys? (2026-07-09)

This gap was found by walking a journey that generalizes Ed's own [Julia Referral journey](https://github.com/ed-scherer/ed-scherer-os/blob/main/docs/reference/online-presence-user-journeys.md) — "someone remembers a member" — beyond Ed specifically to any of the four members. That raises a real question for the group: **is Ed's journey model (extended informally, as it was here) sufficient for SFV's own needs, or does SFV warrant its own documented set of user journeys**, built the same way (actor inventory, journey diagrams, encounter notes) but scoped to all four members and the SFV site itself rather than to one person's presence?

Not decided here — flagging it as a live open question for Demo Day discussion, alongside the merge-timing question above. Arguments either way:
- **For a dedicated SFV journeys doc:** four members means four "remembers a person" variants, not one; a proper actor inventory might surface gaps like this one before they're found by accident; it would also be something all four members could own and extend, rather than living inside Ed's Personal OS repo
- **Against, for now:** the pattern found so far (nav label clarity, mobile nav, member-profile substance) generalizes cleanly from Ed's existing model without a full separate document; a dedicated SFV journeys effort is itself a scoped piece of work that competes with other Demo Day priorities

A lightweight starting point exists at `member-journey-mapping-exercise.md` (adjacent to this file) — a disposable 20-minute worksheet for each member to self-walk their own "someone remembers me" journey, rather than committing to a full journeys document up front. Delete it if the idea goes nowhere.

#### Redistributing content recovered from `index1a.html` (2026-07-10)

A git conflict (see the entry above on `index1a.html`) surfaced better copy from the unpulled March 2026 prototype than what these July drafts started from. Rather than adopt that prototype wholesale — it baked the Framework pitch directly into the SFV site, a direction superseded by the May 4 Demo Day split — its improvements were distributed piece by piece:

| Content | Landed in | Notes |
|---|---|---|
| New "Our Mission" section (Julia / Charter / Derek candidate mission statements) | `index1.html`, `index2.html`, `index3.html` | New nav link + section; SFV-specific, not generic, so not added to the Framework mockups |
| Improved Story prose + Derek's pull-quote | `index1.html`, `index2.html`, `index3.html` | The prototype's closing "living proof / adopt, adapt" pitch paragraph was **not** ported — redundant with the Framework mockups' own CTA |
| Refined "How It Works" pillars (Weekly Heartbeats / Monthly Demo Days / Shared Tools & Transparency / Identity & Purpose Work, replacing Skill Sharing) | All five files | SFV versions keep a self-referential "us/our" voice without asserting the "Family Ventures" brand name; Framework versions use the brand name and third person |
| Updated stats (5.5+ years / 285+ Heartbeats / 65+ Demo Days / 4 Ventures) + refreshed impact cards | `index1.html`, `index2.html`, `index3.html` | Also updated the Instances-section citation of these same numbers in both Framework mockups |
| Improved Values copy (Family as Foundation / Integrity & Transparency / Mutual Support & Flourishing / Purpose-Driven Growth) | All five files | Framework versions re-voiced to third person ("members," "a family") since no single family is speaking there |
| Richer, identity-driven member bios + one-line quotes | `index1.html`, `index2.html`, `index3.html` | Kept **both** bio styles side by side — `[draft option 1]` (today's public-site-sourced bios) and `[draft option 2]` (the prototype's identity/MTP-driven bios) — since each member should pick their own preferred version at review rather than have one chosen for them. The prototype's quote line was added above both options in each card. |
| Founding date specificity ("September 2020") | Footer copyright line in `index1.html`, `index2.html`, `index3.html`; "running since" line in both Framework mockups | Confirmed accurate, not just inherited from the prototype |

`index1.html` / `index2.html` CTAs were deliberately left untouched (still the pre-Framework-split copy) — that's intentional, showing the state of affairs before the Framework was factored out; only `index3.html` has the reworked hand-off CTA.

---


*Last Updated: 2026-07-10 (redistributed improved content recovered from the unpulled `index1a.html` prototype across the three SFV drafts and two Framework mockups — see table above)*
