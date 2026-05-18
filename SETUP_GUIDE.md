# ICEMAN Quarto Site — Setup Guide

## What you have
Your project folder (`iceman-site/`) contains:

```
iceman-site/
├── _quarto.yml          ← site config (navbar, theme, bibliography)
├── index.qmd            ← landing page (downloads, citation, overview)
├── manual/              ← split users manual pages
├── manual.qmd           ← legacy one-page manual
├── tool.qmd             ← interactive assessment forms
├── references.bib       ← your 149 BibTeX references
├── manual_numbering.csv ← PDF number → BibTeX key mapping
└── assets/
    ├── custom.css       ← all custom styles
    └── vancouver-superscript.csl ← Vancouver superscript citation style
```

---

## Step 1 — Install Quarto

Download and install Quarto from https://quarto.org/docs/get-started/

- **macOS:** download the `.pkg` installer
- **Windows:** download the `.msi` installer
- **Linux:** download the `.deb` or `.rpm` package

Verify installation:
```bash
quarto --version
```

---

## Step 2 — Install R or Python (pick one)

Quarto needs a computational engine to render `.qmd` files.

**Option A — R (recommended for research):**
1. Install R from https://cran.r-project.org/
2. Install RStudio from https://posit.co/downloads/
3. In RStudio, install the quarto package:
   ```r
   install.packages("quarto")
   ```

**Option B — Python:**
```bash
pip install jupyter
```

---

## Step 3 — Copy your files

Copy the entire `iceman-site/` folder to wherever you keep your projects.

Also copy into the folder root:
- `ICEMAN manual .pdf`
- `ICEMAN RCT 1.1 (6).docx`
- `ICEMAN MA 1.1 (8).docx`

These are listed under `project.resources` in `_quarto.yml` so Quarto copies them into `docs/` for download.

---

## Step 4 — Add citation keys to the manual (optional but recommended)

Your CSV maps PDF reference numbers (1–149) to BibTeX keys.
For example, reference [60] in the manual = `collaborators2011importance` in your .bib file.

To make references clickable in the manual, you can add inline citations like:
```
[@Hahn2000assessing-0001]
```

The manual pages in `manual/` use the bibliography configured in `_quarto.yml`;
Quarto will automatically render citations using Vancouver style.

---

## Step 5 — Preview locally

Open a terminal, navigate to your `iceman-site/` folder, and run:

```bash
cd iceman-site
quarto preview
```

This opens a live preview in your browser at http://localhost:4321
Any changes you save are instantly reflected.

---

## Step 6 — Render the full site

When you're happy with the content:

```bash
quarto render
```

This creates a `docs/` folder with all the HTML files ready to publish.

---

## Step 7 — Publish

**Option A — GitHub Pages (free, recommended):**
1. Create a GitHub account at https://github.com if you don't have one
2. Create a new repository (e.g. `iceman-tool`)
3. In your terminal:
   ```bash
   quarto publish gh-pages
   ```
   Follow the prompts. Your site will be live at:
   `https://yourusername.github.io/iceman-tool/`

**Option B — Quarto Pub (easiest, no GitHub needed):**
```bash
quarto publish quarto-pub
```
Creates a free site at `https://yourusername.quarto.pub/iceman/`

**Option C — Netlify (most control):**
1. Go to https://netlify.com and sign up
2. Drag and drop your `docs/` folder onto the Netlify dashboard
3. Your site is instantly live with a free URL

---

## Step 8 — Add PDF download forms (optional enhancement)

To add actual fillable PDF forms for download:

1. Create the fillable PDFs using Adobe Acrobat or LibreOffice
2. Save them as `iceman-site/downloads/ICEMAN_RCT_form.pdf`
   and `iceman-site/downloads/ICEMAN_meta_form.pdf`
3. Update the download links in `index.qmd`:
   ```markdown
   <a href="downloads/ICEMAN_RCT_form.pdf" class="btn btn-sm btn-outline-primary">Download PDF</a>
   ```

---

## Customisation tips

| What to change | Where |
|----------------|-------|
| Site title / navbar links | `_quarto.yml` |
| Colours and fonts | `assets/custom.css` |
| Landing page text / citation | `index.qmd` |
| Manual content | `manual/*.qmd` |
| Assessment form items | `tool.qmd` |
| Add a new page | Create `newpage.qmd`, add to `_quarto.yml` navbar |

---

## Troubleshooting

**"quarto: command not found"**
→ Restart your terminal after installing Quarto, or add it to your PATH.

**References not rendering**
→ Make sure `references.bib` is in the same folder as `_quarto.yml`.
→ Check that `bibliography: references.bib` is in `_quarto.yml`.

**CSS not loading**
→ Make sure `assets/custom.css` exists and the path in `_quarto.yml` is correct.

**Site looks unstyled**
→ Run `quarto render` (not just preview) and check the `docs/` output folder.

---

## Need help?

- Quarto documentation: https://quarto.org/docs/websites/
- Quarto GitHub Discussions: https://github.com/quarto-dev/quarto-cli/discussions
