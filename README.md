# Personal Website

Plain HTML + CSS. No build step. Two pages (`index.html`, `research.html`) plus a single stylesheet.

## Editing

- **About / bio:** edit `index.html`.
- **Papers:** edit `research.html`. Copy the `<article class="paper">` block to add a new paper.
- **Styles:** edit `style.css`. Color variables are at the top.
- **CV:** edit `assets/cv.tex`, then recompile:
  ```
  cd assets && pdflatex cv.tex && rm -f cv.aux cv.log cv.out
  ```
- **Files:** drop into `assets/`.
  - Headshot: `assets/headshot.jpg`
  - CV PDF: `assets/cv.pdf` (built from `cv.tex`)
  - Paper PDFs: `assets/papers/`

## Preview locally

```
python3 -m http.server 8000
```

Then open <http://localhost:8000> in a browser.

## Deploy to GitHub Pages

One-time setup:

1. Create a new GitHub repo named exactly `<your-github-username>.github.io` (the name matters: GitHub auto-publishes a repo with this name).
2. From this folder:
   ```
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin git@github.com:<your-github-username>/<your-github-username>.github.io.git
   git push -u origin main
   ```
3. Visit `https://<your-github-username>.github.io` after a minute or two.

Every future change: edit files, then `git add . && git commit -m "..." && git push`. The site updates automatically.

The empty `.nojekyll` file tells GitHub Pages to serve files as-is instead of running Jekyll on them.
