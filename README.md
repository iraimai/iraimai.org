# iraimai.org (GitHub Pages Launch Site)

Minimal, obsidian-dark static launch site for **https://iraimai.org**, designed as a direct sister surface to **https://naveenriaz.com**.

## Files Included

| File | Purpose |
| :--- | :--- |
| `index.html` | Single-page Launch Mode landing surface (`IRAIMAI · Becoming AI-Sovereign`) |
| `styles.css` | Layered modern CSS (`@layer reset, base, theme, layout, components, utilities`), dark starfield, MBS tokens |
| `assets/iraimai-mark.jpg` | Official circular gold IRAIMAI mark (`754x754`, used directly without SVG conversion) |
| `assets/iraimai-logo-en.jpg` | Official gold English lockup (`IRAIMAI · SOVEREIGNTY`, `1024x1024`, Hero centerpiece + `og:image`) |
| `assets/iraimai-logo-ta.jpg` | Official gold Tamil lockup (`இறைமை · SOVEREIGNTY`, `1024x1024`, Thirukkural 388 Sovereignty seal) |
| `assets/favicon.png` | `64x64` raster PNG downsampled directly from `iraimai-mark.jpg` |
| `assets/apple-touch-icon.png` | `180x180` raster PNG downsampled directly from `iraimai-mark.jpg` |
| `404.html` | Matching GitHub Pages 404 fallback |
| `CNAME` | Custom domain binding (`iraimai.org`) for GitHub Pages |

## 1. Deploy to GitHub Pages (3 Minutes)

1. Create a new **public** repository on GitHub (for example `naveenriaz/iraimai.org` or `thirvemarchcraft/iraimai.org`).
2. Push this folder directly as the root of that repository:

```bash
cd /Users/naveen/synthanai/synthai-master-repo/01-soul/brand/iraimai-org-site
cp -R . /tmp/iraimai-org-ghpages
cd /tmp/iraimai-org-ghpages
git init -b main
git add .
git commit -m "launch: iraimai.org logo reveal"
git remote add origin git@github.com:iraimai/iraimai.org.git
git push -u origin main
```

3. On GitHub, open **Settings -> Pages**:
   - **Source**: `Deploy from a branch` -> `main` -> `/ (root)` -> **Save**.
   - **Custom domain**: Confirm `iraimai.org` is populated from `CNAME`.
   - Once DNS propagates (5 to 15 minutes), check **Enforce HTTPS**.

## 2. Namecheap Advanced DNS Setup (Preserving Google Workspace Email)

Keep all 4 of your existing Google Workspace records **untouched** and add the 5 GitHub Pages web records below under **Host Records**:

| Action | Type | Host | Value | TTL |
| :--- | :--- | :--- | :--- | :--- |
| **ADD** | `A Record` | `@` | `185.199.108.153` | Automatic |
| **ADD** | `A Record` | `@` | `185.199.109.153` | Automatic |
| **ADD** | `A Record` | `@` | `185.199.110.153` | Automatic |
| **ADD** | `A Record` | `@` | `185.199.111.153` | Automatic |
| **ADD** | `CNAME Record` | `www` | `iraimai.github.io.` | Automatic |
| **KEEP AS-IS** | `MX Record` | `@` | `SMTP.GOOGLE.COM.` (Priority `1`) | 1 min |
| **KEEP AS-IS** | `TXT Record` | `@` | `v=spf1 include:_spf.google.com ~all` | 1 min |
| **KEEP AS-IS** | `TXT Record` | `google._domainkey` | `v=DKIM1;k=rsa;p=MIIBIj...` | 1 min |
| **KEEP AS-IS** | `CNAME Record` | `stmazmfigoiw` | `gv-uvw6kwa6ydaq4g.dv.googlehosted.com.` | 1 min |

> Note: If Namecheap shows a default `Parking Page` CNAME (`www -> parkingpage.namecheap.com.`) or `URL Redirect Record` on `@`, remove only that parking/redirect record when adding the GitHub Pages records above. Never touch `MX` or Google `TXT` records.
