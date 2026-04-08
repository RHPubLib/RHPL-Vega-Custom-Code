# Vega Kiosk Custom Code

Custom HTML/CSS/JS injected into the III Vega library catalog to adapt it for kiosk use. It suppresses account/login UI, adds touch-friendly navigation buttons, maps homepage images to catalog searches, enforces an inactivity timeout, and prevents links from opening new tabs.

---

## What It Does

### 1. UI Cleanup (CSS)
Hides and adjusts Vega's default UI elements that are inappropriate for a public kiosk:

| Target | What it does |
|---|---|
| `.fixed-bottom` | Hides Vega's persistent footer bar |
| `#user-panel` | Hides the login/account panel |
| `a[data-automation-id=login-forgot-my-passcode-link]` | Hides the "Forgot passcode" recovery link |
| `button[data-automation-id=btn-view-more]` | Hides "View All / View More" buttons (You may want to remove this if you like those buttons)|
| `.header > app-global-nav:nth-child(2)` | Removes the duplicate nav bar Vega injects |
| `body [class*='onetrust-pc-dark-filter']` | Hides the OneTrust cookie consent overlay |

Layout adjustments to fix spacing, max-widths, and scaling for the kiosk display:
- `container-fluid` max-width is uncapped globally, then re-capped at 1600px for the main content area
- Various Vega-generated class names (e.g. `.css-vmk2hm`, `.css-4k03bg`) are tweaked for spacing and image scale

### 2. Typography
- Sets the global font to **Lato** (loaded from Google Fonts), overriding Vega's defaults via `html *`, `.mat-typography`, and `html { font-size: 16px }`. Please choose a font that is suitable for your website style needs.
- Resets `letter-spacing` on `h3` and tightens `line-height` on `body`

### 3. Fixed Navigation Buttons
Two large, fixed-position buttons in the lower-left corner for touch navigation:

- **Back** (`#b-back`) — calls `window.history.back()` via a `javascript:` href
- **Home** (`#b-home`) — navigates to `/`

Both are styled in burgundy (`#6f263d`), scaled up 1.5x, and use Font Awesome icons.

---

## How It Works (JavaScript)

### Image Click Routing
```
imageLinks[] → DOM polling + MutationObserver → click → window.location.href
```
- A map (`imageLinks`) links homepage banner image filename fragments to specific catalog search URLs (filtered by `locationIds`, `materialTypeIds`, `collectionIds`).
- `addClickListenerToImage()` scans the DOM for matching `<img>` tags and attaches click handlers that redirect to the mapped URL after a 100ms delay.
- Because Vega lazy-renders content, the function is called:
  - On `DOMContentLoaded`
  - Every **500ms** via `setInterval` (fallback poller)
  - On any DOM mutation via `MutationObserver`
- Once all images have listeners, the poller and observer are stopped.

### Inactivity Timer
```
First interaction → startTimer() → resetTimer() → 60s timeout → redirect to /
```
- On the **home page** (`/`): the timer only starts after the first `click` or `touchstart`, so an idle kiosk doesn't immediately redirect itself.
- On **all other pages**: the timer starts immediately on page load.
- Any of these events resets the 60-second countdown: `mousemove`, `mousedown`, `keydown`, `touchstart`, `scroll`, `click`.
- After 60 seconds of inactivity, the page redirects to `HOME_URL` (`/`).

### New Window Link Fix
```
DOM sweep → strip target="_blank" → MutationObserver → strip on new nodes → history patch → strip after navigation
```
- Finds all `<a target="_blank">` links and removes the `target` attribute so links never open a new tab (critical for kiosk containment).
- Runs initial sweeps at 0, 500, 1500, and 3000ms after load.
- Patches `history.pushState` / `history.replaceState` to re-sweep at 200, 600, 1200, and 2500ms after each SPA navigation.
- A `MutationObserver` watches for newly added or modified links in real time.
- All actions are logged to the console with `[fix-blank]` prefixes for debugging.

---

## Dependencies
- [Font Awesome 5.15.4](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css) (CDN)
- [Lato font](https://fonts.google.com/specimen/Lato) (Google Fonts)
- Vega (III) catalog platform — this code is injected into it and relies on Vega's DOM structure
