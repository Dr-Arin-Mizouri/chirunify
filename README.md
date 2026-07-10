# chirunify

**Use it here: <https://dr-arin-mizouri.github.io/chirunify/>**

A browser-based tool that prepares a [Chirun](https://chirun.org.uk)-ready
package from a LaTeX lab script. Point it at an experiment folder (the `.tex`
plus its images) and it produces:

- `<slug>.zip` — the Chirun-ready `.tex` and every image, packed flat at the
  zip root, ready to upload to Chirun as one file
- `config.yml` — the matching Chirun configuration
- a "things to look at" list — review items the tool flags for a human
  (e.g. figures missing alt text, images the `.tex` references but the folder
  doesn't contain)

Everything runs **entirely in your browser** via
[Pyodide](https://pyodide.org) — your files are never uploaded anywhere. The
first visit downloads ~10 MB (then cached), so give it a moment to load.

The conversion is **deterministic — no AI**: rule-based conversion,
templating, lookup tables and validation. Judgement calls are flagged in the
review list rather than guessed at.

Built for converting Durham University Physics Level 1 lab scripts into
accessible course materials.

## What's in this repo

Just the deployable app, served by GitHub Pages:

- `index.html` — the single-page UI
- `chirunify-0.1.0-py3-none-any.whl` — the chirunify Python package, which the
  page installs into Pyodide at load time

Development happens in a separate (private) repository; updated builds of
these two files are copied here and pushed to deploy.
