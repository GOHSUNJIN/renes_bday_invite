# reneseal

A secret invitation site styled as a classified intelligence document. Deployed at `reneseal.vercel.app`.

## Screens

| Screen | What it does |
|--------|-------------|
| **Landing** | Classified dossier cover with live T-minus countdown to Aug 16 |
| **Briefing** | Three-page case file — rendezvous details, full itinerary, and the question |
| **Celebrate** | Confetti burst, floating hearts, confirmed date countdown |

## File structure

```
├── index.dc.html   — app template + component logic
├── styles.css      — keyframe animations + base CSS
├── support.js      — DC runtime (generated, do not edit)
├── vercel.json     — Vercel routing
└── assets/         — local images
```

## DC Framework

The app uses a custom DC (Declarative Component) framework. `support.js` is the compiled runtime built on React.

**Template syntax** (inside `<x-dc>`)

| Syntax | Purpose |
|--------|---------|
| `{{ expression }}` | Render a value from `renderVals()` |
| `<sc-if value="{{ bool }}">` | Conditional block |
| `<sc-for list="{{ arr }}" as="item">` | Loop |
| `<helmet data-dc-atomics>` | Inject into `<head>` (deduped) |
| `<script type="text/x-dc" data-dc-script>` | Component class |

**Component class** extends `DCLogic` and must implement `renderVals()` which returns a flat object of values the template can read.

## Deploying

Hosted on Vercel. Push to `master` and it auto-deploys. No build step — static files served directly.
