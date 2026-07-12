# aqualification.lv

Static site for Dr. Jeļena Solovjova — swimming coach education, seminars, consultations.

## Deploy to GitHub Pages

1. Create a new GitHub repo (e.g. `aqualification-site`) and push these files:
   ```
   git init
   git add .
   git commit -m "initial site"
   git branch -M main
   git remote add origin https://github.com/<user>/aqualification-site.git
   git push -u origin main
   ```
2. In the repo: **Settings → Pages → Source: Deploy from a branch → main / root**.
3. Under **Custom domain**, enter `aqualification.lv` and save.
4. Tick **Enforce HTTPS** once the cert is issued (may take a few minutes after DNS propagates).

## DNS (on SiteGround, where aqualification.lv lives)

In the SiteGround DNS Zone Editor, replace any existing A records for the apex domain with these four GitHub Pages A records:

| Type | Name | IPv4             |
|------|------|------------------|
| A    | @    | 185.199.108.153  |
| A    | @    | 185.199.109.153  |
| A    | @    | 185.199.110.153  |
| A    | @    | 185.199.111.153  |

Optionally add a CNAME `www → <user>.github.io` so `www.aqualification.lv` also resolves.

Remove the old SiteGround hosting A record for the apex if it conflicts. Propagation: up to a few hours.

## Editing content

Everything is in `index.html` — one file, inline CSS and JS. Latvian is the default DOM copy. English strings live in `data-en` / `data-en-html` attributes and are shown only after the visitor selects `EN` in the top-right language toggle.
