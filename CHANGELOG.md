# Changelog — Rosewater Teal AO3 Site Skin

**Author:** intothisshadow  
**Based on:** Rosewater Teal v1 + Breath of Life (structure reference)

---

## [v2.1.0] — 2026-04-01

### Mobile Add-on Skin

A companion skin (`style_mobile.css`) for screens ≤62em (tablet and phone).  
Load as a child skin with the desktop skin as parent, media set to `handheld`, `only screen and (max-width: 62em)` and  `only screen and (max-width: 42em)`.

**≤ 62em (tablet / landscape phone)**

- `#main` stacked full width, sidebar floats removed
- Dashboard collapses to horizontal inline flowing text links (matching AO3 default mobile style)
- Dashboard headings hidden; current item gets subtle teal highlight
- Splash modules: 2-column layout
- Tag pills: `max-width: 80vw`, wrapping enabled
- Admin page primary icon capped to 60×60px

*e≤ 42em (portrait phone)**

- Base font reduced to `0.9em`
- Header search bar hidden
- Dashboard borders thinned
- Blurb cards: tighter padding, reduced border-radius
- Splash: single-column layout; heading padding reduced; blurb h4 offset 60px to clear required-tags icons
- Comment icons shrunk to 55px
- Forms: full-width, floats removed
- User profile: icon hidden (absolute positioning incompatible with AO3 mobile layout); banner fills full width
- Drop cap reduced

**≤ 30em (very small phones)**

- Base font reduced to `0.85em`
- Comment icons hidden; byline margin reset
- Drop cap and first-line small caps disabled
- Blurb cards and work meta further reduced

## [v2.0.0] — 2026-03-31

Complete architectural rewrite of v1. Visual identity preserved; everything else rebuilt.

### Architecture

- Full `:root` CSS variable system — all palette, border, surface, button, tag pill, and link colours editable in one place
- All hardcoded hex values replaced with variables throughout
- Tag pill colours have dedicated variables (`--tag-fandom-bg`, etc.) for easy recolouring
- Link colours have dedicated variables (`--link`, `--link-visited`, `--link-active`)
- 21-section table of contents; v1 covered ~8 sections
- HOW TO USE notes added to header comment

### Global / Reset
- Full-page teal gradient background
- `hr`: crimson→teal gradient bar
- `text-align: left` enforced on workskin, blurbs, and system/docs pages

### Typography
- h1–h6: Goudy Bookletter 1911, alternating crimson (odd) / teal (even)
- `h2::after` decorative gradient underline bar
- Extra spacing after h2 on static content pages (`.system`, `.docs`)
- Landmark headings collapsed visually, kept in DOM for accessibility
- `datetime`: `font-size: xx-small`

### Links
- Crimson base, dashed wine on visited, teal on hover, teal-blue on active
- Author links: italic teal, never styled as buttons

### Header & Navigation
- Crimson→teal gradient nav bar
- Pill-shaped search input; crimson→teal button
- Teal dropdown menus with beige border
- AO3 logo recoloured to cream via filter (ZerafinaCSS)

### Dashboard & Sidebar
- Teal sidebar; crimson→teal gradient heading pill
- Goudy uppercase nav links; oxblood→crimson hover with `scale(1.05)`
- Teal gradient pill for current page

### Buttons & Actions
- Crimson gradient base → teal on hover
- Full restore system to prevent button styles bleeding into nav, greeting, dropdowns, footer, author links
- `span.unread`: crimson badge; `.replied`: teal badge
- Inbox comment actions: plain link style

### Forms & Inputs
- White inputs, tan border, teal focus ring
- Fieldsets: parchment background, teal left border
- Skin editor autocomplete overflow fix

### Tag System
- All 6 tag types fully styled with hover states
- New: Category tags — crimson→teal diagonal gradient
- Comma separators removed; `max-width: 45vw` overflow protection
- Tag colours driven by `:root` variables

### Work Blurb Cards
- Parchment→beige gradient, teal left border, crimson bottom, offset shadow
- Fic title: crimson-dark Goudy; author: mid-teal italic
- Visited fic title inherits colour (author excluded via `:not([rel="author"])`)
- Fandoms list clears required-tags float on splash page
- Cards lift on hover

### Work Page
- `#workskin`: parchment-to-teal gradient, Goudy for all children
- `h1`: crimson→teal gradient text with full-width `::after` bar
- `h3` subheadings: teal uppercase, centred gradient `::after` bar
- `.userstuff h3` in FAQ/admin/docs: gradient `::after` bar, AO3 default border overridden
- Drop cap + first-line small caps on opening paragraph
- Work meta sidebar: parchment card, teal left border
- Author byline: `"by "` injected via `::before`
- Kudos bar: blurb card style

### Comments
- Blurb card style; parchment→teal byline gradient strip
- Inbox actions: plain link style aligned with unread/replied badges
- Latest messages byline: stripped of pill

### Front Page (Splash)
- Module/favorite cards: parchment gradient, teal top border
- Section headings: crimson→teal gradient banner
- Blurb fic titles and author links inside gradient heading: cream
- "My Inbox" / "My History" links: no underline
- Favorite list: alternating crimson-teal gradient rows
- 2-column layout for logged-in splash

### Index, Profile, Stats, History
- Media index: card layout, crimson→teal heading banners
- Tag cloud: parchment cards, crimson gradient on hover
- Username banner: crimson→teal gradient, Goudy
- User icon: teal border, crimson bottom, hover switches
- Reading history "Last visited": teal-accented badge

### Miscellaneous
- Custom scrollbar: crimson→teal gradient thumb
- `pre`/`code`: parchment background, teal left border
- Text selection: semi-transparent teal wash
- `overflow: hidden` + `box-sizing: border-box` on `.news .userstuff` to contain images

### ZerafinaCSS Icons (Section 21)
- Integrated "Replace the AO3 Icons 2.0" by ZerafinaCSS
- All rating, category, warning, completion, bookmark, RSS, kudos, and lock icons replaced

---

## [v1.0.0] — 2026-02-19 

-  Skin published



### Known Limitations

- **Goudy Bookletter 1911** must be installed locally or injected via Stylus. AO3 does not support `@font-face` or `@import`. 
- AO3's own stylesheets load after the skin — `!important` is required throughout.
- Complex `:not()` selectors (e.g. `:not(.splash *)`) are rejected by AO3's CSS validator.
- `font-family` values cannot use CSS variables on AO3.
