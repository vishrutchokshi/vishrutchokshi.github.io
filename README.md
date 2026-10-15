# Vishrut Chokshi: Portfolio

A static, single-page portfolio. Plain HTML, CSS, and vanilla JavaScript with no build step. The only external request is the Inter font from Google Fonts, and the page falls back to system fonts if that fails.

## Files

```
index.html                 The portfolio: opening, My Path, three project chapters, experience, toolbox, contact
Vishrut Chokshi_Resume.pdf Your resume; the Resume links on the site open this file
styles.css                 Layout and the Chocolate and Marlborough palette (CSS custom properties)
script.js                  Mobile menu, current-section nav highlight, scroll reveal
.nojekyll                  Tells GitHub Pages to serve files as-is
.gitignore                 Only used with git; browser uploads ignore it (see the upload list below)
assets/
  images/
    nmos-die-wsi2-slag.webp        Figures extracted from the project reports
    nmos-furnace-zones.webp
    test-chip-qfn72-die-attach.webp
    test-chip-die-layout.webp
    interposer-altium-render.webp
    interposer-fabricated.webp
    eis-three-electrode-cell.webp
    eis-nyquist-11nm.webp
    nmos-process.png               Neutral placeholders, not used by the page (safe to delete)
    test-chip.png
    interposer.png
    eis-sem.png
```

## Before you publish

1. Contact details are filled in, and every Resume link opens `Vishrut Chokshi_Resume.pdf` in this folder. To update your resume, save the new version over that file with the same name.
2. Optional: swap any figure. Save the new image in `assets/images/`, then update the `src`, `alt`, `width`, `height`, and `<figcaption>` for that figure inside the matching chapter (`id="nmos"`, `id="testchip"`, or `id="pinholes"`) in `index.html`.

Paths are relative (`assets/...`, not `/assets/...`) so the site works both at `username.github.io` and at `username.github.io/repo-name/`.

## Preview locally

Open `index.html` in a browser, or run a small server from this folder:

```bash
python -m http.server 8000
```

Then visit http://localhost:8000.

## Publish on GitHub Pages (in the browser, no git needed)

### What to upload, and what not to

Upload only these:

```
index.html
styles.css
script.js
.nojekyll
README.md                    (optional; shows on the repository's front page)
Vishrut Chokshi_Resume.pdf
assets/                      (the whole folder, so assets/images/... keeps its structure)
```

Do **not** upload:

- The four project report PDFs (`EE 5900 ...pdf` and `Vishrut Chokshi - Directed Study Report.pdf`). They name your advisor and teammates and include your student roll number. The website does not need them.
- The `.claude` folder (local preview settings).
- `.gitignore` is harmless either way. Browser uploads ignore it, which is why you have to pick the files yourself.

Two things to know about the resume PDF:

- Its file name has a space in it. The site's links already account for that (`Vishrut%20Chokshi_Resume.pdf`), so keep the name exactly as it is.
- It includes your phone number. Anyone who opens it from the site will see it. If you don't want that, upload a version without the number under the same file name.

### First-time setup

1. Sign in at https://github.com and click **New** (or the **+** menu at top right, then **New repository**).
   - For a site at `https://<username>.github.io`, name the repository exactly `<username>.github.io`.
   - Any other name (for example `portfolio`) gives `https://<username>.github.io/portfolio/`.
   - Set it to **Public**. Pages on private repositories needs a paid plan.
   - Leave **Add a README**, **.gitignore**, and **license** unchecked. Click **Create repository**.
2. On the new empty repository's page, click the **uploading an existing file** link.
3. Open `D:\GitHub Website` in File Explorer. Hold **Ctrl** and click each file and folder from the "upload only these" list above, then drag them all into the browser window together.
   - Drag the `assets` folder itself, not the files inside it. That keeps the `assets/images/` path the site expects. Folder drag-and-drop works in Chrome and Edge.
   - `.nojekyll` is an empty file, and some browsers skip empty files. If it isn't in the upload list, you can leave it out. The site has no files whose names start with an underscore, so it works without it.
4. Wait until every file shows in the list under the drop area. Then, under **Commit changes**, type a short message such as `Initial portfolio site`. Leave **Commit directly to the main branch** selected and click **Commit changes**.
5. Check the repository's file list. `index.html`, `styles.css`, `script.js`, and `Vishrut Chokshi_Resume.pdf` should be at the top level, with `assets/images/` holding the `.webp` figures. If the images landed at the top level instead of inside `assets/images/`, delete them and upload the `assets` folder again.
6. Go to **Settings > Pages** (the Settings tab is on the repository, not your profile).
7. Under **Build and deployment**, set **Source** to **Deploy from a branch**. Set **Branch** to `main` and the folder to `/ (root)`, then click **Save**.
8. Wait one to two minutes and refresh the Pages settings page. The live URL appears at the top with a **Visit site** button. The **Actions** tab shows the deploy in progress if you want to watch it.

### Updating the site later

1. Edit the file on your computer, for example `index.html`, or save a new resume over `Vishrut Chokshi_Resume.pdf`.
2. On the repository's main page, click **Add file > Upload files**.
3. Drag in only the files you changed. A file with the same name and path replaces the old one. To replace an image, drag in the `assets` folder containing it, so the path matches.
4. Click **Commit changes**. Pages redeploys automatically in a minute or two.

To fix a typo quickly, you can also open a file on GitHub, click the pencil icon (**Edit this file**), make the change, and click **Commit changes**.

To remove a file, open it on GitHub, click the **...** menu at top right, and choose **Delete file**.

If the live site still shows the old version after a few minutes, hard-refresh the page (**Ctrl+F5**). Browsers cache CSS and images.

## Colors

The site uses one palette, defined at the top of `styles.css` under `:root`: Dark Chocolate #37261A, Marlborough Blue #8AA2BA, Khadi #DED9D0, Blackout #1E1E1E, and Bronco #AAA194. Every text and background pairing meets WCAG AA. Marlborough and Bronco are only used for backgrounds, rules, and decoration, never for small text on Khadi.
