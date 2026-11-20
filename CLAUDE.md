# Domonique King — personal website

A single static page, `index.html`, with all CSS inline in a `<style>` block. No build step.

## Content rules

- Put the owner's text in exactly as written. Don't rephrase, trim, or "fix" it.
- Page order: masthead (name + tagline) → nav bar → About and Contact side by side → Clips → footer.
- Clips go in `<ul class="clips">`, newest first, one `<li>` each: `<a href="URL">Headline</a> — Outlet, Month D, YYYY`.
  The headline is always exactly as published. Use the `add-clip` skill (`.claude/skills/add-clip/SKILL.md`) to add clips.
  While there are none, keep it as `<ul class="clips"></ul>` with nothing between the tags; CSS then shows
  "Stories will be added here soon." That note disappears on its own once a story is added.
- Contact: the plain line "You can reach me at domoniqueking@washsun.com." inside the contact box.
  No "Get in Touch" link and no "Email me" button (the owner asked for the Get in Touch link to be removed).

## Style (keep this on every change)

Green-and-cream colors in a newspaper-style layout: big masthead, nav bar between rules, labeled sections.

**Colors** (CSS variables on `:root`; use these, don't add new ones without reason):
- `--bg` `#3e4235`: dark olive green, the page background
- `--bg-deep` `#34382c`: darker green, for the top stripe, the contact box and the empty-clips note
- `--text` `#f1eee6`: warm cream, for all main text and the filled section-label tabs
- `--muted` `#c9c6bb`: softer cream, for the rules around the nav bar, under labels and above the footer, and for secondary text
- `--rule` `rgba(241,238,230,0.22)`: faint lines between clip items
- `--accent` `#c4c8cc`: pale blue-gray, for hover states, the contact box's top border and the clips note's left border
- One color scheme only: no separate light/dark mode.

**Type** (Google Fonts):
- `Instrument Serif`: the name in the masthead only, uppercase, very large (clamp ~3–7rem), tight line-height.
- `Newsreader`: everything you read. The tagline is semibold (600) at ~1.4rem. The About paragraph is a ~1.3rem lede. Body is ~1.06rem.
- `Inter` 500–600: nav links, beats, and the section-label tabs (uppercase, slight letter-spacing).
- `IBM Plex Mono`: small uppercase, letter-spaced text for the "Reporting on" label and the footer.

**Layout**:
- A 6px `--bg-deep` stripe at the very top of the page.
- Masthead: the name at left, the tagline at right (max ~16rem wide). They stack on narrow screens.
- Nav bar with a rule above and below. At left: "Reporting on" followed by Policy, Courts and Education (plain text, not links). At right: About, Clips and Contact (anchor links).
- Section labels: a filled cream tab with green text, sitting on a full-width `--muted` rule.
- About: the headshot (`headshot.webp`, square, 13rem, no rounding or border) sits left of the About text. Below ~36rem wide it stacks above the text.
- From ~56rem wide, About and Contact sit side by side (about 1.65 : 1); below that they stack. Clips spans the full width underneath.
- Footer: a rule, then "© [year] Domonique King" in mono.
- Max content width ~72rem. Flat design: no shadows, gradients, rounded corners, or icons.
- Must work at phone width: 16px side margins and no sideways scrolling.
