# NoHate — Cyberbullying Detector

A sleek, client-side cyberbullying and hate speech detector for social media text. Built with vanilla HTML, CSS, and JavaScript — no dependencies, no backend required.

![NoHate Preview](https://img.shields.io/badge/status-active-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue) ![HTML](https://img.shields.io/badge/built%20with-HTML%2FCSS%2FJS-orange)

---

## Features

- **Instant Analysis** — Paste any text and get a harmful/safe verdict in milliseconds
- **Toxicity Score** — Animated severity bar showing how toxic the content is (0–100%)
- **Keyword Highlighting** — Offensive terms are highlighted directly in the processed text
- **Editable Keyword Database** — Add or remove keywords from the built-in offensive word list at runtime
- **Scan History** — Last 20 scans are logged; click any entry to re-run the analysis
- **Session Stats** — Live counters for total scanned, flagged, and safe comments
- **Zero Dependencies** — Pure HTML/CSS/JS, works entirely in the browser

---

## Demo

Open `nohate.html` directly in any modern browser — no server needed.

```
git clone https://github.com/YOUR_USERNAME/nohate.git
cd nohate
open nohate.html   # macOS
# or
start nohate.html  # Windows
```

Or deploy instantly via **GitHub Pages** (see below).

---

## How It Works

1. Input text is converted to lowercase and punctuation is stripped
2. Each word is compared against the offensive keyword database
3. Matches are highlighted and a toxicity score is computed
4. Comment is classified as **Harmful** or **Safe**

The toxicity score is calculated as:

```
score = min(100, round((matchCount / max(wordCount × 0.15, 1)) × 100))
```

---

## Deployment

### GitHub Pages (recommended)

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, root `/`
4. Your site will be live at `https://YOUR_USERNAME.github.io/nohate/`

> **Note:** GitHub Pages will serve `index.html` by default. Either rename `nohate.html` to `index.html`, or set the Pages source file manually.

### Netlify / Vercel

Drag and drop the folder into [netlify.com/drop](https://app.netlify.com/drop) for instant hosting.

---

## Project Structure

```
nohate/
├── nohate.html      # Main application (single-file)
├── README.md        # This file
├── LICENSE          # MIT License
└── .gitignore       # Git ignore rules
```

---

## Customising Keywords

The default keyword list is defined in the `<script>` block inside `nohate.html`:

```js
let keywords = [
  "idiot", "stupid", "dumb", ...
];
```

You can also add/remove keywords live from the **Keyword Database** panel in the UI — changes persist for the current session.

---

## Limitations

- Keyword matching is **exact substring-based** — it does not understand context, sarcasm, or intent
- Does not handle leetspeak, character substitution (e.g. `h4te`), or obfuscated slurs
- Session data (history, stats) is **not persisted** across page reloads

---

## Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you'd like to change.

1. Fork the repo
2. Create your branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'Add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

---

## License

[MIT](LICENSE) © 2024
