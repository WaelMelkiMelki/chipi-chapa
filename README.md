# chipi-chapa — Defense Deck

Reveal.js 5.x presentation for a 20-minute academic defense (SUP'COM /
University of Carthage / Huawei Northern Africa):

> **AI-Driven 5G FWA Planning and Fixed Broadband Migration Strategy with
> Digital Service Monetization** — MELKI Wael

Markdown-based slides, speaker notes, KaTeX math, syntax highlighting, slide
search/zoom/menu, and Mermaid diagrams. No bundler — static files plus CDN.

## Folder structure

```text
chipi-chapa/
├── index.html          # Deck shell: loads Reveal.js + plugins, lists slide files
├── package.json        # npm scripts (start, build:pdf) — no build step
├── README.md           # This file
├── .gitignore
├── assets/
│   ├── logos/          # Manually uploaded: supcom.png, carthage.png, huawei.png
│   ├── figures/        # Images extracted from the report PDF
│   └── diagrams/       # Mermaid-rendered SVGs for reuse in the report
├── css/
│   └── custom.css      # Branding layer (CSS variables) on top of theme white.css
├── slides/
│   └── 00-cover.md     # One .md file per section; 00-cover.md is the placeholder
└── scripts/
    └── README-scripts.md  # Helper-script docs (flows live in package.json)
```

**Rationale:** `index.html` stays a thin shell — content lives in `slides/`
(one file per section, numbered `NN-slug.md`), styling in `css/custom.css`,
binary assets in `assets/` by origin (logos vs. report figures vs. rendered
diagrams). Empty asset folders carry a `.gitkeep` because git cannot track
empty directories.

## Stack & pinned versions

| Piece             | Version  | Source (CDN, pinned)                                          |
| ----------------- | -------- | ------------------------------------------------------------- |
| Reveal.js         | 5.2.1    | `cdn.jsdelivr.net/npm/reveal.js@5.2.1`                        |
| reveal.js-menu    | 2.1.0    | `cdn.jsdelivr.net/npm/reveal.js-menu@2.1.0`                   |
| reveal.js-mermaid | 11.15.0  | `cdn.jsdelivr.net/npm/reveal.js-mermaid-plugin@11.15.0`       |
| KaTeX             | auto     | Loaded at runtime by `RevealMath.KaTeX` (no extra tag needed) |
| Inter webfont     | auto     | Google Fonts, graceful fallback to system stack offline       |

Enabled plugins: `RevealMarkdown`, `RevealNotes`, `RevealHighlight`,
`RevealMath.KaTeX`, `RevealSearch`, `RevealZoom`, `RevealMenu`,
`RevealMermaid`. Deck config: `hash: true`, `slideNumber: 'c/t'`,
`progress: true`, `controls: true`, `transition: 'slide'`, `1280×720`,
`margin: 0.05`.

## Run locally

Prerequisites: Node.js ≥ 18.

```bash
npm install
npm start
# → http://localhost:8000
```

`npm start` serves the repo root with caching disabled (`-c-1`), so edits to
`slides/*.md` show up on plain reload. Internet access is required at view
time (Reveal.js + plugins load from CDN).

## Present

| Key              | Action                                              |
| ---------------- | --------------------------------------------------- |
| `F`              | Fullscreen                                          |
| `S`              | Speaker-notes window (separate window with timer)   |
| `M`              | Slide menu (jump to any slide)                      |
| `Esc` / `O`      | Overview grid                                       |
| `Ctrl+Shift+F`   | Search slide text                                   |
| `Alt+Click`      | Zoom into a region                                  |
| `?`              | Full keyboard-shortcut help                         |

Slide numbers (`current/total`), progress bar, and hash URLs (`#/3`) are on.

## Authoring slides

1. Create `slides/NN-slug.md` (e.g. `slides/01-plan.md`).
2. Register it in `index.html` with a `<section data-markdown="slides/NN-slug.md"
   data-separator="^---$" data-separator-vertical="^--$" data-separator-notes="^Note:">`
   block, in presentation order.
3. Separators inside `.md` files: `---` = next horizontal slide,
   `--` = next vertical slide (sub-slide).

Speaker notes (never rendered on the slide itself):

```markdown
Some slide content.

Note:
Say this out loud — visible only in the speaker-notes window (S).
```

Mermaid diagrams: use a raw-HTML block (this plugin selects `.mermaid`; a
fenced ` ```mermaid ` code block would compile to `language-mermaid` and be
ignored):

```html
<div class="mermaid">
flowchart TD
    A[Start] --> B[End]
</div>
```

Math: `$...$` inline and `$$...$$` block (KaTeX). Code: fenced blocks with a
language tag for highlighting. Keep one commit per slide (see below).

## Export to PDF

```bash
npm start            # terminal 1 (must be running)
npm run build:pdf    # terminal 2 → writes chipi-chapa.pdf (git-ignored)
```

`build:pdf` headless-prints `http://localhost:8000/?print-pdf` with
`google-chrome` (falls back to `chromium`). Manual alternative: open the
`?print-pdf` URL in Chrome → Print → Save as PDF (enable background graphics).

## Logos (manual step)

`assets/logos/` is intentionally empty — upload these three files by hand:

- `supcom.png` — SUP'COM logo
- `carthage.png` — University of Carthage logo
- `huawei.png` — Huawei logo

Prefer transparent PNGs, ≥ 600 px wide. Reference them from slides as
`assets/logos/supcom.png` (paths are relative to the repo root).

## Commit convention

One commit per slide:

```text
slide-NN: <verb> <object>
```

Example: `slide-00: add cover slide`. Infra/tooling commits use
`init:` / `chore:` / `fix:` prefixes instead.
