# BarCode Studio

Professional, enterprise-grade barcode generator with a modern UI. Generate, customize, and export barcodes in 15+ formats — all client-side with zero dependencies beyond a CDN script.

## Features

- **15 Barcode Formats** — Code 128, QR Code, EAN-13, UPC-A, EAN-8, UPC-E, Data Matrix, PDF417, ITF, Codabar, Code 39, GS1-128, Aztec, MaxiCode, Han Xin
- **Batch Generation** — Paste multiple items, generate all at once, export individually or in bulk
- **History** — Auto-saved to localStorage, click to reload any previous barcode
- **Export Options** — PNG (raster), SVG (vector), Print-ready, Clipboard copy
- **Dark / Light Theme** — System-aware, persists across sessions
- **Keyboard Shortcuts** — Full keyboard navigation for power users
- **Responsive** — Works on desktop, tablet, and mobile
- **Accessible** — ARIA labels, focus management, keyboard operable

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `/` | Focus data input |
| `1` / `2` / `3` | Switch to Single / Batch / History tab |
| `Ctrl+Enter` | Generate barcode |
| `Ctrl+S` | Download PNG |
| `Ctrl+Shift+C` | Copy to clipboard |
| `Ctrl+Shift+T` | Toggle theme |
| `Esc` | Close modal |

## Getting Started

1. Open `index.html` in any modern browser
2. Select a barcode format from the grid
3. Enter your data
4. Customize colors and scale
5. Download, copy, or print

No build step, no server required. Fully static and self-contained.

## Supported Formats

| Format | Type | Use Case |
|---|---|---|
| Code 128 | 1D | Universal — shipping, inventory |
| QR Code | 2D | URLs, contact info, payments |
| EAN-13 | 1D | Retail product labeling |
| UPC-A | 1D | US/Canada retail |
| EAN-8 | 1D | Small retail items |
| UPC-E | 1D | Condensed UPC |
| Data Matrix | 2D | Small items, electronics |
| PDF417 | 2D | IDs, transport tickets |
| ITF | 1D | Shipping cartons |
| Codabar | 1D | Libraries, blood banks |
| Code 39 | 1D | Industrial, military |
| GS1-128 | 1D | Supply chain labels |
| Aztec | 2D | Transport tickets |
| MaxiCode | 2D | UPS tracking |
| Han Xin | 2D | Chinese standard |

## Tech Stack

- **HTML/CSS/JS** — Single file, no framework
- **bwip-js** — Barcode rendering engine (client-side)
- **Lucide Icons** — UI icon set
- **Inter + JetBrains Mono** — Typography

## License

MIT
