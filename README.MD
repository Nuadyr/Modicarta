# Modicarta

**Modicarta** is a fast, web-based Magic: The Gathering (MTG) Standard deck analyser and metagame matching engine built by Nuadyr. Paste a decklist to instantly view mana curves, synergy breakdowns, metagame coverage, coloured mana requirements, and targeted card replacement suggestions.

It runs locally in your browser with zero server dependencies, supporting high-contrast accessible design systems, PDF export capabilities, and an editable metagame corpus.

---

## Quick Start

1. **Live Web App**: Access directly via GitHub Pages at [https://nuadyr.github.io/Modicarta/](https://nuadyr.github.io/Modicarta/)
2. **Local Run**: Clone this repository and open `index.html` directly in any modern browser—no server setup, Node.js, or build steps required.

```bash
git clone https://github.com/Nuadyr/Modicarta.git
cd Modicarta
# Open index.html in your browser
```

---

## Key Features

* **Mana Curve & Ramp Visualisation**: Responsive SVG charts showing non-land card distributions across mana values and cumulative ramp projections.
* **Archetype Synergy Engine**: Measures archetype alignment using Scryfall Oracle tag lookups and deck composition analysis.
* **Metagame Matching**: Evaluates decklists against embedded or custom MTGGoldfish Standard metagame archetype breakdowns.
* **Coloured Mana Validation**: Checks deck land counts and mana sources against spell color pip demands.
* **Competitive Rule Checks**: Highlights singleton vulnerabilities, deck size compliance, sideboard handling, and illegal cards.
* **Swap Suggestions & Direct Replacements**: Recommends on-theme replacements and metagame swaps, enabling one-click deck updates.
* **Offline PDF Export**: Generates printable PDF deck sheets and full diagnostic reports complete with card visual embeds via an integrated `jsPDF` bundle.
* **Corpus Builder & Maintenance**: Allows pasting or uploading raw decklist collections (`.txt` or `.json`) to update or replace the current metagame reference data on the fly.
* **Accessibility System**: Full WCAG compliance featuring 7:1 contrast ratios, system dark mode support, non-color-only indicators, reduced-motion controls, and keyboard navigation.

---

## Usage & Deck Format

Paste your decklist into the editor box using the standard card quantity format (one card per line):

```text
4 Opt
2 Dread Summons
24 Island

Sideboard
2 Spell Pierce
```

### Advanced Modifiers
* **Modal / MDFC Cards**: Separate faces using standard double slashes: `Card Name // Other Face`.
* **Sideboard Parsing**: Lines following a `Sideboard` header are ignored during standard metrics analysis.

---

## Architecture & Technology

Modicarta is designed as a single-file Vanilla Web Application (`index.html`) using HTML5, CSS Custom Properties, native ES6 JavaScript, and inline JSON/JavaScript libraries.

```
Modicarta/
├── index.html        # Single self-contained application (UI, Styles, Logic, Data)
└── README.md         # Project documentation
```

### Core Components inside `index.html`:
* **Dynamic CSS**: variable mapping for system light/dark adaptive palettes, high contrast ratios, and accessible SVG shape masks.
* **Embedded Metagame Corpus**: Embedded JSON dataset (`#metagame-corpus`) providing pre-calculated card frequency breakdowns across current Standard metagame archetypes.
* **Inlined jsPDF Engine**: Integrated PDF generation engine (`#jspdf-lib`) enabling browser-side PDF document generation without dynamic remote library fetching.
* **Scryfall Integration**: Dynamic asynchronous card data fetching for Oracle tags, mana costs, and image URLs.

---

## Metagame Corpus Management

You can update the internal metagame reference data directly inside the web UI without modifying code:

1. Expand **Data and tools** at the bottom of the page.
2. Under **Build or replace the metagame corpus**, paste new tournament lists formatted with `# Archetype Name` headers or upload `.txt`/`.json` corpus files.
3. Click **Build corpus from pasted lists** to save your updated metagame state into local storage.

---

## License

This project is authored by **Nuadyr**. Magic: The Gathering content, card names, and artwork are trademarks and copyrights of Wizards of the Coast LLC. All rights reserved. Modicarta is not affiliated with Wizards of the Coast.
