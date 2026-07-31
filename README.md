# serene-ho.github.io — setup notes

This is a plain HTML/CSS site (no Jekyll, no build step, no dependencies).
That means GitHub Pages can serve it exactly as-is.

## 1. Publish it on GitHub Pages

1. On GitHub, create a **new repository** named exactly `YOUR-USERNAME.github.io`
   (replace `YOUR-USERNAME` with your actual GitHub username — this exact name
   is what makes GitHub serve it as your personal site).
   - Make it **Public**.
   - Don't initialize it with a README (you already have one here).
2. Upload these files into the repo:
   - Easiest: on the repo's GitHub page, click **Add file → Upload files**,
     then drag in everything from this folder (keep the `assets/` folder
     structure intact) and commit.
   - Or, if you're comfortable with git:
     ```
     cd this-folder
     git init
     git remote add origin https://github.com/YOUR-USERNAME/YOUR-USERNAME.github.io.git
     git add .
     git commit -m "Initial site"
     git branch -M main
     git push -u origin main
     ```
3. Go to **Settings → Pages** in the repo and confirm the source is set to
   deploy from the `main` branch, root folder. (For a `USERNAME.github.io`
   repo this is usually automatic.)
4. Your site will be live at `https://YOUR-USERNAME.github.io` within a
   minute or two.

## 2. Things to fill in before it's ready to send to committees

Search each file for the bracketed placeholders and the dashed `.todo` boxes
on the pages themselves — they're the same information marked twice, once
for you as text, once as a highlighted box on the live page:

| Where | What to replace |
|---|---|
| `index.html` | Email, GitHub URL, LinkedIn URL, Google Scholar URL, "Background" paragraph, grants/awards if any |
| `research.html` | Nothing required — pulled from your dissertation materials — but proofread it |
| `teaching.html` | Teaching philosophy paragraph, courses table |
| `cv.html` | Pre-MIT education line |
| `assets/img/avatar-placeholder.svg` | Replace with a real photo — add e.g. `assets/img/portrait.jpg` and update the `<img src>` in each page's `<div class="portrait">` block |
| `assets/cv/` | Add `Ho_CV.pdf` (the button on the CV page already points here) |

Once you're happy, delete the `.todo` boxes from the HTML (search for
`class="todo"` — each one is a single `<div>...</div>` you can remove).

## 3. Editing later

Every page repeats the same `<nav>` and `<footer>` markup (there's no
templating since there's no build step) — if you change the nav, copy the
change into all four HTML files. Everything else (colors, fonts, spacing)
lives in `assets/css/style.css`.
