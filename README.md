# Federated HPC 2026 — Workshop Website

One-page website for the **Federated HPC: Privacy-Preserving and Collaborative High-Performance Scientific Computing** workshop, held in conjunction with **HiPC 2026**.

It is a single, self-contained `index.html` (HTML + CSS + JavaScript all inline) — no build step, no dependencies, no framework. Just open the file or drop it on any static host.

---

## Quick preview

Double-click `index.html`, or from this folder run a tiny local server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

---

## Host it free on GitHub Pages

1. **Create a repository** on GitHub (e.g. `fedhpc-2026`). Public is required for free Pages.
2. **Add these files** to the repo — either drag-and-drop in the browser (*Add file → Upload files*) or via git:

   ```bash
   git init
   git add index.html README.md
   git commit -m "Add workshop website"
   git branch -M main
   git remote add origin https://github.com/<your-username>/fedhpc-2026.git
   git push -u origin main
   ```
3. **Turn on Pages:** repo **Settings → Pages → Build and deployment**. Set **Source** to *Deploy from a branch*, **Branch** to `main`, folder `/ (root)`, then **Save**.
4. Wait ~1 minute. Your site is live at:

   ```
   https://<your-username>.github.io/fedhpc-2026/
   ```

Every future `git push` (or upload) redeploys automatically.

### Custom domain (optional)
In **Settings → Pages → Custom domain**, add e.g. `fedhpc2026.org`, then point a `CNAME` DNS record at `<your-username>.github.io`.

---

## What to edit before going live

Open `index.html` and search for these `<!-- EDIT ... -->` comments:

| Look for | What to change |
|---|---|
| `EDIT DATES HERE` | The six key dates (currently Aug 2 → Nov 20, 2026). |
| `EDIT SUBMISSION LINK HERE` | Replace `href="#"` on the **Go to submission site** button with your **Linklings** URL once it is live (`id="submitLink"`). |
| `EDIT CONTACT EMAIL + HiPC LINK HERE` | Replace `workshop@example.com` with your real email, and confirm the `https://hipc.org` link. |
| Speakers section | Update **invited speakers** (marked *tentative*). |
| Program committee | 14 members are listed; add/remove `.pc-item` blocks as needed. |

Everything else — title, tagline, topics, organiser bios — is plain text inside clearly-labelled `<section>` blocks and safe to edit directly.

### Adding a header/banner image
The reference site uses a conference banner. To add one, drop an image in the repo and place it at the top of the hero, e.g. inside the `.hero__copy` block:

```html
<a href="https://hipc.org"><img src="hipc-banner.jpg" alt="HiPC 2026" style="border-radius:12px;margin-bottom:1.5rem;max-width:420px;"></a>
```

---

## Design notes (for anyone maintaining it)

- **Colours, type, and spacing** are all defined as CSS variables in the `:root { ... }` block near the top of the `<style>` section — change the palette in one place.
- **Fonts:** Space Grotesk (headings), IBM Plex Sans (body), IBM Plex Mono (dates/labels), loaded from Google Fonts.
- The animated **federation diagram** in the hero is inline SVG; it automatically freezes for visitors who prefer reduced motion.
- Responsive down to mobile, keyboard-focus states included.

## Splitting into separate files (optional)
If you'd rather keep CSS/JS in their own files, move the contents of `<style>` into `styles.css` and `<script>` into `script.js`, then reference them:

```html
<link rel="stylesheet" href="styles.css">
<script src="script.js" defer></script>
```

---

## License
You own this content. Feel free to adapt it for the workshop. Attribution to speakers/committee members is as provided in the workshop proposal.
