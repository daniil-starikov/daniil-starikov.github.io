# Daniil Starikov's academic website

Plain HTML/CSS, no build step. Four pages (`index.html`, `research.html`,
`teaching.html`, `olympiads.html`) sharing `assets/css/style.css`; images,
PDFs, and icons live under `assets/` too. The nav bar's "CV" link points
directly at the PDF rather than a separate page. Deploys to GitHub Pages
with zero configuration.

## 1. Put it on GitHub Pages

1. Create a GitHub account if you don't have one.
2. Create a new repository named exactly `<your-github-username>.github.io`
   (this exact name is what makes GitHub serve it as a website automatically).
3. Upload these files into that repository (drag-and-drop on github.com
   works fine for a first version — no git command line required).
4. Go to **Settings → Pages** in the repo and confirm the source is the
   `main` branch, root folder. GitHub Pages serves plain HTML with no
   build step, so there is nothing else to configure.
5. Your site is live at `https://<your-username>.github.io` within a
   few minutes.

## 2. Optional: custom domain

Buy a domain (e.g. `firstnamelastname.com`, ~$10-15/year from any
registrar). Add a `CNAME` file to the repo root containing just the
domain name, then point the registrar's DNS at GitHub Pages per
GitHub's custom-domain docs. Not required to start.

## 3. Google Analytics

1. Create a free GA4 property at analytics.google.com.
2. Copy your Measurement ID (`G-XXXXXXXXXX`).
3. Uncomment the GA snippet in the `<head>` of every HTML file and
   paste in your ID.
4. Push the change — traffic starts appearing in GA within a day.

Note on what this will and won't tell you: GA shows you referral
source (e.g. someone clicked a link from your department's page or
from Twitter/X), rough visit volume over time, and city-level
geolocation from IP address. It does **not** reliably tell you "someone
from Yale visited" — GA has no built-in employer/institution
lookup, and privacy changes (cookie consent, VPNs, corporate
networks) have made even old-school "reverse DNS on the visitor's IP"
tricks unreliable. What it's genuinely useful for: seeing when
traffic spikes (e.g. the week your department posts its job-market
list) and which channels are driving visits.

## Next steps as your site grows

This is intentionally a minimal v1. Once you want more automation —
a publications list that auto-generates from a BibTeX file, blog
posts, etc. — natural upgrades are the Jekyll theme `al-folio` or
Pascal Michaillat's minimalist Hugo template, both free and built
for exactly this use case. Migrating your content over is
straightforward since it's just text.
