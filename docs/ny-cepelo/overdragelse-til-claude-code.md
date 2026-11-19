# Overdragelse til Claude Code – ny cepelo.dk

Status 19. november 2026. Læs denne fil først. Den samler, hvor arbejdet med den nye cepelo.dk står, og hvad næste skridt er.

## Kort fortalt

CEPELO bygger en ny webshop på cepelo.dk (Shopify Plus). Strukturen deles i to indgange: **Løsninger og viden** og **Shop**. Missionen »Vi sikrer fremtidens værksted« er H1 på forsiden. SEO og GEO/AIO (AI-søgning) indtænkes på tværs af hele sitet.

Design, beslutninger og regler er færdige. Theme-koden er ikke påbegyndt.

## Hvor tingene ligger

| Hvad | Hvor |
| --- | --- |
| Repo (nyt theme) | `CepeloApS/cepelo-theme-ny` (privat), oprettet 19.11.2026 |
| Repo (live theme) | `hplorentzen/cepelo-theme` (privat). Kopi af det live theme pr. 12.11.2026. Røres ikke |
| Startpakke | `docs/ny-cepelo/` på branchen `jonas/ny-cepelo-startpakke`, PR #2 til `kladde` |
| Instruktioner til Claude Code | `docs/ny-cepelo/CLAUDE.md` |
| Byggerækkefølge og åbne beslutninger | `docs/ny-cepelo/README.md` |
| Beslutninger fra oktober | `docs/ny-cepelo/beslutninger/` (referat 21.10, designforslag 27.10, SEO/GEO og structured data 27.10) |
| Design-mockups (facit for layout og tekster) | `docs/ny-cepelo/design/` – 12 sider inkl. fælles header med mega-menu og footer |
| Feltkontrakt (metafelter) | `docs/ny-cepelo/metafelter.md` – udkast, skal godkendes |
| GitHub-opsætning og adgang | `docs/ny-cepelo/github-opsaetning.md` |
| Kampagne (End of Year Sale 2026) | `docs/ny-cepelo/kampagne/` – PDF mangler |
| Shopify-butik | `cepelotools.myshopify.com` |

## Regler i repoet (fra repoets README)

- Push aldrig direkte til `main` (live theme) eller `kladde` (forbundet til et upubliceret theme i Shopify).
- Lav en branch ud fra `kladde`, fx `jonas/<emne>`, og opret en PR til `kladde`. Peter godkender og fletter.
- Publicér aldrig et theme. Push ikke med `shopify theme push`. Integrationen synkroniserer `kladde` automatisk.
- Forhåndsvis lokalt med `shopify theme dev --store cepelotools`.
- Ingen nøgler, tokens eller adgangskoder i repoet.
- Skriv aldrig til Shopify Admin-data (produkter, kollektioner, metafelter, sider, menuer) uden udtrykkelig godkendelse fra Jonas.

## Vigtigste designregler

- Ingen cirkler eller halvcirkler. Hjørner 4–8 px.
- Al tekst sort (`#000000`). Kun tekst på blå knapper og »Nyhed«/»Kampagne«-mærker er hvid.
- Ingen små overskrifter over de store. Ingen dekorative streger – afsnit adskilles med `#F0F0F0`.
- Samme header og footer på alle sider.
- Farver: `#0868B2` (knapper), `#173454` (hover), `#35B6EA` (blå bjælke på produktside, sort tekst), `#F0F0F0`, `#D8D8D8`.
- Montserrat 800 uppercase til overskrifter, Open Sans til brødtekst. Max bredde 1280 px.
- Opfind aldrig fakta, priser, citater eller anmeldelser. Brug synlige pladsholdere som `[ÅBNINGSTIDER KOLDING]`.

Fuld liste i `docs/ny-cepelo/CLAUDE.md`.

## Datakilder

Plytix og HubSpot udfases og erstattes af CEPELOs eget intranet. Temaet læser kun fra Shopify-produktfelter og metafelter. Byg intet, der afhænger direkte af Plytix eller HubSpot. SEO Engine (repo `cepelo-seo`) ejer `kort_svar`, `faq`, `seo_tekst` og links mellem produkter, guides og løsninger.

## Byggerækkefølge (én PR pr. punkt)

1. Grundstruktur: `assets/base.css` med tokens, fonte, `layout/theme.liquid`, Theme Check i GitHub Actions
2. Header med mega-menu og footer som section groups
3. Structured data: Organization, WebSite, BreadcrumbList, LocalBusiness
4. Forside
5. Produktside + Product, VideoObject, FAQPage
6. Kollektion og »Alle produktkategorier«
7. Løsningsside + Service, FAQPage
8. Løsninger og viden-hub, blog og artikler
9. Support og Academy + Course
10. Mobiltjek (390 px) og tilgængelighed

## Åbne punkter, før der skrives theme-kode

- [x] **Hvor bygges det nye theme?** Besluttet 19.11.2026: i `CepeloApS/cepelo-theme-ny`. *Oprindeligt spørgsmål:* Beslutningen 21. oktober var et nyt theme fra bunden. Repoet indeholder det nuværende theme. Afklar med Peter og Nuno: byg i dette repo (fx i en ny branch forbundet til eget upubliceret theme) eller i et nyt repo under organisationen `cepelo`.
- [x] **Claude-appen:** Har adgang til `CepeloApS/cepelo-theme-ny`. *Oprindeligt punkt:* Peter giver Claude GitHub-appen adgang til `cepelo-theme` (github.com/settings/installations › Claude › Configure), eller repoet flyttes til `cepelo`, hvor Nuno installerer appen. Først derefter kan Claude Code i skyen arbejde i repoet fra alle computere.
- [ ] Startpakken (denne mappe) gennemgås og flettes til `kladde` i `cepelo-theme-ny`. PR #2 i `hplorentzen/cepelo-theme` kan lukkes uden fletning.
- [ ] Intranettets sync til Shopify og håndtering af formularer (PDF-guides, Book demo).
- [ ] Gennemgå og godkend `metafelter.md`.
- [ ] URL-struktur og 301-redirects for de 10 produktgrupper.
- [ ] Indhold, der mangler: kampagne-PDF, Academy-program og datoer, PDF-guides, adresse og åbningstider i Kolding, kilde til 312 % ROI, kilde til anmeldelser, logoer til Beissbarth og Fastlign.

## Personer

| Person | GitHub-bruger | Rolle |
| --- | --- | --- |
| Jonas Lind-Bendixen | `CepeloApS` | Marketing, ejer af webshop-projektet |
| Peter Lorentzen | `hplorentzen` | Ejer af `cepelo-theme`. Godkender og fletter PR'er |
| Nuno Franco | – | Teknik og organisationen `cepelo` |

## Første prompt til Claude Code

> Læs `docs/ny-cepelo/overdragelse-til-claude-code.md`, `docs/ny-cepelo/CLAUDE.md` og `docs/ny-cepelo/README.md` på branchen `jonas/ny-cepelo-startpakke`. Følg repoets regler: branch ud fra `kladde`, PR til `kladde`. Før du skriver theme-kode, så bekræft med mig, hvor det nye theme skal bygges. Start derefter med punkt 1 i byggerækkefølgen.
