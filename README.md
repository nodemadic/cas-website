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

## Hosting: GitHub Pages + Turbify DNS

Site is hosted free on **GitHub Pages** from this repo. Turbify keeps the domain but DNS points at GitHub.

- Repo: https://github.com/nodemadic/cas-website
- Pages URL (fallback): https://nodemadic.github.io/cas-website/
- Production URL (after DNS): https://www.completeaccountingsol.com

### DNS setup at Turbify

Log in to https://dcp.turbify.com/dcp/completeaccountingsol.com/dns and replace the existing records with these:

**Apex domain (`completeaccountingsol.com`) — 4 A records:**

| Type | Host | Value           |
|------|------|-----------------|
| A    | @    | 185.199.108.153 |
| A    | @    | 185.199.109.153 |
| A    | @    | 185.199.110.153 |
| A    | @    | 185.199.111.153 |

**www subdomain — 1 CNAME:**

| Type  | Host | Value                  |
|-------|------|------------------------|
| CNAME | www  | nodemadic.github.io.   |

**Remove** any existing A/CNAME records for `@` and `www` that point to Turbify hosting (often `*.bizhost.com`, `*.turbifyhosting.com`, or similar). Leave MX (email) records untouched if Mel uses Turbify email.

### After DNS propagates (5 min – 24 hr)

1. Verify DNS: `dig www.completeaccountingsol.com` should resolve to `nodemadic.github.io`.
2. Re-enable custom domain + HTTPS in GitHub:
   ```bash
   gh api -X PUT /repos/nodemadic/cas-website/pages \
     -f cname=www.completeaccountingsol.com -F https_enforced=true
   ```
3. Visit https://www.completeaccountingsol.com — should load the site.

### Editing the site

Edit `index.html` / `style.css` locally, commit, push — GitHub Pages auto-deploys in ~1 min.

## Editing content

Resume text lives in `index.html`. Update sections in place:

- Hero contact info → top of `<body>`
- Services → `<section id="services">` cards
- Client experience → `<ul class="experience-list">`
- Contact info → `<section id="contact">`

Colors live in CSS custom properties at top of `style.css` (`--burgundy`, `--accent`, `--cream`).
