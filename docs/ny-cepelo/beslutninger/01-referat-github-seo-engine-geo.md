# cepelo.dk – referat: GitHub, SEO Engine og GEO

Oct 21, 2026 · @Jonas

Vi bygger et helt nyt Shopify-theme til cepelo.dk med ren kode fra bunden. Det eksisterende theme omstruktureres ikke. Udgangspunktet er gennemgangen af 19. oktober 2026: hurtige rettelser, ny menu og shop, seks løsningssider, ny forside og løbende forbedring af produktdata.

Referatet dækker tre beslutninger: hvordan temaet styres, hvem der ejer hvilke data, og hvordan siden kobles til SEO Engine og optimeres til AI-søgning (GEO/AIO).

## Nyt theme i GitHub

Det nye theme bygges fra bunden i repoet `hplorentzen/cepelo-theme` og forbindes til Shopify via den indbyggede GitHub-integration. Det følger vores tekniske standard og den måde, SEO Engine allerede kører på.

- **Historik:** Alle ændringer gemmes med hvem, hvad og hvornår. I dag kan ingen se, hvad bureauet og vi selv har ændret.
- **Fortryd:** Vi kan rulle tilbage til en tidligere version med det samme.
- **Test før live:** Ændringer godkendes i et preview-theme, før de rammer cepelo.dk.
- **Samarbejde:** Bureau, interne folk, SEO Engine og Claude arbejder i samme kode uden at overskrive hinanden.

Ingen kode fra det gamle theme kopieres over, så der ikke følger rester eller unødvendig kode med. Tester-skabelonen fra kladdetemaet bruges kun som reference. Theme-editoren kan stadig bruges, og ændringer derfra gemmes automatisk i GitHub.

## Hvert system ejer sin del

Hver type data har én ejer. Skriver to systemer i samme felt, overskriver de hinanden, og modstridende fakta skader både kunder og AI-søgning.

| System | Ejer | Bemærkning |
| --- | --- | --- |
| Plytix | Produktdata: titel, intro, beskrivelse, specifikationer, billeder, brand, FAQ | Rettelser af produkter laves her, ellers overskrives de ved næste sync |
| Shopify Admin | De seks løsninger, fælles fakta (SOH-pris, leasing), menu, kollektioner | Ét sted pr. fakta |
| SEO Engine | Artikler, meta-titler og -beskrivelser, teknisk audit, GEO-måling | Skriver ikke produkttekster direkte i Shopify |
| Theme (GitHub) | Visning og structured data | – |

De hurtige rettelser og de ti nye kategorier fra gennemgangen er dermed overvejende data og ikke kode.

## SEO Engine og AI-søgning (GEO/AIO)

Siden bygges, så SEO Engine kan udfylde faste felter, og temaet viser dem som indhold og structured data.

- **Én blog:** Engine publicerer til en samlet Viden-blog. Artikler tagges med løsning og vises automatisk på løsningssiderne.
- **Faste felter:** kort svar, FAQ og løsningsreference som metafelter. Formatet dokumenteres i begge repos.
- **Hurtigere indeksering:** Engine giver Bing besked ved nye artikler. ChatGPT-søgning bygger på Bing.
- **Structured data:** Siden har i dag Organization, Product og Breadcrumb. Der mangler FAQ, Article, Service, Course, LocalBusiness (showrooms) og VideoObject.
- **Indhold:** Kort svar øverst på hver side, al vigtig tekst synlig i HTML, kilde på nøgletal som »312 % ROI«, og brandnavnet stavet ens.

**Produkter og indhold linker altid begge veje.** Hvert produkt, der nævnes i en artikel, FAQ eller guide, linker til produktsiden, og produktsiden linker tilbage til indholdet. Linkene styres af faste felter og ikke manuelt i teksten. SEO Engine udfylder dem i begge retninger, og felterne på produkterne undtages fra Plytix-synken, så de ikke overskrives.

Vi kan optimere alt, vi selv styrer. Om AI-tjenester citerer os, kan ingen garantere. Derfor får SEO Engine en måling af, hvor ofte Cepelo nævnes.

## HubSpot (Enterprise)

HubSpot gør »Book demo« og »Beregn dit afkast« til målbare leads og viser, om SEO og GEO skaber salg. Indholdet bliver på cepelo.dk. HubSpot står for leads, opfølgning og måling.

| Hub | Bruges til |
| --- | --- |
| Marketing | Afkastberegner som formular, behavioral events (løsningssider, beregner, dyre produkter), lead scoring pr. løsning, revenue attribution inkl. AI-trafik som egen kanal, nyhedsbrev med subscription types |
| Sales | Meetings til »Book demo« (Aalborg/Kolding), tilbud via Quotes fra afkastberegneren, sequences efter demo |
| Service | Reklamation som ticket, AI-kundeagent trænet på cepelo.dk |
| Content | Kampagnesider og nyhedsbreve, sat til `noindex` så de ikke konkurrerer med løsningssiderne |

To regler: Vejledninger og andet indhold, som AI skal kunne finde, ligger på cepelo.dk og ikke i HubSpot. Leasingvilkår og priser i HubSpot-mails hentes fra samme kilde som hjemmesiden.

## Næste skridt

- [ ] Opret repoet og byg det nye theme fra bunden i et preview-theme
- [ ] Aftal nye produktfelter i Plytix og deres sync til Shopify med den, der ejer Plytix
- [ ] Forny SEO Engines Shopify-adgang, som udløber i november, og tilføj læseadgang til produkter
- [ ] Ret fejlene fra gennemgangen (skridt 1)

**Kræver beslutning fra ledelsen:** de fem punkter fra gennemgangen (elektronik/retail, ejer af produktdata, prisvisning, de seks løsninger, hvor fakta bor) samt om den norske side skal have norsk indhold.

> Note 10. november 2026: Plytix og HubSpot udfases og erstattes af CEPELOs intranet. Se `CLAUDE.md` → Datakilder og `docs/ny-cepelo/metafelter.md`.
