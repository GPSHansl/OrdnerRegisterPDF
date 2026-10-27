# Registerliebe

A fully **offline-capable**, single-file web app for creating printable folder register sheets as SVG — no server, no dependencies, no installation.

![Screenshot](https://via.placeholder.com/900x500?text=Registerliebe)

---

## Features

- **Multiple registers** — manage any number of named folder registers, switch via dropdown
- **Inline text fields** — each register slot has its own input field(s) on the main screen
- **1–3 lines per register** — per folder; hidden lines keep their text when the line count is reduced
- **Line styles** — font, size (in pt), bold, italic and underline per line, set once per folder
- **All common page formats** — A0–A6, Letter, Legal, Tabloid in portrait or landscape
- **2–31 register slots** per sheet, freely configurable
- **Live preview sidebar** — SVG preview always visible on the right, updates instantly
- **Print directly** — prints the SVG in original size (font sizes in pt match the printout)
- **Download as SVG** — vector output with physical dimensions in mm, ready for any PDF printer
- **Export / Import JSON** — save individual registers with their name; on import, choose to overwrite or create a new copy
- **Drag & drop reordering** — reorder register slots by dragging the handle
- **Persistent state** — all data is saved in `localStorage`; survives page reloads
- **100% offline** — one self-contained `.html` file, no CDN, no network required

---

## Usage

**Direkt online nutzen:** [Im Browser öffnen](https://gpshansl.github.io/OrdnerRegisterPDF/printOrdnerRegister.html)

1. Download [`printOrdnerRegister.html`](printOrdnerRegister.html)
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. Done — no setup required

---

## Register Management

| Action | How |
|--------|-----|
| Switch register | Dropdown in the folder panel |
| Settings (name, format, lines, line styles) | ⚙️ button |
| New register | ➕ button |
| Export register | 📤 button |
| Import register | 📥 button |
| Delete register | 🗑️ button (not possible when only one register exists) |
| Reset everything | 💀 Reset button in the ℹ️ About dialog |

---

## Export / Import

Export saves the **current register** as a `.json` file including its name:

```json
{
  "registerName": "Kunden",
  "registerCount": 10,
  "lineCount": 2,
  "lineStyles": [{ "font": "", "bold": true, "italic": false, "underline": false, "size": 23 }, ...],
  "pageFormat": "A4",
  "pageOrientation": "portrait",
  "contents": ["<div>Verträge</div><div>2026</div>", "<div>Rechnungen</div>", ...],
  "exportDate": "2026-07-04T09:41:04.583Z"
}
```

On **import**, if a register with the same name already exists, you choose:
- **Überschreiben** → replace the existing register
- **Neu erstellen** → create a new copy with suffix *(Import)*

---

## Page Settings

Open ⚙️ to configure per register:

| Setting | Options |
|---------|---------|
| Name | Free text |
| Format | A0, A1, A2, A3, **A4**, A5, A6, Letter, Legal, Tabloid |
| Orientation | Portrait, Landscape |
| Register count | 2 – 31 |
| Lines per register | 1 – 3 |
| Line style (per line) | Font, size 6–72 pt, **B**old, *I*talic, <u>U</u>nderline |

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
| Output | Inline SVG (viewBox in mm) with `<foreignObject>` for the text |
| Storage | `localStorage` (JSON) |
| Dependencies | **None** |
| File count | **1** |

---

## License

MIT — free to use, modify and distribute.
