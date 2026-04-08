# RHPL IIC Catalog

Custom HTML/CSS/JavaScript for the RHPL Innovative Items Collection (IIC) — a Library
of Things catalog featuring tools, electronics, musical instruments, art supplies,
experience passes, and more. The IIC runs as both a full patron-facing web catalog
and a stripped-down in-library kiosk.

**Two experiences, one catalog:**

| Experience | URL | Description |
|---|---|---|
| Full patron experience | [iic.rhpl.org](https://iic.rhpl.org/) | Complete browsing with top navigation bar — for regular patron use at home or in-library |
| In-library kiosk | [mbiic-rhpl.na3.iiivega.com](https://mbiic-rhpl.na3.iiivega.com) | Stripped-down kiosk: no login UI, image-click routing to collections, 60-second inactivity timer |

---

## What's in This Folder

| File / Folder | Contents |
|---|---|
| `Header.html` | Kiosk CSS: removes login/account UI, cookie banners; adds Back/Home buttons; hours display and multi-mode search bar |
| `Footer.html` | Kiosk JavaScript: image-click routing to 8 IIC collections, 60-second inactivity timer, link containment |
| `Library-of-Things/` | Full example kiosk implementation for the original Library of Things deployment |

---

## Kiosk Deployment

For a complete walkthrough of how RHPL creates, deploys, and manages kiosks using
Chrome OS Flex and Google's device management tools, see the IUG 2026 pre-conference
presentation:

**[Vega Kiosks: Creating, Deploying & Managing Through Google](https://docs.google.com/presentation/d/1FfcUfYAUmDG5X7S0zuxtOrt6WyJUMFBTdcCUFG6egf4/edit?usp=sharing)**
*IUG 2026 Pre-Conference | Speed Geeking, 15 min | Derek Brown, Director of IT*

For a technical deep-dive into how the kiosk JavaScript works, see
[`vega-clean-kiosk-overview.md`](../vega-clean-kiosk-overview.md).

### Hardware Model

RHPL runs **11 catalog kiosks** on a cost-effective, replicable platform:

| Component | Details |
|---|---|
| Hardware | Refurbished Dell Optiplex with touchscreen |
| Cost | Under $200/unit including touchscreen |
| OS | Chrome OS Flex — free for Google Nonprofit customers |
| vs. traditional kiosk hardware | Eliminates $2,000–$5,000/unit cost |

---

## What the Code Does

### Header (`Header.html`)

- **Hours display**: Shows current library hours using `normalSchedule` (Sunday–Saturday)
  with `UnavailableDates` overrides for holidays and special closures
- **Multi-mode search bar**: Routes searches to catalog, RHPL website, or events calendar
- **UI cleanup**: Removes login/account UI, cookie banners, and Vega default chrome
- **Navigation buttons**: Fixed Back and Home buttons for touch navigation

### Footer (`Footer.html`)

- **Image click routing** via `imageLinks` array — maps banner image filename fragments
  to collection-filtered searches at `locationId=15`, `materialTypeId=23`:

  | Image fragment | Collection | `collectionId` |
  |---|---|---|
  | `WQ2r4` | All IIC items | *(no collection filter)* |
  | `ArtsCrafts` | Arts & Crafts | 130 |
  | `Electronics` | Electronics | 131 |
  | `Experiences` | Experiences | 132 |
  | `Household` | Household | 134 |
  | `Tools` | Tools | 137 |
  | `Music` | Music | 135 |
  | `ngHdl` | *(additional collection)* | 136 |

- **Inactivity timer**: 60-second countdown; starts on first interaction from home page,
  starts immediately on all other pages
- **Link containment**: Removes `target="_blank"` from all links via `MutationObserver`
  and `history` patching

---

## Building a New Kiosk

For a clean starting point with no RHPL-specific content, see
**[New-Kiosk-Template/](../New-Kiosk-Template/)** in the repository root.

---

## Customization Notes

### Update hours (`Header.html`)

```js
const normalSchedule = ["Sun hours", "Mon hours", ..., "Sat hours"];

const UnavailableDates = [
    ["MM-DD-YYYY", "H:MMam-H:MMpm"],  // special hours
    ["MM-DD-YYYY", "Closed"],          // closed day
];
```

### Add or change image links (`Footer.html`)

```js
const imageLinks = [
    { src: 'YourImageFragment', url: 'https://mbiic-rhpl.na3.iiivega.com/search?query=*&locationIds=X&collectionIds=Y&materialTypeIds=23' },
];
```

### Adjust the inactivity timer (`Footer.html`)

```js
inactivityTimer = setTimeout(() => {
    window.location.href = HOME_URL;
}, 60000);  // ← milliseconds
```

---

## Dependencies

| Dependency | Source |
|---|---|
| RHPL hours script | `rhpl.org/wp-content/uploads/2023/04/s-hours.js` — replace or remove |
| RHPL website search script | `rhpl.org/wp-content/uploads/2023/05/website-search.js` — remove if not using website search |
| III Vega platform | Injected into Vega; relies on its DOM structure |
