# SVG Ordner Register Editor

A fully **offline-capable**, single-file web app for creating printable folder register sheets as SVG — no server, no dependencies, no installation.

![Screenshot](https://via.placeholder.com/900x500?text=SVG+Ordner+Register+Editor)

---

## Features

- **Multiple registers** — manage any number of named folder registers, switch via dropdown
- **Rich text editor** — bold, italic, underline, adjustable font size per text selection
- **All common page formats** — A0–A6, Letter, Legal, Tabloid in portrait or landscape
- **2–31 register slots** per sheet, freely configurable
- **Live preview sidebar** — SVG preview always visible on the right, updates instantly
- **Print directly** — prints the SVG without a popup window
- **Download as SVG** — vector output ready for any PDF printer
- **Export / Import JSON** — save individual registers with their name; on import, choose to overwrite or create a new copy
- **Drag-free reordering** — move register slots up/down or to top/bottom with one click
- **Persistent state** — all data is saved in `localStorage`; survives page reloads
- **100% offline** — one self-contained `.html` file, no CDN, no network required

---

## Usage

1. Download [`printOrdnerRegister.html`](printOrdnerRegister.html)
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. Done — no setup required

---

## Editor

| Button | Shortcut | Action |
|--------|----------|--------|
| **Bold** | `Ctrl+B` | Toggle bold on selection |
| *Italic* | `Ctrl+I` | Toggle italic on selection |
| <u>Underline</u> | `Ctrl+U` | Toggle underline on selection |
| **A−** | — | Decrease font size by 2 px |
| **A** | — | Reset font size to default (14 px) |
| **A+** | — | Increase font size by 2 px |

> Font size changes affect the selected text only. Each text segment stores exactly one font size — no accumulated nesting.

---

## Register Management

| Action | How |
|--------|-----|
| Switch register | Dropdown in the header |
| Rename | ✏️ button next to dropdown |
| New register | ➕ button |
| Delete register | 🗑️ button (disabled when only one register exists) |

---

## Export / Import

Export saves the **current register** as a `.json` file including its name:

```json
{
  "registerName": "Kunden",
  "registerCount": 10,
  "pageFormat": "A4",
  "pageOrientation": "portrait",
  "contents": ["<b>Verträge</b>", "<b>Rechnungen</b>", ...],
  "exportDate": "2026-07-04T09:41:04.583Z"
}
```

On **import**, if a register with the same name already exists, you choose:
- **OK** → overwrite existing
- **Cancel** → create a new copy with suffix *(Import)*

---

## Page Settings

Open ⚙️ to configure per register:

| Setting | Options |
|---------|---------|
| Format | A0, A1, A2, A3, **A4**, A5, A6, Letter, Legal, Tabloid |
| Orientation | Portrait, Landscape |
| Register count | 2 – 31 |

---

## Responsive Layout

| Screen width | Behaviour |
|---|---|
| ≥ 901 px | SVG preview always visible on the right |
| ≤ 900 px | Preview sidebar hidden; 👁 Vorschau button appears in toolbar |

---

## Technology

| | |
|---|---|
| Language | Vanilla JavaScript (ES2020) |
| Styling | Inline CSS with CSS custom properties |
| Editor | Native `contenteditable` with `document.execCommand` |
| Output | Inline SVG with `<foreignObject>` for rich HTML content |
| Storage | `localStorage` (JSON) |
| Dependencies | **None** |
| File count | **1** |

---

## License

MIT — free to use, modify and distribute.
