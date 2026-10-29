# dCal Landing Page

The static site that lives at https://dcal.dangkang.com/ (served by GitHub
Pages from this repo; https://dangkang.github.io/dcal-web/ redirects there).

## Structure

```
./
├── index.html       ← Hero, features, pricing, FAQ
├── privacy.html     ← Privacy policy
├── terms.html       ← Terms of use
├── tokusho.html     ← 特定商取引法に基づく表記
├── en/              ← English versions of the pages above
├── CNAME            ← Custom domain for GitHub Pages
├── _config.yml      ← GitHub Pages / Jekyll config
└── assets/
    └── style.css    ← Single CSS file for the whole site
```

## Deploying via GitHub Pages

1. Repository **Settings** → **Pages**
2. **Source**: `Deploy from a branch`
3. **Branch**: `main` / `/ (root)`
4. Click **Save**

After ~1 minute the site is published.

## Custom domain (`dcal.dangkang.com`)

1. The `CNAME` file at the repo root contains exactly `dcal.dangkang.com`
2. DNS for `dangkang.com` is managed at VALUE-DOMAIN. The zone has a
   wildcard `*` record, so `dcal` needs its own line:
   `cname dcal dangkang.github.io.`
3. GitHub provisions HTTPS via Let's Encrypt once DNS resolves; keep
   **Enforce HTTPS** on
4. Moved from `dangkang.github.io/dcal-web/` on 2026-10-29 so that the
   Stripe account lists a site on its own domain

## Local preview

```bash
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
