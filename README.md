# H²Flow — project page

Static page for the paper *Groups Shape Futures, Futures Define Groups: Hypothesis-Conditioned Hypergraph Flow
Matching for Collective Motion Forecasting* (arXiv link: to be added).
No build step: `index.html` is self-contained (fonts from Google Fonts).

Preview locally:

```bash
python -m http.server 8000      # then open http://localhost:8000
```

Publish: create the repository `keshuw95/H2Flow`, push this folder to `main`, then
Settings → Pages → *Deploy from a branch* → `main`, `/ (root)`.
The site appears at `https://keshuw95.github.io/H2Flow/` (the URL printed in the arXiv paper's first-page footnote).

```bash
git init -b main
git add -A
git commit -m "H2Flow project page"
git remote add origin https://github.com/keshuw95/H2Flow.git
git push -u origin main
```

## When the arXiv ID and the code are out

- Hero buttons (`index.html`, `<div class="btns">`): turn the two `<span class="btn" aria-disabled="true">` into links,
  Paper → `https://arxiv.org/abs/<id>`, Code → the code repository.
- BibTeX block (`<pre id="bibtext">`): replace `journal = {arXiv preprint}` with `journal = {arXiv preprint arXiv:<id>}`.

## Contents

- `static/demo.json` — flow states, estimates and 2–4 s groups of NBA test plays 101, 150 and 213 (int16 centimetres,
  base64), from the paper's NBA flow dump (`exp_figures/data/h2flow_flow_s7.npz`). The hero animation and the live demo
  read it.
- `static/media/fig_*.webp` — Figs. 1–4 of the paper (from `overleaf/H2Flow_CVPR/figs`).
- `static/media/<clip>.mp4/.jpg` — four looping clips (flow_steps, hyp_groups, more_plays, pedestrians) and their
  posters, cut from the paper's videos; `overview.mp4` — the 2.5 min overview (720p), kept in the repo but not shown on the page.
- `static/og.jpg` — link preview (the overview's title card), `static/favicon.svg` — tab icon.

The page was first built as `../project_page/h2flow.html`; this copy adds a full HTML head (description, Open Graph
tags, icon), moves the assets under `static/`, and adds a `[hidden]` rule that the claude.ai wrapper used to provide.
The results tables transcribe Tabs. 1–3 of the paper; re-check them whenever those tables change.

Layout: a dark cover (title, authors, links, and the live court as a tilted stage), a white body with the figures set
directly on the page (white cards in dark mode), a dark video section, and a dark footer. The cover replays the flow on
play 213: its camera starts zoomed out to the noise and moves in to the forecast (the zoom per Euler step keeps 85% of
the 4 s states in view), then outlines the most-supported group of three of up to three top-scored hypotheses.
Sections: Overview (statement, Fig. 1, the paper's three contributions), Videos (four clips; the overview video is not shown), Results (headline gains, Table 1 as small-multiple
dot plots per level with NBA/NFL/Soccer and ADE/FDE switches, Tables 1–3 folded, the group-overlap analysis), Method
(Fig. 2 and its three components, no equations), Interactive Demo, Qualitative Results, BibTeX.

Type: Newsreader (title, headings, key numbers), Inter (text and interface), JetBrains Mono (BibTeX only).
