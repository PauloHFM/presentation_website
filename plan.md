# To-do / ideas

Rough priority order. Ticked items are done.

## Done

- [x] GitHub repository with CI/CD to GitHub Pages (build check on PRs, deploy on `main`)
- [x] RSS feed (`/index.xml`, linked in the footer/social icons)
- [x] Bilingual site (EN / PT-BR)
- [x] Hugo + theme update, theme as a real git submodule

## Next

1. **Write the first real posts.** The Tech Blog is empty (the theme demo
   post was removed). `hugo new posts/my-post.md`, plus a `.pt-br.md` version.
2. **Real favicon, avatar and icons.** `static/images/favicon.svg` is a
   placeholder; the theme also links `favicon-16x16.png`, `favicon-32x32.png`,
   `apple-touch-icon.png`, `site.webmanifest` and `safari-pinned-tab.svg`
   (none exist yet). Decide between the Gravatar (current) or `avatarURL`.
3. **Check "Enforce HTTPS" in Settings -> Pages**, so canonical URLs, the
   sitemap and the RSS feed are `https://` (the live sitemap used `http://`).
4. **PT-BR CV link.** The CV button uses a single link for both languages;
   wire up the Portuguese CV per language (see the note in `hugo.toml`).
5. **Projects page** (the menu entry is commented out for PT-BR).

## Later / optional

- Privacy-friendly analytics (GoatCounter, Plausible, Umami... see
  `themes/coder/docs/analytics.md`).
- Search (e.g. Pagefind, which is static and needs no service).
- Comments (the theme supports giscus, utterances, Disqus...).
- Content-Security-Policy via the theme's `params.csp`.
- Grid view for the blog list (an older version of the layout is in git history).
- Social share image / Open Graph defaults.
