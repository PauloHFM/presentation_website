# Personal Presentation Website

Source of <https://me.paulohfm.com>, a bilingual (English / Portuguese-BR) personal site built with [Hugo](https://gohugo.io/), the [Coder](https://github.com/luizdepra/hugo-coder) theme and deployed to GitHub Pages.

| Piece | Version / where |
|-------|-----------------|
| Hugo | 0.170.1 (pinned in `.github/workflows/hugo.yml`) |
| Sass | Dart Sass (Hugo 0.170+ no longer bundles a Sass compiler) |
| Theme | `themes/coder`, a git submodule pinned to upstream commit `c83ad86` (v1.2 + 15 commits) |
| Hosting | GitHub Pages, deployed by GitHub Actions on pushes to `main` |
| Domain | `me.paulohfm.com` (set in repo Settings -> Pages; DNS `CNAME` record) |

## Run it locally

```bash
# 1. Clone WITH the theme submodule
git clone --recurse-submodules https://github.com/PauloHFM/presentation_website.git
cd presentation_website
# (already cloned without it?  git submodule update --init --recursive)

# 2. Install the tools (macOS shown; see docs/TUTORIAL.md for Linux/Windows)
brew install hugo
brew install dart-sass          # Dart Sass, needed for Hugo 0.170+

# 3. Start the dev server (drafts included)
hugo server -D
```

> If Homebrew says it could not link `sass` because `/opt/homebrew/bin/sass`
> already exists, that is the npm package (`npm install -g sass`). Hugo cannot
> use it (build error `unexpected EOF when executing "sass"`). Fix it with
> `brew link --overwrite dart-sass`; check with `sass --version`.

Open <http://localhost:1313>. A production-like build is `hugo --gc --minify`
(output goes to `public/`, which is git-ignored).

## Write a post

```bash
hugo new posts/my-post.md              # English
hugo new posts/my-post.pt-br.md        # Portuguese-BR version of the same post
```

New posts start as `draft = true` (see `archetypes/posts.md`). Remove that
line (or set it to `false`) when the post is ready to publish. Pages and posts
live in `content/`; the Portuguese version of a file just adds `.pt-br` before
`.md`.

## Change something and publish

1. Create a branch and make the change (check it with `hugo server -D`).
2. Open a pull request. GitHub Actions builds the site as a check; nothing is
   deployed from a PR.
3. Merge to `main`. The workflow builds again and deploys to GitHub Pages.

## Update the theme or Hugo

```bash
# Theme: move the submodule to the latest upstream commit, then commit it
git submodule update --remote themes/coder
git add themes/coder && git commit -m "Update theme"

# Hugo: bump HUGO_VERSION in .github/workflows/hugo.yml (and brew upgrade hugo)
```

Check the pull-request build before merging an update.

## Project layout

| Path | What it is |
|------|------------|
| `hugo.toml` | Site configuration (languages, menu, social links, params) |
| `content/` | Pages and posts (`about`, `contact`, `posts/`, `authors/`) |
| `archetypes/` | Templates used by `hugo new` |
| `layouts/` | Overrides of the theme (footer, `email` shortcode) |
| `static/` | Files copied as-is (favicon, images) |
| `themes/coder` | The theme (git submodule, do not edit in place) |
| `.github/workflows/hugo.yml` | Build check on PRs, deploy on `main` |
| `CNAME` | Records the custom domain for reference |
| `docs/TUTORIAL.md` | Long Hugo walkthrough based on this repo (optional reading) |
| `plan.md` | Current to-do list / ideas |

## Domain

`me.paulohfm.com` is a subdomain, so DNS only needs a `CNAME` record pointing
to `PauloHFM.github.io`. In the repo go to **Settings -> Pages**, set the
custom domain and enable **Enforce HTTPS**. The site's `baseURL` in
`hugo.toml` must match (`https://me.paulohfm.com/`).

## License

See [LICENSE](LICENSE).
