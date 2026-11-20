# Domonique King — personal website

A single static page, `index.html`, with all CSS inline in a `<style>` block. No build step.

## Content rules

- Put the owner's text in exactly as written. Don't rephrase, trim, or "fix" it.
- Page order: top bar → hero statement → About → Clips → Contact.
- Clips go in `<ul class="clips">`, one `<li>` each: linked headline, then "— Publication, Month Year".
- Contact email: domoniqueking@washsun.com, shown only as the plain line "You can reach me at domoniqueking@washsun.com." No "Get in Touch" link (the owner asked for it to be removed).

## Style (keep this on every change)

Colors are a dark olive-green page with cream text; layout and type are a minimal editorial reporter portfolio.

**Colors** (CSS variables on `:root`; use these, don't add new ones without reason):
- `--bg` `#3e4235`: dark olive green, the page background
- `--bg-deep` `#34382c`: slightly darker green, for any band or panel that needs to stand apart
- `--text` `#f1eee6`: warm cream, for all main text
- `--muted` `#c9c6bb`: softer cream, for section labels and secondary text
- `--rule` `rgba(241,238,230,0.22)`: thin divider lines
- `--accent` `#c4c8cc`: pale blue-gray, for hover states and buttons
- One color scheme only: no separate light/dark mode.

**Type**:
- Serif `Cormorant Garamond` (Google Fonts), light weight 300–400, for the name, the hero statement, and body text.
- Sans `Jost` 300–400, small, for nav links and section labels only. Section labels are uppercase with wide letter-spacing (~0.18em).
- The hero statement is large (clamp ~2.4–3.75rem), weight 300, tight line-height (~1.15), and reads as one sentence: "[Name] is a [role] covering [beat]."

**Layout**:
- Top bar: name at left, small nav (About, Clips, Contact) at right.
- Lots of empty space; left-aligned content; max width ~64rem; body text kept to a ~36rem column.
- The page ends with the contact section: just the email line, in body text.
- Flat design: no shadows, gradients, rounded cards, or decorative icons.
- Must work at phone width: 16px side margins and no sideways scrolling.
