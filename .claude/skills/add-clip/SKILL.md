---
name: add-clip
description: Add one of Domonique's published stories to the Clips section of her site from a link, using the headline exactly as published plus the outlet and date, then commit and push. Use when she runs /add-clip with a story URL or asks to add a clip or story to the site.
argument-hint: <link to the story>
---

# Add a clip

Add the story at the link the user gave (`$ARGUMENTS`) to the Clips list in `index.html`, then push it.
If no link was given, ask for one and stop.

## 1. Open the link and read three facts

Open the URL with whatever web-fetching tool this session has, such as WebFetch or the `web-fetch` agent.
Ask for the raw facts below, not a summary. From the article page, get:

- **Headline:** the story's headline exactly as displayed on the article page, which is normally the `<h1>`.
  - Copy it character for character: same words, capitalization, punctuation, and curly vs. straight quotes.
  - Never rewrite, shorten, "clean up" or summarize it.
  - Don't use the browser-tab `<title>` text, which often adds " - Outlet Name" or a different SEO headline.
  - If the on-page headline and the `og:title` / `<title>` differ, use the on-page one and mention both to the user.
- **Outlet:** the publication's name as it styles itself, e.g. "The Washington Sun".
- **Date:** the original publication date shown on the story, not an "Updated" date.

**If you can't get all three for certain, don't guess.** That includes a failed fetch, a paywall or login page, a bot block, an error page, a page that isn't clearly the story, or a missing or ambiguous headline, outlet or date. Tell the user what happened. Ask them for the headline, the outlet and the date, exactly as published, and wait for the answer. Use only what they give you for anything you couldn't read yourself.

## 2. Check before editing

- Read the current Clips list in `index.html`, the `<ul class="clips">` element.
- If the same URL is already there, don't add it again. Tell the user and stop.

## 3. Add it to the list

Each clip is one `<li>` in this exact format:

```html
<li><a href="URL">Headline</a> — Outlet, Month D, YYYY</li>
```

- Write the date with the full month name, no leading zero, e.g. "November 20, 2026".
- Escape only what HTML requires: `&` → `&amp;`, `<` → `&lt;`, `>` → `&gt;` in the headline and outlet, and `"` → `&quot;` inside the `href`.
  Leave every other character, including curly quotes and dashes, exactly as published.
- Keep the list newest first. Normally the new story goes at the top. If it is older than clips already listed, place it by date so the order stays newest first, and say where it went.
- While the list is empty it is written as `<ul class="clips"></ul>`. The empty tag is what shows the "Stories will be added here soon." note. When adding the first clip, expand it to:

  ```html
      <ul class="clips">
        <li>…</li>
      </ul>
  ```

- Keep the indentation the same as the surrounding markup. Change nothing else on the page.
- Follow the style rules in `CLAUDE.md`. Don't add styles or restyle the list.

## 4. Verify

- Re-read the edited `<ul class="clips">` block. Check that the headline text matches what you copied character for character, and that the HTML is well formed.
- Make sure the list is still in newest-first order.

## 5. Commit and push

- Commit only `index.html`, with a message like: `Add clip: <headline>`.
- Push to the branch this session is working on, following the session's git rules.
  Don't push to `main` or any other branch unless the user has said to.
- If the push fails, say so plainly. Don't report the clip as published.

## 6. Tell the user what you added

Reply briefly with:

- the headline, outlet and date exactly as added
- the link
- where it went in the list (top, or which position and why)
- where each fact came from: read from the page, or provided by the user
- whether the push succeeded, and which branch it went to

Be accurate about "live": the change is visible on the public site only if the branch you pushed to is the one the site is published from. If you don't know of any published site, say the change is pushed but not yet live anywhere.
