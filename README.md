# Personal Site

- Source lives on `main`; published output goes to `gh-pages` via Quarto.
- Drafts under `private/` stay out of public builds; render with the `public` profile.

## Setup (using uv)
1. Install Quarto CLI (v1.5+ recommended).
2. Create/activate a venv: `uv venv` then `source .venv/bin/activate` (PowerShell: `.venv\\Scripts\\activate`)
3. Install Python deps: `uv pip install -r requirements.txt`
4. (Once) register the kernel name used in `_quarto.yml`: `python -m ipykernel install --user --name quarto-env --display-name "Python (quarto-site)"`

## Develop
- Preview locally (excludes drafts): `quarto preview --profile public`
- One-off render: `quarto render --profile public`

## Publish to GitHub Pages
- If the repo has a GitHub remote and you have a token with `repo` scope configured, run:
  - `quarto publish gh-pages --profile public --no-prompt`
- Quarto will build with the `public` profile, create/update the `gh-pages` branch with `_site`, and push it. Verify GitHub Pages is set to serve from `gh-pages` (root).
