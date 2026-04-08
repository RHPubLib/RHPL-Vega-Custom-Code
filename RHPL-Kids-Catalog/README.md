# RHPL Kids Catalog

**Kids Catalog: Developmentally-Appropriate Discovery Through Themed Visual Navigation**

> **2026 Clarivate Library Innovation Awards — Finalist**

Rochester Hills Public Library's Kids Catalog is a themed discovery interface built on
Vega Discover, designed specifically for how children actually explore and select
materials — not how adults search for them. It serves children from pre-readers through
teenagers, running as both a public web catalog accessible from home and a series of
in-library touch kiosks deployed throughout the building.

Where the main library catalog expects users to search by title, author, or subject
heading, the Kids Catalog meets children where they are: visual subject browsing through
images of dinosaurs, princesses, and planes for younger readers; series and character
navigation for children who already know what they love. The result is a catalog that
works for a four-year-old slapping a touchscreen and a twelve-year-old looking for the
next book in a series — at the same time, in the same space.

**Browse it live:**

| Page | URL | Audience |
|---|---|---|
| Kids Catalog Home | [kids.rhpl.org](https://kids.rhpl.org/) | All ages — recommended public link |
| Subject Browsing | [kidssubject.rhpl.org](https://kidssubject.rhpl.org/) | Pre-readers and early readers — image-based subject navigation |
| Series Browsing | [kidsseries.rhpl.org](https://kidsseries.rhpl.org) | Confident readers — character and series navigation |
| In-Library Kiosk | [mbkids-rhpl.na3.iiivega.com](https://mbkids-rhpl.na3.iiivega.com) | Stripped-down in-building kiosk experience |

---

## What's in This Folder

| File / Folder | Contents |
|---|---|
| `Header.html` | Kiosk CSS: removes login UI, bookshelf, cookie banners; adds Back/Home buttons; injects RHPL logo |
| `Footer.html` | Kiosk JavaScript: image-click routing, 60-second inactivity timer, link containment |
| `Kids-Home/` | Deployed kiosk — catalog homepage with New Books, DVDs, and Picture Books routing |
| `Kids-Series/` | Deployed kiosk — series browsing page with subject-to-series routing |
| `Kids-Subject/` | Deployed kiosk — subject browsing page with keyword search routing |

---

## Project Overview

Rochester Hills Public Library partnered with Clarivate in 2024 to pioneer a themed
kids catalog using Vega Discover, creating a developmentally-appropriate discovery
interface for children through teenagers. This implementation combined professional
Early Childhood Literacy expertise with intentional technical design to reduce barriers
to independent browsing and serve both in-library kiosk users and home patrons.

**Goals:**
- Create a developmentally-appropriate discovery interface aligned with how children
  actually think and explore
- Reduce barriers to independent browsing and material selection across a wide age
  range (pre-readers through teens)
- Serve both high-traffic in-library kiosk users and home patrons
- Design for reproducibility to benefit the broader library community

**Timeline:**

| Year | Milestone |
|---|---|
| 2024 | Launch of kids-themed catalog with Clarivate collaboration |
| 2024 | Multi-departmental user testing with children and parents across age ranges |
| 2024–present | Continuous improvement based on usage data and patron feedback |
| 2025 | Presented *"Modding Vega Discover: How I Stopped Using Defaults and Learned to Love Customization"* at IUG 2025, Denver |
| 2026 | Youth Services redesign incorporating additional kiosks based on patron demand |
| Q2 2026 | Launch of two additional themed catalogs (Innovative Items and Bookmobile-specific) |

---

## The Challenge and Opportunity

Traditional library catalogs are designed for adult search behavior and literacy levels,
creating barriers for children's natural discovery patterns. RHPL recognized an
opportunity to leverage Vega Discover's theming capabilities while applying professional
child development expertise to create an interface that respects how children across
developmental stages actually explore and select materials.

RHPL's high-traffic play zone leading to the Storytime room provided an ideal location
for testing whether a thoughtfully-designed interface could accommodate both intentional
navigation and exploratory interaction — including very young children who engage through
play rather than focused search.

---

## What Makes This Project Innovative

### Applied Professional Expertise

RHPL Youth Services Manager **Wendy Lehman's** Early Childhood Literacy background
directly informed the catalog's developmental design approach:

> *"Drawing on my background in early childhood education, I knew a traditional catalog
> search wouldn't meet the needs of our youngest patrons. Young children don't look for
> books by title or author — they think in pictures and concepts like dinosaurs,
> princesses, or monsters. While older children often come to the library with specific
> characters or a favorite series in mind. Our user testing showed that visual browsing
> helped our youngest and newest readers feel successful, while organizing by series
> supported children who were ready to choose more independently. One of my favorite
> moments was seeing parents and children use the kiosk together, talking, pointing, and
> deciding side by side. It turned book finding into a shared moment of discovery instead
> of just a task."*
>
> — Wendy Lehman, Youth Services Manager, Rochester Hills Public Library

This expertise-driven approach distinguished RHPL's implementation:

| Principle | Application |
|---|---|
| **Evidence-based developmental differentiation** | Separated visual subject browsing (images of dinosaurs, princesses, planes, basketball — for lower reading levels) from series navigation (for higher reading levels) based on user testing feedback |
| **Inclusive interaction design** | Interface accommodates both focused navigation and exploratory "slapping" — recognizing that discovery happens through play for youngest users |
| **Multi-departmental collaboration** | User testing involved Youth Services, Circulation, IT, and patron families, creating a structured feedback loop that informed both RHPL iterations and input to Clarivate for platform development |
| **Strategic placement** | Integration with play zone rather than traditional reference desk location proved as crucial as interface design |

### Community Thought Leadership

RHPL built this to demonstrate possibilities and make implementation reproducible:

- Presented *"Modding Vega Discover: How I Stopped Using Defaults and Learned to Love Customization"* at IUG 2025 (Denver)
- Clarivate regularly refers libraries to RHPL for assistance with Vega Discover Premium customization questions
- Direct consultation with multiple libraries on custom code development
- RHPL's approach adopted by libraries like Valley Library Consortium for their kids catalogs
- RHPL's header/footer customization code widely used across IUG community
- Open sharing model enables libraries to implement themed catalog variations using their own approaches

### Technical Innovation

Chrome OS Flex kiosk deployment provides a secure, cost-effective technical model:

| Component | Details |
|---|---|
| Hardware | Refurbished Dell Optiplex with touchscreen — under $200/unit |
| OS | Chrome OS Flex — free for Google Nonprofit customers |
| vs. traditional kiosk hardware | Eliminates $2,000–$5,000/unit cost |
| Management | Google Admin Console — centralized fleet management across all devices |

For the complete deployment walkthrough, see the IUG 2026 pre-conference presentation:

**[Vega Kiosks: Creating, Deploying & Managing Through Google](https://docs.google.com/presentation/d/1FfcUfYAUmDG5X7S0zuxtOrt6WyJUMFBTdcCUFG6egf4/edit?usp=sharing)**
*IUG 2026 Pre-Conference | Speed Geeking, 15 min | Derek Brown, Director of IT*

---

## Measurable Impact

### Usage Metrics

*In-library and home access combined:*

| Metric | Value |
|---|---|
| Views in most recent 30-day period | 13,816 (distinct from 82,761 views on main catalog) |
| Views in 2025 from outside the building | 29,117 — strong home patron adoption |
| Average engagement time | 3m 37s |

*Most popular subject themes, past year:*

| Subject | Views |
|---|---|
| Monsters | 4,243 |
| Dinosaurs | 3,694 |
| Princesses | 3,339 |
| Dogs | 3,095 |
| Planes | 2,834 |

These theme preferences validate the developmental approach: high engagement with visual,
theme-based navigation designed for lower reading levels reflects quintessential early
childhood interests.

### Behavioral Impact

Parent-child co-discovery emerged as the primary interaction pattern — the kiosk became
a collaborative engagement point rather than just a child-only tool. Sustained high usage
in the play area environment shows that when patrons are present, kids and parents are
typically actively engaging together on the device.

This unexpected collaborative pattern has driven patron demand for expansion throughout
the building, directly influencing architectural planning for the 2026 Youth Services
redesign to incorporate additional kiosk stations.

### Community Impact

- Libraries like Valley Library Consortium adopted RHPL's kids catalog customization approach
- Multiple libraries implementing their own themed catalog variations inspired by RHPL's demonstration of possibilities
- RHPL's header/footer customization code adopted across IUG community
- Clarivate regularly refers libraries to RHPL for Vega Discover Premium customization assistance

### Expansion Validation

Success of the kids catalog model led directly to Q2 2026 launch of two additional
themed catalogs:

- **Innovative Items Catalog** — highlighting unique and specialized materials
- **Bookmobile-specific catalogs** — extending the themed approach to mobile services

---

## Sustainability and Scalability

### Demonstrated Replicability

RHPL designed this implementation from the start for easy reproduction by other libraries.

*Cost-effective technical model:*
- Chrome OS Flex deployment (free for Google Nonprofit customers)
- Refurbished Dell Optiplex hardware: under $200 per unit including touchscreen
- 11 kiosks throughout RHPL demonstrate scalability
- Eliminates traditional kiosk hardware costs while providing a secure, maintainable environment

*Community adoption evidence:*
- Valley Library Consortium and other libraries implementing themed approaches
- RHPL's customization code openly shared and widely adopted
- Clarivate regularly forwards libraries to RHPL for implementation assistance
- IUG 2025 conference presentation provided framework for community replication

### Lessons Learned That Others Can Apply

1. **Patron demand validates the approach** — enthusiasm exceeded expectations: not only high
   in-library usage, but patrons actively seeking home access and requesting more kiosks
   throughout the building, directly influencing architectural planning for 2026 redesign
2. **Methodology is scalable across use cases** — success with kids catalog led to Q2 2026
   expansion to Innovative Items Catalog and Bookmobile-specific themed catalogs
3. **Cross-departmental collaboration is essential** — user testing involving multiple RHPL
   departments and engaging both children and parents was critical to understanding what
   encourages discovery and sustains engagement
4. **Child development expertise must drive design decisions** — professional Early Childhood
   Literacy background was crucial to evidence-based decisions like separating visual
   navigation (lower reading levels) from series navigation (higher reading levels)
5. **Strategic placement equals interface design in importance** — high-traffic play zone
   location proved as crucial as interface design for engagement and discovery
6. **Design for exploration, not just navigation** — accommodating "exploratory slappers"
   (very young children engaging through play) alongside focused users created an inclusive
   experience that serves a wider developmental range

---

## Inclusion, Accessibility, and Mission Alignment

### Developmental Accessibility

The kids catalog reduces barriers for children across the full developmental spectrum:

- **Visual subject browsing** serves pre-readers and emerging readers who think in themes
  and images rather than text-based categories
- **Series navigation** provides clear pathways for more confident readers who want to
  follow favorite characters and storylines
- **Exploratory interaction design** accommodates youngest children who discover through
  play rather than focused search
- **Parent-child collaboration** creates shared discovery experiences that support literacy
  development and family engagement

Accessibility here isn't just about physical access — it's about cognitive and developmental
appropriateness. By respecting how children actually think and explore at different stages,
we remove barriers that traditional catalog interfaces create.

### Equity Through Technology

- **Home access** (29,117 views in 2025 from outside the building) extends
  developmentally-appropriate discovery beyond library hours and for families who cannot
  visit in person
- **Cost-effective technical model** (under $200/unit with Chrome OS Flex) makes
  replication financially accessible to libraries of all budget sizes
- **Open sharing of customization code** provides community benefit and enables other
  libraries to implement similar approaches regardless of their technical capacity

### Strategic Mission Alignment

This project directly supports RHPL's commitment to digital-first, patron-centered
transformation:

- **Patron-driven innovation** — user testing with families and continuous refinement
  based on usage data puts patron needs at the center of design
- **Community leadership** — open sharing model, IUG presentation, and assistance to
  other libraries positions RHPL as a thought leader
- **Cost stewardship** — leveraging Google Nonprofit benefits and refurbished hardware
  demonstrates responsible resource management
- **Service expansion** — success model scaling to Innovative Items and Bookmobile
  catalogs shows a sustainable approach to innovation

---

## Recognition & Presentations

- **2026 Clarivate Library Innovation Awards — Finalist** (all global entries)
- **[Vega Kiosks: Creating, Deploying & Managing Through Google](https://docs.google.com/presentation/d/1FfcUfYAUmDG5X7S0zuxtOrt6WyJUMFBTdcCUFG6egf4/edit?usp=sharing)** — IUG 2026 Pre-Conference, Chicago (April 12, 2026)
- **[Vega in Action: A Community Showcase of Customer Implementations](https://docs.google.com/presentation/d/1gTJiUCmVT9UCMEIrZxtuB7wvAZNHmb-0kneuxeNqOD8/edit?usp=sharing)** — IUG 2026 Annual Conference, Chicago (co-presented with Sarah Kasprzak, London Public Library)
- *"Modding Vega Discover: How I Stopped Using Defaults and Learned to Love Customization"* — IUG 2025, Denver
- Valley Library Consortium adopted RHPL's kids catalog approach for their implementation
- Clarivate regularly refers libraries to RHPL for Vega Discover Premium customization assistance

---

## Customizing the Kiosk Code

### Add or change image links (`Footer.html`)

```js
const imgMyNewImage = document.querySelector('img[src*="YourImageFragment"]');
if (imgMyNewImage) {
    imgMyNewImage.addEventListener('click', function() {
        window.location.href = 'https://mbkids-rhpl.na3.iiivega.com/search?query=*&...';
    });
}
```

### Adjust the inactivity timer (`Footer.html`)

```js
inactivityTimer = setTimeout(() => {
    window.location.href = HOME_URL;
}, 60000);  // ← milliseconds
```

### Change button colors (`Header.html`)

```css
#b-back { background-color: #6f263d; }  /* RHPL burgundy — replace with your brand color */
#b-home { background-color: #6f263d; }
```

---

## Dependencies

| Dependency | Source |
|---|---|
| Font Awesome 5.15.4 | [cdnjs.cloudflare.com](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css) |
| Lato (all weights) | [Google Fonts](https://fonts.google.com/specimen/Lato) |
| Google Analytics | Not included — add your own GA4 tag if needed |
| RHPL logo image | Hosted at `static.wixstatic.com` — replace with your own image URL |
| III Vega platform | Injected into Vega; relies on its DOM structure |
