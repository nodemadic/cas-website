# Complete Accounting Solutions — Website

Single-page site for Melanie Pepper / Complete Accounting Solutions.

Domain: `completeaccountingsol.com` (hosted via [Turbify](https://dcp.turbify.com/dcp/completeaccountingsol.com/dns)).

## Files

- `index.html` — page content
- `style.css` — burgundy + cream theme, responsive single-page layout

No build step. Plain HTML/CSS, hosted as-is.

## Local preview

```bash
cd cas-website
python3 -m http.server 8765
# open http://localhost:8765
```

## Deploy to Turbify

Turbify hosting offers two paths depending on the plan:

### Option A — Turbify SiteBuilder (drag-and-drop, may not accept raw HTML)

SiteBuilder is template-based and typically does not allow uploading arbitrary HTML/CSS. If Mel's plan only includes SiteBuilder, the cleanest path is to recreate the layout inside SiteBuilder, copying text/colors from `index.html` / `style.css`.

### Option B — Turbify Web Hosting (File Manager / FTP)

If the plan includes Web Hosting with file upload:

1. Log in to Turbify Hosting Control Panel.
2. Open **File Manager** (or connect via FTP — credentials under *Manage My Services* → *Web Hosting* → *FTP*).
3. Navigate to the `public_html/` (or `www/`) document root.
4. Upload:
   - `index.html`
   - `style.css`
5. Set `index.html` as the default document if not already.
6. Visit `https://www.completeaccountingsol.com/` to verify.

### DNS

DNS already points to Turbify nameservers (per [dcp.turbify.com/dcp/completeaccountingsol.com/dns](https://dcp.turbify.com/dcp/completeaccountingsol.com/dns)). No DNS change needed — just replace the "Under Construction" placeholder.

## Editing content

Resume text lives in `index.html`. Update sections in place:

- Hero contact info → top of `<body>`
- Services → `<section id="services">` cards
- Client experience → `<ul class="experience-list">`
- Contact info → `<section id="contact">`

Colors live in CSS custom properties at top of `style.css` (`--burgundy`, `--accent`, `--cream`).
