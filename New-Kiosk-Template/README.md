# New Kiosk Template

A clean, RHPL-neutral base template for building a new Vega catalog kiosk from scratch.
No RHPL branding, URLs, or image links — just the working structure ready to customize.

For a full technical explanation of how every piece of this code works, see
[`vega-clean-kiosk-overview.md`](../vega-clean-kiosk-overview.md).

For a complete walkthrough of hardware selection, Chrome OS Flex deployment, and
Google device management at scale, see the IUG 2026 pre-conference presentation:
**[Vega Kiosks: Creating, Deploying & Managing Through Google](https://docs.google.com/presentation/d/1FfcUfYAUmDG5X7S0zuxtOrt6WyJUMFBTdcCUFG6egf4/edit?usp=sharing)**

---

## What's in This Folder

| File | Contents |
|---|---|
| `Header.html` | CSS: UI cleanup, Lato typography, fixed Back/Home navigation buttons |
| `Footer.html` | JavaScript: image-click routing, 60-second inactivity timer, `target="_blank"` link stripping |

---

## Quick Start

**1.** Log into your Vega admin panel and open the **Custom Header** settings.

**2.** Copy `Header.html` contents → paste into the **Header** field → Save.

**3.** Copy `Footer.html` contents → paste into the **Footer** field → Save.

**4.** Update the `imageLinks` array in `Footer.html` to match your banner images
(filename fragments are case-sensitive):

```js
const imageLinks = [
    { src: 'YourImageFragment', url: 'https://your-vega-instance.iiivega.com/search?...' },
];
```

**5.** Optional adjustments:

```js
// Inactivity timeout — default 60 seconds
}, 60000);
```

```css
/* Button color — replace with your brand color */
#b-back { background-color: #6f263d; }
#b-home { background-color: #6f263d; }
```

**6.** Verify: Back/Home buttons appear on all pages, links stay in the same tab,
idle non-home pages redirect after timeout, banner images navigate to correct searches,
login UI is not visible.

---

## Real-World Examples

See how the template was customized for RHPL's live deployments:

- **[RHPL-Kids-Catalog/](../RHPL-Kids-Catalog/)** — Kids catalog kiosk (multiple pages)
- **[RHPL-IIC-Catalog/](../RHPL-IIC-Catalog/)** — IIC / Library of Things kiosk with hours display and collection routing
- **[RHPL-IIC-Catalog/Library-of-Things/](../RHPL-IIC-Catalog/Library-of-Things/)** — Full annotated kiosk example

---

## Dependencies

| Dependency | Source |
|---|---|
| Font Awesome 5.15.4 | [cdnjs.cloudflare.com](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css) |
| Lato (all weights) | [Google Fonts](https://fonts.google.com/specimen/Lato) |
| III Vega platform | Injected into Vega; relies on its DOM structure |
