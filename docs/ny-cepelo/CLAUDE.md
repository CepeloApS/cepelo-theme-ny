# CLAUDE.md – cepelo-theme-ny

Instruktioner til Claude Code for det nye cepelo.dk-theme. Ligger i `docs/ny-cepelo/`. Læs hele filen før første ændring.

## Projektet

Nyt Shopify-theme til cepelo.dk (Shopify Plus, B2B-fokus), bygget fra bunden med ren kode. Det eksisterende theme omstruktureres ikke, og der kopieres ingen kode fra det.

Mål:
- To tydelige indgange: **Løsninger og viden** og **Shop**.
- Færre klik til guides, support og viden.
- Missionen »Vi sikrer fremtidens værksted« er H1 på forsiden.
- SEO og GEO/AIO (AI-søgning) på tværs af hele sitet.

Kildedokumenter (beslutninger, ikke forslag):
- `docs/ny-cepelo/beslutninger/01-referat-github-seo-engine-geo.md` (21. okt. 2026)
- `docs/ny-cepelo/beslutninger/02-designforslag-struktur-og-sider.md` (27. okt. 2026)
- `docs/ny-cepelo/beslutninger/03-seo-geo-structured-data.md` (27. okt. 2026)
- `docs/ny-cepelo/design/` – HTML-mockups af alle sider fra design-canvasset »Ny cepelo.dk – forslag«
- `docs/ny-cepelo/kampagne/` – End of Year Sale 2026 (indhold til kampagnesektionen)
- `docs/ny-cepelo/metafelter.md` – feltkontrakt mellem theme, Shopify Admin og SEO Engine

Ved konflikt mellem dokumenterne gælder den nyeste dato. Ved konflikt med dette dokument gælder dette dokument.

## Teknisk opsætning

| Lag | Valg |
| --- | --- |
| Platform | Shopify Plus, Online Store 2.0 (JSON-templates, sections, section groups) |
| Repo | `CepeloApS/cepelo-theme-ny` på GitHub (kan senere overføres til `hplorentzen`) |
| Deploy | Shopifys indbyggede GitHub-integration. Ingen Vercel – Shopify hoster temaet |
| CI | GitHub Actions kører Theme Check på hver PR (`.github/workflows/theme-check.yml`) |
| Lokal udvikling | Shopify CLI: `shopify theme dev --store <butik>.myshopify.com` |

Vercel bruges kun, hvis der bygges en separat app uden for temaet (fx en afkastberegner med backend). Det er et bevidst arkitekturvalg, der skal afklares med Jonas først, og som følger CEPELOs tekniske standard (GitHub, Supabase EU, Vercel, Entra ID).

### Branches og themes
Følg reglerne i repoets `README.md`:
- `main` er den godkendte version af det nye theme. `kladde` forbindes til et upubliceret theme i Shopify. Push aldrig direkte til nogen af dem.
- Lav en branch ud fra `kladde`, fx `jonas/<emne>`, og opret en pull request til `kladde`. Peter godkender og fletter.
- Push ikke med `shopify theme push`. Integrationen synkroniserer `kladde` automatisk.
- Theme-editoren i Shopify skriver ændringer tilbage til `kladde`. Kør altid `git pull` først, og ret ikke `config/settings_data.json` eller `templates/*.json` uden at have hentet seneste version.

**Besluttet 19. november 2026:** Det nye theme bygges fra bunden i dette repo, `CepeloApS/cepelo-theme-ny`. Det nuværende live-theme ligger fortsat i `hplorentzen/cepelo-theme` og røres ikke. Repoet kan senere overføres til `hplorentzen`; så skal Shopify-forbindelsen og Claude-appen sættes op igen fra Peters konto.

### Produktionsforsigtighed
- Publicér aldrig et theme og push aldrig til live-themet.
- Skriv aldrig til Shopify Admin-data (produkter, kollektioner, metafelter, sider, menuer) uden udtrykkelig godkendelse fra Jonas i chatten. Læs og verificér først.
- Ingen API-nøgler, tokens eller adgangskoder i koden eller i commits. Shopify CLI logger ind via browser.

## Datakilder – hvert system ejer sin del

| System | Ejer |
| --- | --- |
| Produktdatakilde (se note) | Produktdata: titel, intro, beskrivelse, specifikationer, billeder, brand, FAQ, video-ID, feature-blokke |
| Shopify Admin | De seks løsninger, fælles fakta (SOH-pris, leasing, åbningstider), menu, kollektioner |
| SEO Engine | Artikler, meta-titler og -beskrivelser, `kort_svar`, `faq`, `seo_tekst`, links begge veje, GEO-måling |
| Theme (dette repo) | Visning og structured data. Ingen fakta hardcodes i Liquid |

**Note – åbent punkt:** Dokumenterne fra oktober nævner Plytix som produktdatakilde og HubSpot til leads. Siden er det besluttet, at Plytix og HubSpot udfases og erstattes af CEPELOs eget intranet (bygget med Claude Code). Temaet skal derfor læse produktdata fra **Shopify-produktfelter og metafelter** uanset hvilket system der fylder dem. Byg ikke noget, der afhænger direkte af Plytix eller HubSpot (scripts, embeds, formularer), før Jonas har bekræftet, hvordan intranettet synker til Shopify og håndterer formularer.

## Designregler (fra 27. oktober – gælder over brand-guiden ved konflikt)

- Ingen cirkler eller halvcirkler – hverken som dekoration, badges, ikoner eller knapper. Knapper og kort har små hjørner (4–8 px). Brand-guidens cirkulære badges og PDF-kampagnens runde »TILBUD«-mærker bruges **ikke** på sitet.
- Al tekst er sort (`#000000`). Kun tekst på blå knapper og »Nyhed«/»Kampagne«-mærker er hvid.
- Ingen små overskrifter over de store (fx »01 · ARBEJDSGANG«).
- Ingen dekorative streger. Afsnit adskilles med lys grå baggrund (`#F0F0F0`).
- Samme header og footer på alle sider (section groups).
- Den blå bjælke på produktsiden er lys blå (`#35B6EA`) med sort tekst.
- Ikoner: tynd sort streg, ingen udfyldning, aldrig emojis.

### Tokens (se `assets/base.css`)
| Token | Værdi |
| --- | --- |
| CEPELO Blå (knapper, links ved hover) | `#0868B2` |
| Mørk Navy (hover på knap) | `#173454` |
| Lys blå accent | `#35B6EA` |
| Off-white (afsnit, kort) | `#F0F0F0` |
| Lys grå (input-kanter) | `#D8D8D8` |
| Tekst | `#000000` |
| Overskrifter | Montserrat ExtraBold (800), uppercase |
| Brødtekst | Open Sans (300/400/600) |
| Indholdsbredde | max 1280 px, 32 px sidemargin (16 px under 720 px) |

Logo: `https://cdn.shopify.com/s/files/1/0590/4410/2221/files/CEPELO-Blue-Black-text.png?v=1781856465` (lys baggrund). Hent fra URL, ikke lokal kopi.

Virksomhedsdata (må ikke gættes): CEPELO A/S · Nibevej 54, 9200 Aalborg SV · CVR DK35818332 · CEPELO Norway AS. Rådgivning 98 18 09 00 · teknisk support 98 18 02 03.

## SEO og GEO – regler i koden

- **Én H1 pr. side.** Forsiden: »Vi sikrer fremtidens værksted«.
- **Kort svar øverst** på løsningssider, Academy, support og kategorier (metafelt `kort_svar`).
- **Al vigtig tekst i HTML ved sideindlæsning.** Accordions er `<details>`. Mega-menuen er almindelige `<a href>` i HTML; JavaScript åbner den kun visuelt.
- **Brødkrummer** på alle undersider, synlige og som BreadcrumbList.
- **Structured data** genereres som JSON-LD i `snippets/structured-data-*.liquid` ud fra felter. Se tabellen i `docs/ny-cepelo/beslutninger/03-seo-geo-structured-data.md`. AggregateRating kun ved rigtige anmeldelser.
- **Priser** vises og markeres ekskl. moms (`valueAddedTaxIncluded: false`). Forhandlerpriser bag login markeres ikke.
- **Filtre** (lager, brand, type) får `noindex` eller canonical til hovedkollektionen.
- **Brandnavne staves ens:** CEPELO, Autel, MaxiSys, EVDiag Box 2, Zmartgear, ISOtunes.
- **Tal kræver kilde.** »312 % ROI« vises kun med kilde og forudsætninger fra et felt.
- **Links begge veje** (produkt ↔ guide ↔ løsning) styres af metafelter, ikke manuelt i tekst.

## Indhold og sprog

- Al tekst i temaet er dansk og ligger i `locales/da.default.json`. Norsk (`nb.json`) afventer ledelsens beslutning.
- Tone: klar, teknisk kompetent, jordnær. Korte sætninger. Ingen marketingfloskler.
- Opfind aldrig fakta, priser, citater, anmeldelser eller adresser. Mangler noget, brug en synlig pladsholder som `[ÅBNINGSTIDER KOLDING]` og nævn det i PR-beskrivelsen.

## Om design-mockups i `docs/ny-cepelo/design/`

- `.dc.html`-filerne er mockups fra design-canvasset. Brug dem som facit for layout, rækkefølge, tekster og komponenter – ikke som kode, der kopieres ind.
- Billeder med `/_blob/…` virker kun i canvasset. I temaet kommer billeder fra Shopify (produkter, filer eller section-indstillinger).
- `{{ … }}`, `<sc-for>`, `<sc-if>` og `<dc-import>` er canvas-syntaks. Oversæt til Liquid-sections med blocks og schema-indstillinger.
- Filer med præfikset `Foer-` er den gamle version og ikke medtaget.

## Arbejdsgang for Claude Code

1. Én opgave pr. branch og PR. PR-beskrivelsen siger kort: hvad, hvorfor, hvilke pladsholdere der mangler data, og hvordan det testes i preview.
2. Kør `shopify theme check` lokalt før commit.
3. Byg mobil først; alle sider skal virke ved 390 px uden vandret scroll.
4. Tilgængelighed: rigtige `<button>`, `<a href>`, `<label>` til inputs, kontrast mindst 4,5:1, touch-mål mindst 44 px.
5. Ingen eksterne scripts eller apps uden aftale. Fonte via Google Fonts med `display=swap`, eller hostet i `assets/`.
6. Spørg Jonas før beslutninger, der kræver ledelsen (se `README.md` → Åbne beslutninger).
