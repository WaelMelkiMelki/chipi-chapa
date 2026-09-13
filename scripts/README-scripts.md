# scripts/

Helper scripts for the deck live here. Currently docs-only on purpose: the
day-to-day flows (`npm start`, `npm run build:pdf`) are one-liners in
`package.json` so there is no build step to maintain.

## Current flows

| Flow          | Command                 | What it does                                                  |
| ------------- | ----------------------- | ------------------------------------------------------------- |
| Serve locally | `npm start`             | `http-server -p 8000 -c-1 .` (cache disabled for authoring)   |
| Export to PDF | `npm run build:pdf`     | Headless Chrome prints `http://localhost:8000/?print-pdf`     |

`build:pdf` requires `npm start` to be running in another terminal and a
`google-chrome` (or `chromium`) binary on PATH. Manual fallback: open
`http://localhost:8000/?print-pdf` in Chrome → Print → Save as PDF.

## Planned helpers (not yet created)

- `extract-figures.sh` — pull images out of the report PDF into
  `assets/figures/` (e.g. via `pdfimages` / PyMuPDF), with stable filenames.
- `render-diagrams.sh` — render checked-in Mermaid sources to standalone SVGs
  in `assets/diagrams/` for reuse in the written report
  (e.g. via `npx @mermaid-js/mermaid-cli`).

Conventions for future scripts: POSIX `sh`, executable bit set (`chmod +x`),
`<verb>-<object>.sh` naming, and a `--help` flag that prints usage.
