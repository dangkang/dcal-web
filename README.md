# dCal Landing Page

The static site that lives at https://dcal.app (or
https://dangkang.github.io/hycalendar-mac/ as a fallback).

## Structure

```
docs/
├── index.html       ← Hero, features, pricing, FAQ
├── privacy.html     ← Privacy policy (JA + EN)
├── terms.html       ← Terms of use (JA + EN)
├── _config.yml      ← GitHub Pages / Jekyll config
└── assets/
    └── style.css    ← Single CSS file for the whole site
```

## Deploying via GitHub Pages

1. Repository **Settings** → **Pages**
2. **Source**: `Deploy from a branch`
3. **Branch**: `main` / `docs` folder
4. Click **Save**

After ~1 minute the site is published at
`https://<username>.github.io/<repo>/`.

## Custom domain (`dcal.app`)

1. Purchase the domain (お名前.com / Cloudflare Registrar)
2. Add a `CNAME` file under `docs/` containing exactly `dcal.app`
3. At the DNS provider, add an `ALIAS` / `ANAME` / `CNAME` record pointing
   `dcal.app` → `<username>.github.io`
4. Wait for DNS propagation (~minutes); GitHub auto-provisions HTTPS via
   Let's Encrypt

## Local preview

```bash
cd docs/
python3 -m http.server 8000
# → open http://localhost:8000/
```

(No Jekyll needed locally — the site is plain HTML/CSS.)

## Editing notes

- Plain HTML so the file is self-contained and re-styleable.
- Mobile breakpoint at 640px (`@media (max-width: 640px)`).
- Accent colour is defined once as `--accent: #2563eb` in `assets/style.css`.
- Privacy / Terms also live as Markdown copies in the repo root (PRIVACY.md /
  TERMS.md) for code-side reference.
