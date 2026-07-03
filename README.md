# BarCode Studio

<p align="center">
  <img src="favicon.svg" width="96" height="96" alt="BarCode Studio Logo">
</p>

<p align="center">
  <strong>Professional, enterprise-grade barcode generator with a modern UI</strong>
</p>

<p align="center">
  Generate, customize, and export barcodes in 15+ formats — all client-side with zero build steps, zero server dependencies, and zero compromises.
</p>

<p align="center">
  <a href="#features">Features</a> &bull;
  <a href="#quick-start">Quick Start</a> &bull;
  <a href="#supported-formats">Formats</a> &bull;
  <a href="#keyboard-shortcuts">Shortcuts</a> &bull;
  <a href="#tech-stack">Tech Stack</a> &bull;
  <a href="#browser-support">Browser Support</a> &bull;
  <a href="#license">License</a>
</p>

---

## Table of Contents

- [Features](#features)
- [Quick Start](#quick-start)
- [Screenshots](#screenshots)
- [Supported Formats](#supported-formats)
  - [1D Barcodes](#1d-barcodes)
  - [2D Barcodes](#2d-barcodes)
  - [Format Details](#format-details)
- [How It Works](#how-it-works)
  - [Single Generation](#single-generation)
  - [Batch Generation](#batch-generation)
  - [History](#history)
- [Export Options](#export-options)
- [Customization](#customization)
  - [Colors](#colors)
  - [Scale](#scale)
  - [Theme](#theme)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [File Structure](#file-structure)
- [Browser Support](#browser-support)
- [Performance](#performance)
- [Accessibility](#accessibility)
- [SEO & Meta](#seo--meta)
- [Contributing](#contributing)
- [Changelog](#changelog)
- [License](#license)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

---

## Features

### Core Functionality

| Feature | Description |
|---------|-------------|
| **15 Barcode Formats** | Full support for Code 128, QR Code, EAN-13, UPC-A, EAN-8, UPC-E, Code 39, ITF-14, Codabar, GS1-128, Data Matrix, PDF417, Aztec, MaxiCode, and Han Xin |
| **Batch Generation** | Paste multiple items (one per line), generate all barcodes at once, export individually or in bulk |
| **History** | Auto-saved to `localStorage` — up to 50 entries with one-click reload |
| **Live Preview** | Real-time barcode rendering as you type (200ms debounce) |
| **Format Examples** | Each format chip shows an example data placeholder for quick testing |

### Export & Sharing

| Export | Format | Description |
|--------|--------|-------------|
| **PNG** | Raster | High-quality raster image at selected scale (1x–5x) |
| **SVG** | Vector | Scalable vector format — perfect for print and large displays |
| **Copy** | Clipboard | One-click copy to system clipboard as PNG image |
| **Print** | Print | Opens a print-ready window with the barcode centered |

### User Experience

- **Dark / Light Theme** — Toggle between themes; persists across sessions via `localStorage`
- **Glassmorphism UI** — Modern frosted-glass aesthetic with ambient gradient orbs
- **Keyboard Shortcuts** — Full keyboard navigation for power users (7 shortcuts)
- **Responsive Design** — Optimized for desktop, tablet, and mobile screens
- **Toast Notifications** — Non-intrusive feedback for actions (download, copy, errors)
- **Error Handling** — Clear, visible error messages when data doesn't match format requirements
- **Format Categories** — Formats organized into 1D and 2D sections with visual labels
- **Loading States** — Spinner animation on the Generate button during rendering
- **Micro-interactions** — Hover glow, card lift, chip overlay, and smooth transitions

### Accessibility

- **ARIA Labels** — All interactive elements have proper ARIA attributes
- **Focus Management** — Visible focus indicators (`:focus-visible`) for keyboard navigation
- **Role Attributes** — `role="tablist"`, `role="tab"`, `role="radiogroup"`, `role="dialog"`, etc.
- **Screen Reader** — Error messages and status badges announced to assistive technology
- **Keyboard Operable** — Every action achievable without a mouse

---

## Quick Start

### 1. Open the App

No installation required. Simply open `index.html` in any modern browser:

```bash
# Option 1: Double-click index.html
# Option 2: Use a local server (recommended for full features)
npx serve .
# or
python -m http.server 8000
```

### 2. Select a Format

Click any format chip from the grid. Formats are organized into two sections:
- **1D Barcodes** — Code 128, EAN-13, UPC-A, EAN-8, UPC-E, Code 39, ITF-14, Codabar, GS1-128
- **2D Barcodes** — QR Code, Data Matrix, PDF417, Aztec, MaxiCode, Han Xin

### 3. Enter Your Data

Type or paste your data into the input field. Each format has specific requirements:
- **QR Code**: Any text, URL, or data (up to 4,296 alphanumeric characters)
- **EAN-13**: Exactly 12 or 13 digits
- **Code 128**: Any ASCII text
- See the [Format Details](#format-details) section for all constraints.

### 4. Customize

- **Foreground Color**: Change the bar/QR color (default: black)
- **Background Color**: Change the background (default: white)
- **Scale**: Adjust from 1x (smallest) to 5x (largest) — affects PNG/SVG output resolution

### 5. Export

Click any export button:
- **PNG** — Downloads a raster image file
- **SVG** — Downloads a scalable vector file
- **Copy** — Copies the image to your clipboard
- **Print** — Opens a print dialog with the barcode

---

## Screenshots

> The app features a dark-mode-first design with glassmorphism effects, ambient gradient backgrounds, and a polished, professional interface.

**Key UI Elements:**
- Sticky top bar with logo, keyboard shortcuts button, and theme toggle
- Hero section with animated gradient title
- Tabbed interface (Single / Batch / History)
- Format grid split into 1D and 2D sections
- Live preview with checkerboard pattern background
- Barcode info bar showing format, character count, and dimensions

---

## Supported Formats

### 1D Barcodes

| Format | BCID | Use Case | Data Constraint | Example |
|--------|------|----------|-----------------|---------|
| **Code 128** | `code128` | Universal — shipping, inventory, logistics | Any ASCII text | `1234567890` |
| **EAN-13** | `ean13` | Retail product labeling (international) | 12 or 13 digits | `5901234123457` |
| **UPC-A** | `upca` | US and Canada retail | 11 or 12 digits | `012345678905` |
| **EAN-8** | `ean8` | Small retail items (compact) | 7 or 8 digits | `96385074` |
| **UPC-E** | `upce` | Compressed UPC code | 6–8 digits | `01234565` |
| **Code 39** | `code39` | Industrial, military, government | A–Z, 0–9, `- . $ / + % SPACE` | `CODE39` |
| **ITF-14** | `itf` | Shipping cartons and packaging | Even number of digits (14) | `12345678901231` |
| **Codabar** | `codabar` | Libraries, blood banks, photo labs | `0-9 - $ : / . +` | `A1234567890A` |
| **GS1-128** | `gs1-128` | Supply chain, shipping labels | GS1 Application Identifier format | `(01)09521234543213` |

### 2D Barcodes

| Format | BCID | Use Case | Data Constraint | Example |
|--------|------|----------|-----------------|---------|
| **QR Code** | `qrcode` | URLs, contact info, payments, marketing | Any text / URL (up to 4,296 chars) | `https://example.com` |
| **Data Matrix** | `datamatrix` | Small items, electronics, healthcare | Up to 3,116 numeric characters | `DM-2024-001` |
| **PDF417** | `pdf417` | IDs, transport tickets, large data | Up to 1,850 text characters | `PDF417SAMPLE` |
| **Aztec** | `aztec` | Transport tickets, boarding passes | Up to 3,067 numeric characters | `AZTEC-2024` |
| **MaxiCode** | `maxicode` | UPS package tracking | 93 characters max | `1Z9999W99999999999` |
| **Han Xin** | `hanxin` | Chinese GB/T standard | Chinese characters | `测试` |

### Format Details

#### Code 128
- **Standard**: ISO/IEC 15417
- **Character Set**: Full ASCII (0–127)
- **Checksum**: Automatic (Mod 103)
- **Best For**: General-purpose 1D barcode, shipping labels, inventory

#### QR Code
- **Standard**: ISO/IEC 18004
- **Versions**: 1–40 (auto-selected based on data)
- **Error Correction**: Level M (15% recovery) — configurable via bwip-js
- **Best For**: URLs, vCards, WiFi configs, payment links

#### EAN-13
- **Standard**: GS1 (International Article Number)
- **Check Digit**: Auto-calculated (13th digit)
- **Prefix**: Country code (first 2–3 digits)
- **Best For**: Retail products sold internationally

#### UPC-A
- **Standard**: GS1 (Universal Product Code)
- **Check Digit**: Auto-calculated (12th digit)
- **Number System**: First digit identifies type (0 = regular, 2 = weighted, 3 = NDC)
- **Best For**: Retail products in US and Canada

#### Data Matrix
- **Standard**: ISO/IEC 16022
- **Max Capacity**: 3,116 numeric / 2,335 alphanumeric / 1,556 bytes
- **Auto-Sizing**: Automatically selects optimal symbol size
- **Best For**: Small items, electronics, surgical instruments

#### PDF417
- **Standard**: ISO/IEC 15438
- **Type**: Stacked linear barcode (2D)
- **Max Capacity**: 1,850 text characters / 2,710 numeric
- **Best For**: Driver's licenses, transport tickets, inventory lists

---

## How It Works

### Single Generation

1. **Select Format** — Click a format chip from the 1D or 2D grid
2. **Enter Data** — Type text into the data input field
3. **Customize** — Adjust foreground/background colors and scale
4. **Generate** — Click the "Generate Barcode" button (or press `Ctrl+Enter`)
5. **Preview** — The barcode appears instantly in the preview panel
6. **Export** — Download as PNG/SVG, copy to clipboard, or print

### Batch Generation

1. **Switch to Batch Tab** — Click the "Batch" tab (or press `2`)
2. **Enter Data** — Paste multiple lines into the textarea
   - Format: `data | format` (one per line)
   - Example: `1234567890 | code128`
   - If format is omitted, the currently selected format is used
3. **Generate All** — Click "Generate All" button
4. **Review** — Each barcode appears in a list with preview, data, and format
5. **Export** — Download individual barcodes or export all as PNG

**Batch Input Examples:**
```
1234567890 | code128
https://example.com | qrcode
5901234123457 | ean13
012345678905 | upca
96385074 | ean8
```

### History

- **Auto-Saved** — Every generated barcode is automatically saved
- **Up to 50 Entries** — Oldest entries are removed when limit is reached
- **Click to Reload** — Click any history card to load that barcode's data and format
- **Clear History** — Click the "Clear" button to wipe all history
- **Persistence** — Stored in `localStorage`, survives browser restarts

---

## Export Options

### PNG Export
- **Format**: Portable Network Graphics (raster)
- **Resolution**: Determined by scale setting (1x–5x)
- **Use Case**: Web, digital displays, presentations
- **File Name**: `barcode-{format}-{data}.png`

### SVG Export
- **Format**: Scalable Vector Graphics (vector)
- **Resolution**: Infinitely scalable without quality loss
- **Use Case**: Print, large-format displays, design tools
- **File Name**: `barcode-{format}-{data}.svg`

### Clipboard Copy
- **Format**: PNG image data
- **Use Case**: Paste directly into documents, chats, emails
- **Note**: Requires clipboard API support (modern browsers)

### Print
- **Format**: Opens a new window with the barcode centered
- **Use Case**: Physical labels, packaging, documentation
- **Note**: Uses `window.print()` for native print dialog

---

## Customization

### Colors

| Option | Default | Description |
|--------|---------|-------------|
| **Foreground** | `#000000` (black) | Color of the bars, dots, or modules |
| **Background** | `#FFFFFF` (white) | Background color behind the barcode |

- Use the color picker or type a hex value directly
- Hex values must be in format `#RRGGBB` (7 characters)
- Changes apply in real-time (200ms debounce)

### Scale

| Scale | Use Case |
|-------|----------|
| **1x** | Smallest file size, low resolution |
| **2x** | Small barcodes, thumbnails |
| **3x** (default) | Standard use, good balance |
| **4x** | High-resolution displays |
| **5x** | Print-quality, large format |

### Theme

- **Dark Mode** — Deep navy/indigo background with white text
- **Light Mode** — Clean white background with dark text
- **Toggle** — Click the moon/sun icon in the top bar (or press `Ctrl+Shift+T`)
- **Persistence** — Theme choice saved to `localStorage`

---

## Keyboard Shortcuts

| Shortcut | Action | Context |
|----------|--------|---------|
| `/` | Focus data input | Global (when not in input) |
| `1` | Switch to Single tab | Global (when not in input) |
| `2` | Switch to Batch tab | Global (when not in input) |
| `3` | Switch to History tab | Global (when not in input) |
| `Ctrl+Enter` | Generate barcode | Global |
| `Ctrl+S` | Download PNG | Global |
| `Ctrl+Shift+C` | Copy to clipboard | Global |
| `Ctrl+Shift+T` | Toggle theme | Global |
| `Esc` | Close shortcuts modal | When modal is open |

> **Note**: Shortcuts involving `1`, `2`, `3`, and `/` are disabled when an input field is focused to prevent conflicts with normal typing.

---

## Tech Stack

### Core

| Technology | Version | Purpose |
|------------|---------|---------|
| **HTML5** | — | Semantic markup, structure |
| **CSS3** | — | Custom properties, grid, flexbox, animations |
| **JavaScript** | ES2022+ | Application logic, IIFE module pattern |

### Dependencies (CDN)

| Library | Version | Purpose | License |
|---------|---------|---------|---------|
| **bwip-js** | 4.3.0 | Barcode rendering engine (client-side) | MIT |
| **Lucide Icons** | Latest | UI icon set (1000+ icons) | ISC |
| **Inter** | Variable | Primary sans-serif typeface | OFL |
| **JetBrains Mono** | Variable | Monospace font for data/code | OFL |

### No Build Step Required

- Single `index.html` file — open and run
- No `npm install`, no `webpack`, no `vite`, no bundler
- All dependencies loaded from CDN
- Works offline after first load (CDN assets cached by browser)

---

## Architecture

### Design Principles

1. **Single File** — Entire app in one `index.html` (HTML + CSS + JS)
2. **Zero Dependencies** — No npm packages, no build tools
3. **Client-Side Only** — No server, no API calls, no data sent anywhere
4. **Progressive Enhancement** — Works without JavaScript for basic HTML, full features with JS
5. **Accessibility First** — ARIA labels, keyboard navigation, focus management

### Code Structure

```
index.html (single file)
├── <head>
│   ├── Meta tags (SEO, viewport, theme-color)
│   ├── Favicon (SVG)
│   ├── Google Fonts (Inter + JetBrains Mono)
│   ├── bwip-js (barcode engine)
│   └── Lucide Icons
├── <style>
│   ├── CSS Custom Properties (design tokens)
│   ├── Dark/Light Theme variables
│   ├── Component styles (cards, buttons, forms, etc.)
│   ├── Layout (grid, responsive breakpoints)
│   ├── Animations (float, fadeUp, toastIn, spin)
│   └── Print stylesheet
├── <body>
│   ├── Ambient background (gradient orbs)
│   ├── Top bar (logo, shortcuts, theme toggle)
│   ├── Hero section (title, subtitle)
│   ├── Tab navigation (Single, Batch, History)
│   ├── Tab content panels
│   ├── Toast container
│   └── Shortcuts modal
└── <script>
    ├── FORMATS constant (15 format definitions)
    ├── State management (currentFormat, batchItems, history)
    ├── DOM references ($ selectors)
    ├── Format grid initialization
    ├── Barcode generation (bwipjs.toCanvas)
    ├── History management (localStorage)
    ├── Batch processing
    ├── Export functions (PNG, SVG, Copy, Print)
    ├── Theme toggle
    ├── Toast notifications
    ├── Keyboard shortcuts
    └── Init function
```

### State Management

| State | Storage | Description |
|-------|---------|-------------|
| `currentFormat` | Variable | Currently selected barcode format ID |
| `batchItems` | Variable | Array of batch items with data, format, and error state |
| `history` | `localStorage` | Array of generated barcodes (max 50) |
| `debounceTimer` | Variable | Timer for debounced input (200ms) |
| Theme | `localStorage` | `'dark'` or `'light'` |

### CSS Architecture

- **Custom Properties** — All colors, spacing, shadows, and transitions as CSS variables
- **Theme System** — `[data-theme="dark"]` and `[data-theme="light"]` selectors
- **Component-Based** — Each UI component has its own CSS block
- **Mobile-First** — Base styles for mobile, `@media` queries for larger screens
- **Print Styles** — `@media print` hides UI elements, shows only barcode

---

## File Structure

```
Barcode-Generator/
├── index.html          # Main application (HTML + CSS + JS)
├── favicon.svg         # SVG favicon (barcode design)
├── README.md           # This file
└── .git/               # Git repository
```

---

## Browser Support

| Browser | Version | Status |
|---------|---------|--------|
| **Chrome** | 90+ | Fully Supported |
| **Firefox** | 88+ | Fully Supported |
| **Safari** | 14+ | Fully Supported |
| **Edge** | 90+ | Fully Supported |
| **Opera** | 76+ | Fully Supported |
| **Samsung Internet** | 15+ | Fully Supported |
| **iOS Safari** | 14+ | Fully Supported |
| **Chrome Android** | 90+ | Fully Supported |

### Requirements

- **JavaScript** — Must be enabled
- **Clipboard API** — Required for copy-to-clipboard (not available in all contexts)
- **Canvas** — Required for barcode rendering (supported in all modern browsers)
- **localStorage** — Required for theme and history persistence

---

## Performance

| Metric | Value |
|--------|-------|
| **File Size** | ~25 KB (HTML + CSS + JS) |
| **First Paint** | < 100ms (static file) |
| **Barcode Generation** | < 50ms (typical) |
| **Debounce** | 200ms (input to render) |
| **History Limit** | 50 entries (localStorage) |
| **CDN Dependencies** | 4 requests (bwip-js, Lucide, Inter, JetBrains Mono) |

### Optimization Notes

- **No Build Step** — Zero compilation time
- **Lazy Icons** — Lucide icons created on-demand per section
- **Debounced Input** — Prevents excessive re-renders during typing
- **CSS Variables** — Theme switching without style recalculation
- **Efficient Selectors** — Minimal DOM queries, cached references

---

## Accessibility

### WCAG 2.1 Compliance

| Criterion | Level | Implementation |
|-----------|-------|----------------|
| **1.1.1 Non-text Content** | A | Alt text on images, ARIA labels on icons |
| **1.3.1 Info and Relationships** | A | Semantic HTML, ARIA roles |
| **1.4.1 Use of Color** | A | Color not sole indicator (text labels always present) |
| **1.4.3 Contrast (Minimum)** | AA | Theme colors designed for sufficient contrast |
| **2.1.1 Keyboard** | A | All functionality available via keyboard |
| **2.4.1 Bypass Blocks** | A | Skip to content not needed (single-page app) |
| **2.4.3 Focus Order** | A | Logical tab order through interactive elements |
| **2.4.7 Focus Visible** | AA | Custom `:focus-visible` outline |
| **4.1.2 Name, Role, Value** | A | ARIA labels, roles, and states on all controls |

### ARIA Implementation

```html
<!-- Tab navigation -->
<div class="tabs" role="tablist">
  <button class="tab active" role="tab" aria-selected="true">...</button>
</div>

<!-- Format grid -->
<div class="format-grid" role="radiogroup" aria-label="Barcode format selection">
  <div class="format-chip" role="radio" aria-checked="false">...</div>
</div>

<!-- Status badge -->
<span class="badge badge-success" id="status-badge" aria-live="polite">Ready</span>

<!-- Toast notifications -->
<div class="toast-container" aria-live="polite">...</div>

<!-- Modal -->
<div class="modal-overlay" role="dialog" aria-modal="true" aria-labelledby="shortcuts-title">
```

---

## SEO & Meta

| Tag | Value |
|-----|-------|
| **Title** | BarCode Studio — Professional Barcode Generator |
| **Description** | Enterprise-grade barcode generator supporting QR Code, Code 128, EAN-13, UPC-A, and more. Export as PNG, SVG, or print directly. |
| **Theme Color** | `#6366f1` (Indigo) |
| **Viewport** | `width=device-width, initial-scale=1.0` |
| **Charset** | UTF-8 |
| **Favicon** | SVG (barcode design with indigo gradient) |

---

## Contributing

Contributions are welcome! Here's how to get started:

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/amazing-feature`
3. **Commit** your changes: `git commit -m 'Add amazing feature'`
4. **Push** to the branch: `git push origin feature/amazing-feature`
5. **Open** a Pull Request

### Development Guidelines

- **Single File** — Keep everything in `index.html`
- **No New Dependencies** — CDN-only, no npm packages
- **Accessibility** — Add ARIA labels for new interactive elements
- **Responsive** — Test on mobile, tablet, and desktop
- **Themes** — Ensure new UI works in both dark and light modes
- **Format Support** — Use bwip-js bcid values for new barcode formats

---

## Changelog

### v2.0.0 (Latest)
- Complete UI redesign with glassmorphism and ambient gradients
- Split format grid into 1D and 2D sections with category labels
- Added gradient Generate button with glow hover effect
- Added loading spinner animation
- Improved barcode preview with checkerboard pattern
- Added minimal footer with credits
- Enhanced micro-interactions (card lift, chip overlay, toast spring)
- Better responsive breakpoints for mobile

### v1.1.0
- Added prominent "Generate Barcode" button
- Fixed bwip-js format IDs (`gs1` → `gs1-128`, `itf` for ITF-14)
- Replaced screen-reader-only errors with visible error box
- Added format grid initialization on page load

### v1.0.0
- Initial enterprise-grade rebuild
- 15 barcode formats
- Single, Batch, and History tabs
- Dark/light theme toggle
- Keyboard shortcuts
- Responsive design
- SVG favicon

---

## License

This project is licensed under the **MIT License**.

```
MIT License

Copyright (c) 2024 BarCode Studio

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## Author

**Girish Lade** — [GitHub](https://github.com/girishlade111)

---

## Acknowledgments

- [bwip-js](https://github.com/metafloor/bwip-js) — Barcode rendering engine
- [Lucide](https://lucide.dev) — Beautiful open-source icons
- [Inter](https://rsms.me/inter) — Typeface for UI
- [JetBrains Mono](https://www.jetbrains.com/mono) — Monospace typeface

---

<p align="center">
  Made with precision. Built for professionals.
</p>
