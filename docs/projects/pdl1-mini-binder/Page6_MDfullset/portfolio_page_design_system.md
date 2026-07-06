# Portfolio Page Design System

Reusable design document derived from the uploaded `index.html` page.

## 1. Design intent

This page uses a restrained scientific-portfolio style: warm paper background, serif editorial headings, compact sans-serif body text, monospaced numeric labels, and low-saturation accent colors. The tone is expert-facing, calm, and analytical rather than flashy.

The design works well for computational protein-design portfolio pages because it supports:

- narrative explanation;
- quantitative summaries;
- tables and parameter blocks;
- charts;
- embedded figures;
- interactive molecular viewers;
- short interpretive callouts.

The default visual hierarchy should make the page feel like a polished technical field report, not a slide deck or journal article.

---

## 2. Core visual tokens

### Backgrounds

| Token | Hex | Use |
|---|---:|---|
| `--bg` | `#faf9f6` | Main page background; warm off-white paper tone |
| `--bg2` | `#f0eeea` | Secondary panels, table headers, toolbar backgrounds |
| `--bg3` | `#e6e3dc` | Borders, dividers, subtle structure |
| White | `#ffffff` | Cards, table surfaces, chart panels, figure panels |

### Text

| Token | Hex | Use |
|---|---:|---|
| `--tx` | `#1a1a18` | Primary headings and high-emphasis text |
| `--tx2` | `#5a5850` | Body copy |
| `--tx3` | `#8a8878` | Metadata, captions, labels, quiet text |

### Accent palette

| Token | Hex | Use |
|---|---:|---|
| `--accent` | `#1d6b52` | Primary accent, links, left borders |
| `--accent2` | `#0f4a38` | Strong accent text and stat numbers |
| `--accent-light` | `#e1f0ea` | Green-tinted background for banners and insight callouts |
| `--coral` | `#c85a3a` | Warning/error or contrast accent |
| `--coral-light` | `#faeae4` | Coral-tinted panel background |
| `--blue` | `#2e6da4` | Optional chart/category color |
| `--blue-light` | `#e6f0fa` | Optional blue panel background |
| `--amber` | `#b07818` | Optional caution/secondary metric color |
| `--amber-light` | `#faf0da` | Optional amber panel background |
| `--purple` | `#6b4c9a` | Optional categorical or cluster color |
| `--purple-light` | `#ede6f5` | Optional purple panel background |

### Geometry

| Token | Value | Use |
|---|---:|---|
| `--radius` | `6px` | Small cards, banners, buttons, select inputs |
| `--radius-lg` | `10px` | Larger cards, callouts, viewers |

Use thin borders rather than heavy shadows. The page’s visual depth comes from spacing, warm panels, and subtle borders.

---

## 3. Typography

### Font stack

```css
--serif: "Source Serif 4", Georgia, serif;
--sans: "DM Sans", system-ui, sans-serif;
--mono: "JetBrains Mono", monospace;
```

### Usage

| Element | Font | Style |
|---|---|---|
| `h1` | Serif | 2rem, 600 weight, slight negative tracking |
| `h2` | Serif | 1.35rem, 600 weight, bottom divider |
| `h3` | Sans | 1rem, 600 weight |
| Body `p` | Sans | 0.938rem, relaxed line-height, muted text |
| Subtitle | Serif | 1.05rem, italic, quiet gray |
| Numeric stats | Mono | 1.6rem, accent-dark |
| Labels / metadata | Sans or mono | Small caps, uppercase, letter-spaced |
| Code | Mono | Inline chip on `--bg2` |

### Typographic principle

Use serif type for narrative framing and section rhythm. Use sans-serif for operational explanation. Use monospace only where the content is numerical, identifier-like, parameter-like, or code-like.

---

## 4. Page shell

### Container

```css
.page {
  max-width: 920px;
  margin: 0 auto;
  padding: 2rem 1.5rem 4rem;
}
```

### Recommendation

Keep the 920px max width for long-form technical pages. It is wide enough for charts and two-column comparisons but narrow enough for readable body text.

For heavier dashboards, use a separate dashboard page rather than widening this template too much.

---

## 5. Top series banner

### Purpose

The banner anchors the page inside a multi-part portfolio series.

### Pattern

```html
<div class="series-banner">
  <span class="tag">Post-MD Fingerprinting</span>
  <span class="sep">|</span>
  <span>Series label</span>
  <span class="sep">|</span>
  <a href="...">← Previous page</a>
</div>
```

### Styling notes

- Light green background.
- Left border in primary accent.
- Monospace uppercase tag.
- Small link with dashed underline.
- Works best as a compact navigational/context strip, not a full hero.

### Reuse guidance

For future pages, update only:

- the tag;
- the series label;
- previous/next page links.

Do not overstuff the banner with metrics or long copy.

---

## 6. Hero title block

### Pattern

```html
<h1>Part N: Short, memorable title</h1>
<p class="subtitle">One-sentence technical subtitle</p>
```

### Guidance

The page title should be interpretive, not merely descriptive. The subtitle can carry the technical specificity.

Good pattern:

- Title: `What Survives Physics`
- Subtitle: `Post-MD interface fingerprinting across 28 consensus PD-L1 mini-binder candidates`

This creates a useful split: narrative hook first, precise scope second.

---

## 7. Recap block

### Purpose

Use `.recap` to connect the current page to the previous workflow step and state the question being answered.

### Pattern

```html
<div class="recap">
  <p><strong>Previously:</strong> ... This page asks: <em>...</em></p>
</div>
```

### Styling

- `--bg2` background.
- Rounded large radius.
- Left border in `--accent`.
- Slightly smaller text.

### Usage rule

Use one recap block near the top of each portfolio page. It should answer:

1. What came before?
2. What changed in this page?
3. What question does this page resolve?

---

## 8. Stat cards

### Purpose

The stat row provides an immediate quantitative summary.

### Pattern

```html
<div class="stats-row">
  <div class="stat-card">
    <div class="num">28</div>
    <div class="label">Simulations completed</div>
  </div>
</div>
```

### Layout

- Four columns on desktop.
- Two columns on small screens.
- White card surface.
- Thin border.
- Centered content.
- Monospace number.
- Uppercase label.

### Recommended use

Use 3–4 stat cards. Avoid more than 4 unless the page is a dashboard.

Good metrics are:

- counts;
- pass rates;
- means/medians;
- headline thresholds;
- top-level outcomes.

Avoid putting explanatory text inside stat cards. Explain in the paragraph below.

---

## 9. Section structure

### `h2`

Use `h2` for major narrative turns:

- scaling a workflow;
- defining a scoring step;
- interpreting a major result;
- explaining a visualization;
- concluding with triage implications.

`h2` includes a bottom border, so it should not be overused.

### `h3`

Use `h3` for local subsections inside a major section:

- parameters;
- figure titles;
- example labels;
- component headings.

### Paragraph rhythm

The page works best with 1–3 paragraphs between visual elements. Do not stack too many figures without explanatory text.

---

## 10. Parameter tables

### Purpose

Use `.param-table` for concise computational or analysis settings.

### Pattern

```html
<table class="param-table">
  <thead>
    <tr><th>Parameter</th><th>Value</th><th>Rationale</th></tr>
  </thead>
  <tbody>
    <tr>
      <td>Persistence threshold</td>
      <td class="num">≥ 90% occupancy</td>
      <td>Contact present in at least 22 of 24 frames</td>
    </tr>
  </tbody>
</table>
```

### Styling principles

- Table headers use `--bg2`, uppercase small labels.
- Numeric or parameter values use monospace.
- Rows get subtle dividers.
- Hover state is acceptable for interactive pages.

### Use when

A parameter table is appropriate when the reader needs to know exactly how a result was computed, but does not need a full methods section.

---

## 11. Chart cards

### Purpose

Chart cards make Chart.js figures feel integrated into the article.

### Pattern

```html
<div class="chart-grid">
  <div class="chart-card">
    <h3>Original-contact retention by design</h3>
    <canvas id="chart-survival" height="280"></canvas>
  </div>
</div>
```

### Layout

- `.chart-grid`: two columns on desktop, one column on narrow screens.
- `.chart-card-wide`: spans both columns.
- Canvas max height: approximately 280px for standard cards, 200px for wide summary charts.

### Guidance

Use chart cards for:

- ranked bar charts;
- grouped comparisons;
- histograms;
- scatter plots;
- before/after comparisons.

Keep chart titles short. Put the interpretation in body text or a callout, not in the title.

---

## 12. Callouts

### Base callout

```html
<div class="callout">
  <div class="callout-title">Title</div>
  <p>Interpretive note...</p>
</div>
```

### Insight callout

```html
<div class="callout callout-insight">
  <div class="callout-title">Wet-lab perspective</div>
  <p>...</p>
</div>
```

### Styling

- White base callout.
- Insight callout uses `--accent-light`.
- Left border in `--accent`.
- Compact title.
- Smaller body text.

### Usage rule

Use callouts for interpretation, not for caveats. The best callouts translate computational output into practical screening, triage, or experimental-design implications.

Recommended recurring labels:

- `Wet-lab perspective`
- `Design triage implication`
- `Workflow implication`
- `What this adds`
- `Practical readout`

---

## 13. Comparison blocks

### Purpose

Use `.comparison-row` for side-by-side before/after or model-vs-model comparisons.

### Pattern

```html
<div class="comparison-row">
  <div class="comparison-col">
    <h3>Pre-MD</h3>
    <div class="val">77.0%</div>
    <div class="context">contact native PD-L1 interface residues</div>
  </div>
  <div class="comparison-col">
    <h3>Post-MD</h3>
    <div class="val">70.3%</div>
    <div class="context">contact native PD-L1 interface residues</div>
  </div>
</div>
```

### Use when

A comparison block is better than a table when the reader needs to absorb the contrast quickly rather than inspect many rows.

Good uses:

- pre/post;
- upstream/downstream;
- RFdiffusion/Boltz;
- static/trajectory;
- design/developability.

---

## 14. Figure and heatmap cards

### Purpose

Use these for rendered images, heatmaps, cluster plots, or precomputed analysis figures.

### Pattern

```html
<div class="heatmap-design">
  <h3>Example title — <code>design_id</code></h3>
  <div class="meta">100 aa · clusterA · ipTM 0.92 · 83% contact survival</div>
  <img src="..." alt="...">
</div>
```

### Styling

- White card.
- Border and large radius.
- Metadata line in monospace.
- Image gets its own border and white background.
- Figure captions use `.fig-caption`.

### Guidance

Use this pattern when the image is an analytical artifact. For decorative or conceptual images, use a simpler figure container.

---

## 15. Interactive molecular viewer

### Purpose

The `.patch-viewer` component is the most complex reusable pattern. It supports interactive 3D exploration with controls, metadata, legend, and navigation.

### Component structure

```html
<div class="patch-viewer">
  <div class="patch-viewer-toolbar">
    <div class="patch-control">
      <label>Design</label>
      <select>...</select>
    </div>
    <div class="patch-control">
      <label>View</label>
      <select>...</select>
    </div>
    <div class="patch-toggle-row">
      <label class="patch-toggle"><input type="checkbox"> Show target</label>
    </div>
  </div>

  <div class="patch-viewer-stage">
    <div id="binder-patch-viewer"></div>
    <div class="patch-loading">Loading...</div>
  </div>

  <div class="patch-viewer-nav">
    <button class="patch-nav-button">Previous</button>
    <div class="patch-design-label">design_id</div>
    <button class="patch-nav-button">Next</button>
  </div>

  <div class="patch-meta">...</div>
  <div class="patch-legend">...</div>
  <div class="patch-error">...</div>
</div>
```

### Layout details

- Toolbar: two-column grid on desktop, one-column on mobile.
- Stage height: 520px desktop, 420px mobile.
- Metadata grid: four columns desktop, two columns mobile.
- Controls use small uppercase labels.
- Buttons are minimal white controls with border and hover background.

### Reuse guidance

Use this viewer pattern only when interactivity adds clear value. Otherwise, use static images or short videos. The viewer should support a specific analytical task, such as comparing interface patches, ranking constructs, or inspecting persistent contacts.

---

## 16. Footer

### Pattern

```html
<div class="page-footer">
  <p>...</p>
  <a href="...">...</a>
</div>
```

### Guidance

Keep the footer quiet. Use it for previous/next navigation, repository links, or short page provenance. Do not put major conclusions here.

---

## 17. Responsive behavior

Current responsive breakpoints:

```css
@media (max-width: 700px) {
  .chart-grid { grid-template-columns: 1fr; }
  .patch-viewer-toolbar { grid-template-columns: 1fr; }
  .patch-viewer-stage { height: 420px; }
  .patch-meta { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 600px) {
  .stats-row { grid-template-columns: repeat(2, 1fr); }
  .comparison-row { grid-template-columns: 1fr; }
}
```

### Practical guidance

For future pages:

- Keep major grids to one or two columns.
- Collapse two-column comparisons on mobile.
- Keep chart cards readable at 320–390px width.
- Avoid fixed-width tables unless they can scroll or remain compact.
- Keep molecular viewers tall enough to be useful but not taller than the viewport.

---

## 18. Content-design rules

### Page formula

A strong page using this system should follow this sequence:

1. Series banner.
2. Interpretive title and precise subtitle.
3. Recap block.
4. Headline stat cards.
5. Workflow/method setup.
6. Parameter table.
7. Result section with chart cards.
8. Interpretive callout.
9. Comparison section.
10. Figure/viewer section if needed.
11. Practical triage implication.
12. Quiet footer.

### Voice

Use expert-facing, operational language.

Good:

> The persistent post-MD contact networks are larger than the starting contact sets, indicating local interface reorganization and consolidation rather than widespread disengagement.

Avoid:

> This proves the binders work experimentally.

Avoid also:

> This does not calculate every possible physical phenomenon and should not be interpreted without extensive experimental caveats.

The intended audience is scientifically literate. Focus on what the analysis does and how it changes the screening decision.

---

## 19. Component reuse checklist

Before publishing a new page, check:

- [ ] Does the page use the same root color and font tokens?
- [ ] Is the title short and interpretive?
- [ ] Does the subtitle carry the technical scope?
- [ ] Is there exactly one top recap block?
- [ ] Are there 3–4 useful stat cards?
- [ ] Are parameters shown in a compact table when needed?
- [ ] Are charts placed inside chart cards?
- [ ] Are callouts used for practical interpretation?
- [ ] Are comparison blocks used instead of dense tables where possible?
- [ ] Does the page collapse cleanly on mobile?
- [ ] Are molecular viewers used only when they add real value?
- [ ] Is the page quiet, readable, and not overdecorated?

---

## 20. Minimal starter template

```html
<link href="https://fonts.googleapis.com/css2?family=Source+Serif+4:ital,wght@0,400;0,600;1,400&family=DM+Sans:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<div class="page">

  <div class="series-banner">
    <span class="tag">Page Topic</span>
    <span class="sep">|</span>
    <span style="font-size:.85rem;color:var(--tx2)">The wet-lab scientist's guide to computational protein design</span>
    <span class="sep">|</span>
    <a href="../PreviousPage/">← Previous</a>
  </div>

  <h1>Part N: Interpretive Title</h1>
  <p class="subtitle">Precise technical subtitle</p>

  <div class="recap">
    <p><strong>Previously:</strong> Previous step. This page asks: <em>current question.</em></p>
  </div>

  <div class="stats-row">
    <div class="stat-card"><div class="num">28</div><div class="label">Designs screened</div></div>
    <div class="stat-card"><div class="num">70%</div><div class="label">Pass rate</div></div>
    <div class="stat-card"><div class="num">0.92</div><div class="label">Top score</div></div>
    <div class="stat-card"><div class="num">4</div><div class="label">Priority hits</div></div>
  </div>

  <h2>Section heading</h2>
  <p>Body text...</p>

  <div class="callout callout-insight">
    <div class="callout-title">Design triage implication</div>
    <p>Practical interpretation...</p>
  </div>

</div>
```

---

## 21. CSS token block for reuse

```css
:root {
  --bg:#faf9f6;
  --bg2:#f0eeea;
  --bg3:#e6e3dc;
  --tx:#1a1a18;
  --tx2:#5a5850;
  --tx3:#8a8878;
  --accent:#1d6b52;
  --accent2:#0f4a38;
  --accent-light:#e1f0ea;
  --coral:#c85a3a;
  --coral-light:#faeae4;
  --blue:#2e6da4;
  --blue-light:#e6f0fa;
  --amber:#b07818;
  --amber-light:#faf0da;
  --purple:#6b4c9a;
  --purple-light:#ede6f5;
  --mono:"JetBrains Mono", monospace;
  --sans:"DM Sans", system-ui, sans-serif;
  --serif:"Source Serif 4", Georgia, serif;
  --radius:6px;
  --radius-lg:10px;
}
```
