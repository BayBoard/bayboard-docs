# BayBoard help

Shop-staff help for [BayBoard](https://bayboard.io), the schedule board for auto repair shops. Published at [docs.bayboard.io](https://docs.bayboard.io) with Mintlify.

## What is here

- `docs.json`: site navigation, branding, and SEO settings.
- `*.mdx`: one page per task, grouped by folder (`schedule-board/`, `reports/`, and so on).
- `changelog.mdx`: sole source of truth for What's New. The app opens https://docs.bayboard.io/changelog in a new tab. Do not maintain a duplicate changelog in the app repository.
- `images/`: screenshots from the live app.
- `logo/`, `favicon.png`, `style.css`: brand assets and overrides.

## Working on the docs

Install the Mintlify CLI and preview locally:

```bash
npm i -g mint
mint dev
```

Before opening a pull request:

```bash
mint validate
mint broken-links
```

Every change goes through a pull request to `main`. Merging `main` publishes the site. Pull requests get a preview URL from Mintlify.

Writing rules: second person, short sentences, sentence-case headings, button labels exactly as the app shows them, no em or en dashes, no emoji. Screenshots are real captures from the app, cropped, PNG, wrapped in `<Frame>` with alt text.

## Contact

Questions about BayBoard: hello@bayboard.io.

## Copyright

Copyright BayBoard LLC. All rights reserved. This repository is public so the help site can be built and crawled; the content is not licensed for reuse.
