# circuit-lab

Practical electronics notes — components, formulas, and real circuits — viewed as mindmaps with [Markmap](https://markmap.js.org).

## Contents

| File | Topic |
|---|---|
| [Resistor.md](./Resistor.md) | Resistors: Ohm's law, series/parallel, voltage divider, LED |
| [Transistor.md](./Transistor.md) | NPN transistor as a switch, $R_B$, $\beta$ |

Each Markdown file is one mindmap: `#` / `##` headings are main branches, `-` lists are child nodes.

---

## Using Markmap

Markmap turns a Markdown file into an interactive mindmap (zoom, pan, fold/unfold branches).

### Option 1: Cursor / VS Code (recommended)

1. Install the **[Markmap](https://marketplace.visualstudio.com/items?itemName=gera2ld.markmap-vscode)** extension (`gera2ld.markmap-vscode`).
2. Open a `.md` file, e.g. `Resistor.md`.
3. Open the mindmap with one of:
   - Command Palette (`Cmd+Shift+P` / `Ctrl+Shift+P`) → **Open as markmap**
   - Click the Markmap icon on the editor title bar
   - Right-click the file → **Open as markmap**

Edit Markdown on the left; the mindmap updates on the right.

### Option 2: CLI (export HTML)

Requires [Node.js](https://nodejs.org). No global install needed:

```bash
npx markmap-cli Resistor.md
npx markmap-cli Transistor.md
```

This generates an HTML file and opens it in the browser.

| Option | What it does |
|---|---|
| `-o out.html` | Set the output filename |
| `--offline` | Inline assets so the HTML works without a network |
| `-w` | Watch: HTML updates as you edit the `.md` file |
| `--no-open` | Do not open the browser |
| `--no-toolbar` | Hide the toolbar on the mindmap |

Examples:

```bash
npx markmap-cli Transistor.md -o transistor.html --offline
npx markmap-cli Resistor.md -w
```

### Option 3: Web, no install

Paste Markdown into [markmap.js.org](https://markmap.js.org).

---

## Writing Markdown for Markmap

File structure becomes the mindmap tree:

```md
# Root (one file = one mindmap)

## Level-1 branch

- Level-2 branch
  - Level-3 branch
  - Another node
- Another level-2 branch

## Another level-1 branch

- Note
```

Conventions in this repo:

- `#` — component / topic name
- `##` — major sections (concept, formulas, examples)
- `###` — subsections
- nested `-` — details, formulas, tips

Supported out of the box:

- **Bold**, _italic_, `code`
- KaTeX formulas: `$I = \frac{U}{R}$`
- Images / SVG in HTML: `<img src="..." />`
- Links and code blocks

### Appearance options (frontmatter)

Add this at the top of a file to change colors, node width, or default expand depth:

```md
---
markmap:
  colorFreezeLevel: 2
  maxWidth: 320
  initialExpandLevel: 2
---

# Resistor (R)
```

| Option | Meaning |
|---|---|
| `colorFreezeLevel` | Children inherit the ancestor color from that level down |
| `maxWidth` | Max text width per node (`0` = no limit) |
| `initialExpandLevel` | Expand to this level on load (`-1` = expand all) |
| `zoom` / `pan` | Enable/disable zoom and pan |

---

## Adding a new note

1. Create a `.md` file in the repo root, e.g. `Capacitor.md`.
2. Start with `# Component name`, then `##` / lists as above.
3. Open it in Markmap and check that the tree is easy to read.
4. Add a row to the **Contents** table in this README.

Keep one component per file — the mindmap stays clearer than stuffing everything into one Markdown file.
