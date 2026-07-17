# Contributing to Contributor Catalyst

Thanks for helping build this site. It's a plain HTML/CSS/JS project with no build step, so you can go from clone to change in a couple of minutes.

## Before you start

- Check the [open issues](../../issues) for something to work on, or open a new one with the right template ([bug](../../issues/new?template=bug-report.yml), [feature](../../issues/new?template=feature-request.yml), [content task](../../issues/new?template=content-task.yml)).
- Comment on the issue to claim it. If it's unclear or under-specified, ask questions there before writing code.
- For anything beyond a typo fix, wait for a mentor to confirm the approach before investing significant time.

## Setup

1. Clone the repo: `git clone https://github.com/contributor-catalyst/website.git`
2. Open `index.html` directly in a browser, or serve the folder with any static server (e.g. `python3 -m http.server`).
3. No `npm install`, no build step. Edit HTML/CSS/JS files directly and refresh the browser to see changes.

## Coding conventions

- **HTML**: use semantic elements (`<nav>`, `<main>`, `<article>`, `<section>`, headings in order) instead of generic `<div>`s wherever one fits.
- **CSS**: add new styles to the relevant file in `assets/css/`; keep selectors scoped to the component/page you're touching rather than adding global overrides.
- **JS**: keep scripts framework-free and in `assets/js/`; prefer small, named functions over inline handlers.
- **JSON data** (`data/*.json`): match the existing schema for that file exactly — same keys, same nesting — so the JS that renders it doesn't break. If you need a new field, say so in your issue/PR rather than adding it silently.
- **Images**: add descriptive `alt` text for every content image; decorative images should use `alt=""`.

## Accessibility standards

This site is built to be usable with a keyboard and a screen reader. Before opening a PR:

- Every image has meaningful `alt` text (or `alt=""` if purely decorative).
- Headings are in a logical order (no skipping from `<h2>` to `<h4>`).
- Interactive elements (links, buttons, nav toggles) are reachable and operable via keyboard (Tab/Shift+Tab/Enter).
- Color choices maintain reasonable contrast against their background.
- New landmarks/regions (`nav`, `main`, etc.) are labeled if there's more than one of the same type on a page.

## Testing your change

There's no automated test suite, so testing is manual:

1. Open every page you touched directly in a browser.
2. Tab through the page with your keyboard only and confirm focus order makes sense and nothing is unreachable.
3. If you changed a JSON file, confirm the page that consumes it still renders (check the browser console for errors).
4. If you changed layout/CSS, check at a narrow (mobile) width as well as desktop.
5. Click every link you added or touched to confirm it resolves.

## Opening your pull request

- Fill out the PR template completely — reviewers use it to decide what to check first.
- Keep PRs focused on one issue; unrelated cleanup should be its own PR.
- Link the issue you're closing (`Closes #123`).
- A mentor will review first; once approved, a maintainer merges and the site redeploys automatically via `.github/workflows/deploy.yml`.
