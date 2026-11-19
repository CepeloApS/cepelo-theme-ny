# cepelo-theme-ny – startpakke

Nyt Shopify-theme til cepelo.dk (Shopify Plus). Bygges fra bunden med Claude Code. Start med at læse `CLAUDE.md`.

## Indhold

| Mappe / fil | Hvad |
| --- | --- |
| `CLAUDE.md` | Instruktioner til Claude Code: teknik, designregler, SEO-regler, arbejdsgang |
| `docs/ny-cepelo/beslutninger/` | Referat og beslutninger fra oktober 2026 |
| `docs/ny-cepelo/design/` | HTML-mockups af alle sider fra design-canvasset (facit for layout og tekster) |
| `docs/ny-cepelo/metafelter.md` | Feltkontrakt: hvilke felter temaet læser, og hvem der ejer dem |
| `docs/ny-cepelo/kampagne/` | End of Year Sale 2026 – læg PDF'en her |
| `docs/ny-cepelo/indhold/` | Tekstudkast til sider, fx løsningen »ADAS og hjuludmåling« og ordlisten |
| `docs/ny-cepelo/overdragelse-til-claude-code.md` | Status og overdragelse pr. 19. november 2026 |

## Kom i gang

1. Installér Shopify CLI og log ind: `shopify theme dev --store <butik>.myshopify.com`
2. Åbn Claude Code i denne mappe.
3. Første opgave til Claude Code – se »Byggerækkefølge« nedenfor.

## Byggerækkefølge (én PR pr. punkt)

1. Grundstruktur: Online Store 2.0-skelet, `assets/base.css` med tokens, fonte, `layout/theme.liquid`, Theme Check i GitHub Actions
2. Header med mega-menu og footer som section groups (`docs/ny-cepelo/design/Header.dc.html`, `Footer.dc.html`)
3. Structured data-snippets: Organization, WebSite, BreadcrumbList, LocalBusiness
4. Forside (`Main.dc.html`)
5. Produktside (`Produkt.dc.html`) + Product, VideoObject, FAQPage
6. Kollektion og »Alle produktkategorier« (`Kategori.dc.html`, `Kategorier.dc.html`)
7. Løsningsside som metaobject-template (`Losning.dc.html`) + Service, FAQPage
8. Løsninger og viden-hub, blog og artikler (`Viden.dc.html`)
9. Support (`Support.dc.html`) og Academy (`Academy.dc.html`) + Course
10. Mobiltjek af alle sider (390 px) og tilgængelighed

## Åbne beslutninger

- Hvordan intranettet synker produktdata og håndterer formularer (afløser Plytix og HubSpot)
- URL-struktur og 301-redirects for de 10 produktgrupper
- Kilde til anmeldelser (Google eller Trustpilot)
- Elektronik og retail: Pro-shop eller ud af hovedsitet
- Norsk indhold (`nb.json`)
- Indhold, der mangler: Academy-program og datoer, PDF-guides, adresse og åbningstider i Kolding, kilde til 312 % ROI, logoer til Beissbarth og Fastlign
