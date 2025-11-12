# hg-portfolio

==============================
FILE: README.md
==============================
# Harshad Ghodke — Data Science & Engineering Portfolio

A fast, no-build static site you can host on GitHub Pages. One HTML file (Tailwind via CDN), easily customizable, with project cards that link to repos, notebooks, and live demos.

## Quick start
1. Create a new GitHub repo (e.g., `hg-portfolio`).
2. Add the files from this starter.
3. Commit & push to `main`.
4. **Enable GitHub Pages**: Settings → Pages → *Deploy from a branch* → Branch: `main` → Folder: `/`.
5. (Optional) Edit `index.html` → update name, tagline, social links, and project cards.

## Adding projects
- Duplicate a `<article class="project-card">…</article>` block in `index.html`.
- Point the buttons to your GitHub repo, a rendered notebook (nbviewer), or a Streamlit/HF Space demo.
- For notebooks, use nbviewer links like: `https://nbviewer.org/github/<user>/<repo>/blob/main/notebook.ipynb`.

## Optional enhancements
- Add a custom domain under Settings → Pages → Custom domain.
- Use Quarto or MkDocs Material later for multi-page docs while keeping this as the landing page.
- Hook a contact form via Formspree (no backend) or keep a `mailto:` link.

---
