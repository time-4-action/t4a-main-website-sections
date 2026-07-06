# Patrik Components — Website Sections

Scriptless HTML chart & range-bar components for the Patrik site. Every page contains
**only markup + `data-*` config**; all rendering and styling live in one shared script,
[`patrik-components.js`](patrik-components.js).

## Section Builder

The easiest way to create a component: open **[`index.html`](index.html)** in a browser.
Each builder gives you a simple UI, a live preview, and a ready-to-paste HTML snippet.

| Builder | What it makes |
| --- | --- |
| [`builder/radar-chart.html`](builder/radar-chart.html) | Performance octagon — single dataset or a comparison dropdown |
| [`builder/range-bars.html`](builder/range-bars.html) | Feel / rider-goal bars — two-pole or labelled-scale mode |

Configure → copy the snippet → paste it into your page → make sure the page loads
`patrik-components.js` once near the end of `<body>`. The script auto-renders everything.

## Repository layout

```
index.html                 Landing hub — links to every builder & example
patrik-components.js        The one shared render script (radar + range bars)

builder/                    Interactive builders (UI → preview → copyable HTML)
  ├─ radar-chart.html
  ├─ range-bars.html
  └─ builder.css            Shared builder styling

examples/                   Static reference pages using the components
  ├─ chart.html             Single radar chart
  ├─ chart-selector.html    Radar chart with a comparison dropdown
  └─ range-bars.html        Feel & rider-goal range bars

docs/                       Usage guide (attributes, options, screenshots)
  ├─ guide.html
  └─ guide.pdf

assets/                     Screenshots & images
reference/                  Full Patrik website page, kept for reference
```

## The two components (quick reference)

**Radar chart** — `<div class="patrik-radar-chart">`
- `data-axes` — comma list of axis labels
- `data-values` — comma list of values 0–100 (single-dataset mode)
- or a `<select class="patrik-radar-select">` inside, one `<option value="…">` per model
- optional colours: `data-fill` `data-stroke` `data-point` `data-grid` `data-axis-color` `data-label-color`

**Range bar** — `<div class="patrik-range-bar">`
- `data-title`, and either `data-left`/`data-right` (two-pole) or `data-scale` (labelled stops)
- `data-min` / `data-max` — start/end of the highlighted band (`data-scale-index` makes these stop indexes)
- optional: `data-value` marker, and colours `data-range` `data-track` `data-text` `data-border`

See [`docs/guide.html`](docs/guide.html) for the full attribute tables.
