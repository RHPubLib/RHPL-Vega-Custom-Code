# RHPL Vega Custom Code

Community resources from **Rochester Hills Public Library (RHPL)** for libraries using the
III Vega Discover catalog platform. This repository contains the custom HTML/CSS/JavaScript
that powers three live RHPL catalog properties — a fully-branded public discovery layer,
a developmentally-appropriate kids catalog, and a Library of Things kiosk — shared openly
so other libraries can learn from, adapt, and reuse what we've built.

> **2026 Clarivate Library Innovation Awards — Finalist** for the RHPL Kids Catalog.
> See [RHPL-Kids-Catalog/](RHPL-Kids-Catalog/) for the full project story.

---

## What This Is

RHPL uses Vega Discover's custom header and footer injection to transform our catalog
instances far beyond Vega's out-of-the-box appearance. Each property has its own
design language, audience, and behavior — but all share common patterns for UI cleanup,
inactivity handling, and touch-friendly navigation that other libraries can apply to
their own Vega instances.

This is the same code running live on RHPL's catalogs today. Browse to any of the URLs
below to see it in action.

**Vega Discover — Main Catalog**
- [discover.rhpl.org](https://discover.rhpl.org/) — RHPL's public catalog

**Kids Catalog**
- [kids.rhpl.org](https://kids.rhpl.org/) — Kids catalog home
- [kidssubject.rhpl.org](https://kidssubject.rhpl.org/) — Visual subject browsing for younger readers
- [kidsseries.rhpl.org](https://kidsseries.rhpl.org) — Series and character browsing
- [mbkids-rhpl.na3.iiivega.com](https://mbkids-rhpl.na3.iiivega.com) — In-library kiosk experience

**IIC Catalog**
- [iic.rhpl.org](https://iic.rhpl.org/) — Full patron-facing IIC catalog
- [mbiic-rhpl.na3.iiivega.com](https://mbiic-rhpl.na3.iiivega.com) — In-library IIC kiosk experience

---

## What This Repository Contains

```
RHPL-Vega-Custom-Code/
├── README.md                    ← This file
├── vega-clean-kiosk-overview.md ← Technical deep-dive: how the kiosk code works
│
├── RHPL-Discover/               ← Vega Discover — discover.rhpl.org
│   ├── README.md
│   ├── Header.html
│   └── Footer.html
│
├── RHPL-Kids-Catalog/           ← Kids Catalog & Kiosk — kids.rhpl.org
│   ├── README.md                ← Clarivate finalist story, design approach, usage metrics
│   ├── Header.html
│   ├── Footer.html
│   ├── Kids-Home/               ← Kiosk example: catalog homepage
│   ├── Kids-Series/             ← Kiosk example: series browsing
│   └── Kids-Subject/            ← Kiosk example: subject browsing
│
├── RHPL-IIC-Catalog/            ← IIC Catalog & Kiosk — iic.rhpl.org
│   ├── README.md                ← IIC overview + kiosk deployment reference
│   ├── Header.html
│   ├── Footer.html
│   └── Library-of-Things/      ← Full annotated kiosk example
│
└── New-Kiosk-Template/          ← Clean base template for new kiosk deployments
    ├── README.md
    ├── Header.html
    └── Footer.html
```

---

## IUG 2026 Presentations — Chicago

RHPL presented both of these sessions at IUG 2026 in Chicago. If you found this
repository through one of those presentations — welcome.

### [Vega Kiosks: Creating, Deploying & Managing Through Google](https://docs.google.com/presentation/d/1FfcUfYAUmDG5X7S0zuxtOrt6WyJUMFBTdcCUFG6egf4/edit?usp=sharing)

*IUG 2026 Pre-Conference — The Great ILS-Data Pre-Conference: Quick Lessons With Your Peers
| April 12, 2026 | Speed Geeking, 15 min*

**Derek Brown**, Director of IT — Rochester Hills Public Library

<a href="https://docs.google.com/presentation/d/1FfcUfYAUmDG5X7S0zuxtOrt6WyJUMFBTdcCUFG6egf4/edit?usp=sharing"><img src="docs/iug2026-vega-kiosks-slide.png" width="520" alt="Vega Kiosks: Creating, Deploying & Managing Through Google — IUG 2026 Pre-Conference"></a>

A practical walkthrough of how RHPL creates, deploys, and manages Vega catalog kiosks
using Chrome OS Flex and Google's device management tools — from hardware selection
through fleet management across 11 devices. Presented alongside the Clarivate Library
Innovation Awards Finalist recognition.

### [Vega in Action: A Community Showcase of Customer Implementations](https://docs.google.com/presentation/d/1gTJiUCmVT9UCMEIrZxtuB7wvAZNHmb-0kneuxeNqOD8/edit?usp=sharing)

*IUG 2026 Annual Conference — Chicago*

- **Derek Brown**, Director of IT — Rochester Hills Public Library
- **Sarah Kasprzak**, ILS Solutions Specialist — London Public Library

<a href="https://docs.google.com/presentation/d/1gTJiUCmVT9UCMEIrZxtuB7wvAZNHmb-0kneuxeNqOD8/edit?usp=sharing"><img src="docs/iug2026-vega-in-action-slide.png" width="520" alt="Vega in Action: A Community Showcase of Customer Implementations — IUG 2026 Chicago"></a>

A community showcase of real-world Vega Discover implementations from libraries across
the IUG network, including RHPL's themed kiosk and catalog work. If you're exploring
what's possible with Vega customization, this presentation shows how the patterns in
this repository translate into live patron experiences.

---

## Using This at Your Library

The CSS class names and JavaScript patterns in these files target Vega's generated DOM.
Vega's class names (`.css-xxxxx`) can change across platform updates — if something
stops working after a Vega update, inspect the current DOM and update the relevant
selector.

**RHPL-specific values to replace before deploying:**
- Catalog URLs: `rhpl.na3.iiivega.com`, `mbkids-rhpl.na3.iiivega.com`, `mbiic-rhpl.na3.iiivega.com`
- Brand colors: RHPL teal `#006980` or burgundy `#6f263d`
- Google Analytics: not included in these files — add your own GA4 tag if needed
- Hours schedule: `normalSchedule` array and `UnavailableDates` entries
- Image filename fragments in `imageLinks` or individual `querySelector` calls
- `locationIds`, `collectionIds`, `materialTypeIds` in search URLs

---

## Contributing

Pull requests welcome. If you've adapted this code for your library, built on these
patterns, or found something that needed fixing — submit a PR or open an issue.

---

Rochester Hills Public Library — Rochester Hills, Michigan
[rhpl.org](https://rhpl.org)
