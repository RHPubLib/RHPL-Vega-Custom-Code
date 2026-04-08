# RHPL Discover

Custom HTML/CSS/JavaScript for the main RHPL Vega Discover catalog.

**Live:** [discover.rhpl.org](https://discover.rhpl.org/) | Vega instance: [rhpl.na3.iiivega.com](https://rhpl.na3.iiivega.com)

This is the full-featured customization for RHPL's public-facing catalog — account portal
tweaks, teal branding, multi-mode search bar (catalog / website / events), and live hours
display. It is the most complete RHPL Vega customization and the best reference for CSS
patterns used across all properties.

---

## What It Does

### Header (`Header.html`)

- **Typography**: Lato font (all weights) from Google Fonts
- **Brand color**: RHPL teal `#006980` applied to login button, nav icons, and interactive elements
- **Account portal**: CSS fixes for payment display and portal layout
- **UI cleanup**: Cookie banners, Vega default spacing, and nav chrome suppressed
- **Multi-mode search bar**: Dropdown for catalog / website / events with dynamic placeholder text

### Footer (`Footer.html`)

- **Hours display**: `normalSchedule` (Sunday–Saturday) with `UnavailableDates` overrides
  for holidays and special closures through 2027
- **Search routing**:
  - **Catalog** → `rhpl.na3.iiivega.com/search?query=...`
  - **Website** → `rhpl.org/?s=...`
  - **Events** → `rhpl.org/program-calendar/#/events/?keyword=...`

---

## Customization Notes

### Update brand color (`Header.html`)

Replace `#006980` (RHPL teal) with your library's brand color. It appears in multiple
CSS rules — use Find & Replace.

### Update hours (`Footer.html`)

```js
const normalSchedule = ["Sun hours", "Mon hours", ..., "Sat hours"];

const UnavailableDates = [
    ["MM-DD-YYYY", "H:MMam-H:MMpm"],  // special hours
    ["MM-DD-YYYY", "Closed"],          // closed day
];
```

### Update catalog URL (`Footer.html`)

Replace `rhpl.na3.iiivega.com` with your Vega instance URL.

---

## Dependencies

| Dependency | Source |
|---|---|
| Font Awesome 5.15.4 | [cdnjs.cloudflare.com](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css) |
| Lato (all weights) | [Google Fonts](https://fonts.google.com/specimen/Lato) |
| Google Analytics | Not included — add your own GA4 tag if needed |
| III Vega platform | Injected into Vega; relies on its DOM structure |
