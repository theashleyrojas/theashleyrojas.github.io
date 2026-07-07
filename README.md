# Ashley Rojas — academic website

A clean, static personal website for the economics job market. No build step,
no framework — just HTML + CSS. Easy to host free on GitHub Pages and edit yourself.

## Files

```
academic-website/
├── index.html        About / home (big photo, bio, featured job market paper)
├── research.html     Job market paper + working papers + works in progress
├── teaching.html     Courses (instructor of record + TA), teaching statement
├── cv.html           Embedded + downloadable CV
├── css/style.css     All styling (warm modern minimal palette)
├── assets/           Your photo + PDFs go here (see PUT-YOUR-FILES-HERE.txt)
├── CNAME             Your custom domain (edit this — see step 4)
└── .nojekyll         Tells GitHub Pages to serve the files as-is
```

## Step 1 — Fill in your details (find & replace)

Open the four `.html` files and replace these placeholders. They appear in every
file's footer, so use your editor's "replace in all files":

| Placeholder | Replace with |
|---|---|
| `YOUR_EMAIL@sc.edu` | your real email |
| `YOUR_LINKEDIN` | your LinkedIn handle (the part after `/in/`) |

Then personalize the content:
- **research.html** — edit/delete the "Working Papers" and "Works in Progress" blocks.
- **teaching.html** — fill in real course numbers, titles, and terms.
- **index.html** — tweak the bio paragraph if you'd like.

## Step 2 — Add your files

Put these in the `assets/` folder (exact names — then nothing else to edit):
`headshot.jpg`, `Rojas_CV.pdf`, `Rojas_JMP.pdf`, and optionally
`Rojas_JMP_slides.pdf`, `Rojas_teaching_statement.pdf`.
Until you add the photo, an "AR" placeholder shows automatically.

## Step 3 — Preview locally (optional)

From this folder:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000> in your browser. Ctrl-C to stop.

## Step 4 — Put it on GitHub Pages

1. Create a **free GitHub account** if you don't have one.
2. Create a new **public** repository. For the simplest URL, name it
   `YOURUSERNAME.github.io` (this gives you `https://YOURUSERNAME.github.io`).
3. Upload these files to the repo. Either drag-and-drop in the GitHub web UI
   ("Add file → Upload files"), or from this folder in a terminal:

   ```bash
   git init
   git add -A
   git commit -m "Initial website"
   git branch -M main
   git remote add origin https://github.com/YOURUSERNAME/YOURUSERNAME.github.io.git
   git push -u origin main
   ```

4. In the repo on GitHub: **Settings → Pages**. Under "Build and deployment",
   set Source = "Deploy from a branch", Branch = `main`, folder = `/ (root)`, Save.
5. Wait ~1 minute, then visit `https://YOURUSERNAME.github.io`. Done.

## Step 5 — Custom domain (you chose this)

1. Buy a domain (~$12/yr) from Namecheap, Cloudflare, Google Domains, etc.
   Something like `ashleyrojas.com` or `ashley-rojas.com`.
2. Edit the **CNAME** file in this repo so it contains only your domain, e.g.:

   ```
   www.ashleyrojas.com
   ```

3. At your domain registrar, add DNS records pointing to GitHub Pages:
   - A **CNAME record**: host `www` → value `YOURUSERNAME.github.io`
   - Four **A records** for the apex (`@`) so `ashleyrojas.com` works too:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
4. Back in **Settings → Pages → Custom domain**, enter your domain and save.
   Check "Enforce HTTPS" once it becomes available (can take a few hours).

Full reference: <https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site>

## Updating later

Edit a file, then either re-upload via the GitHub web UI, or:

```bash
git add -A && git commit -m "Update" && git push
```

Changes go live in about a minute.
