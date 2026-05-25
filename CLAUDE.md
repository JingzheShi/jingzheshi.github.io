# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Jingzhe Shi's personal academic homepage, served by GitHub Pages at `https://jingzheshi.github.io/`. Adapted from Jon Barron's template (`https://jonbarron.info/`).

No build step, no package manager, no tests. Edits to `index.html` / `stylesheet.css` ship on push to `master`. To preview locally, open `index.html` directly in a browser or serve the directory (e.g. `python -m http.server`).

## Structure

- `index.html` — the entire English homepage. All content (bio, publications, work experience, awards) lives here as inline HTML tables; there is no templating. Each publication is a `<tr>` block under "Selected Publications & Preprints" with a thumbnail (`images/`), title link, author list, venue, and code/arXiv links.
- `stylesheet.css` — Lato font imports plus a few classes (`.papertitle`, `.name`, link colors). Layout is driven by inline styles on the tables in `index.html`, not CSS classes.
- `images/` — paper thumbnails, logos, profile photo, favicon. Add new paper images here and reference by relative path.
- `data/CV_JingzheShi.pdf` — linked CV.

## Chinese version sync (.github/workflows/sync-chinese.yml)

`index_cn.html` is the Chinese homepage, linked from `index.html` (and vice versa). When it changes on `master`, the workflow:

1. Injects `<base href="https://jingzheshi.github.io/">` before the favicon link so relative asset paths still resolve from the main site.
2. Pushes the result as `index.html` to the separate org repo `jingzhe-cn/jingzhe-cn.github.io` using the `ORG_REPO_TOKEN` secret.

Keep relative asset paths (`images/...`, `data/...`) in `index_cn.html` — the workflow's `<base>` tag is what makes them resolve on the mirror.

## Editing conventions observed in index.html

- Publication entries follow a fixed two-cell `<tr>` pattern (25% thumbnail / 75% text). Match the existing pattern when adding entries rather than inventing new markup.
- `*` denotes equal contribution, `^` denotes equal correspondence (legend stated near the section header).
- Author's own name is wrapped in `<strong>` in author lists.
- Sections are ordered: bio → Publications → Work Experience → Honors → Language and Skills. Commented-out blocks (Education, Fun facts) are kept in source for easy re-enable.
