# personal_website

Personal website of Samir Pahari. A single-file site (`index.html`) plus `assets/` (headshot, CV PDF, link-preview image). Everything on the page is rendered from one `DATA` object; the map geometry and the Leaflet library are inlined at build time, so the site has no CDN dependency.

Live at https://samirpahari91.github.io/personal_website/ · `https://samirpahari91.github.io/personal_website/#cv` opens the plain CV directly (also the **R** key).

## Updating content
Open `index.html`, find `const DATA = {` and edit the record (education, research, jobs, talks, awards, places, milestones, spans, Q&A answers). Replace `assets/Samir_Pahari_CV.pdf` with a new CV. Commit; GitHub Pages redeploys in about a minute.

Rebuilding from source (optional): `source/src/*.js|html` are the readable parts; `cd source && python3 build.py` reassembles `index.html` (it expects Leaflet under `source/tools/node_modules`, so run `npm install` in `source/tools` first; `node genmap.mjs` there regenerates the map geometry).

## Custom domain (optional)
Settings → Pages → Custom domain, then at the registrar add `A` records for the apex → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 and a `CNAME` for `www` → `samirpahari91.github.io`. Tick "Enforce HTTPS" once the certificate is issued, and update the `og:image`, `twitter:image` and canonical URLs in `index.html` to the new domain.

## Basemap attribution
Imagery © Esri, Maxar, Earthstar Geographics, and the GIS User Community · OpenTopoMap (CC-BY-SA, data © OpenStreetMap contributors, SRTM) · © OpenStreetMap contributors, © CARTO. Vector coastlines: Natural Earth via world-atlas; US states via us-atlas. Leaflet 1.9.4 (BSD-2-Clause).
