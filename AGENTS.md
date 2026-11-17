# Jumper Docs

User-facing documentation for Jumper (jumper.exchange), built with [Mintlify](https://mintlify.com/).
Pages are MDX; `docs.json` defines the site config and navigation. Most commits come from the Mintlify
web editor (`mintlify[bot]`), so expect edits to land here from outside git as well.

## Layout

- `docs.json`: theme, colors, navbar, and the navigation tree (tabs, groups, pages). Must stay at the
  repo root so Mintlify finds it.
- Root `*.mdx`: guide pages (`index`, `quickstart`, `development`, `why-jumper`, `faq`) and some product
  and fee pages (`jumper-fees`, `jumper-rwa`, `jumper-perps-2`, `chads-vs-chuds-competition-terms`).
- `products/`: product pages (Swap, Earn, Portfolio, Pass, Scan).
- `resources/`: analytics, audits, chains, providers, smart contracts, brand assets, official links.
- `images/`: screenshots and illustrations referenced as `/images/<file>`.
- `logo/`, `favicon.svg`: brand assets referenced from `docs.json`.
- `api-reference/`, `essentials/`, `ai-tools/`, `snippets/`: Mintlify starter content. Not linked from
  `docs.json`, so not in the site navigation.

## Run locally

```bash
npm install -g mint
mint dev            # preview at http://localhost:3000
mint broken-links   # check internal links before pushing
```

There is no package.json, build step, test suite, or env file. Pushing to `main` deploys the site.

## Conventions

- A new page only appears in the site navigation once its path (without `.mdx`) is added to a group in
  `docs.json`. Unlisted pages stay reachable by URL and search. Removing or renaming a page means updating `docs.json` too.
- Give new pages frontmatter with `title`, `description`, and optionally `icon` (a few existing pages
  lack `description`).
- Prefer the Mintlify components the existing pages use (`<Frame>` around screenshots, `<Accordion>`,
  `<Card>`, `<Note>`, `<Steps>`) over raw HTML.
- Audience is Jumper end users, not integrators: plain language, no internal service names.
- Support contact used across the site: `support@jumper.exchange`.

## Ownership

Jumper squad, reviewer Eugene (`@chybisov`). Review requests: request the
reviewer above on the PR.
