# cepelo.dk – SEO, GEO/AIO og structured data

27. oktober 2026. Gælder det nye theme. Supplerer `01-referat-github-seo-engine-geo.md`.

> Note 10. november 2026: Hvor der står Plytix eller HubSpot, læses feltet fra Shopify-produktfelter og metafelter. Se `docs/ny-cepelo/metafelter.md`.

## Principper på tværs af sitet
- **Kort svar øverst.** Løsningssider, Academy, support og kategorier åbner med 2–3 sætninger, der besvarer spørgsmålet direkte. AI-tjenester citerer typisk første afsnit.
- **Al vigtig tekst i HTML.** Ingen indhold kun i billeder, faner der loades med JavaScript eller PDF'er. Accordions (Beskrivelse, Specifikationer, FAQ) ligger i HTML og foldes kun visuelt.
- **Én H1 pr. side.** Forsiden: »Vi sikrer fremtidens værksted«. Undersider: sidens emne.
- **Spørgsmål som overskrifter.** SEO/GEO-blokken på produktsider bruger formatet »Hvad er …?«, »Hvem er den til?«, »Hvilke testere virker den med?«, så både søgemaskiner og AI kan matche spørgsmålet direkte.
- **Fakta ét sted.** Priser, leasing, SOH-pris og åbningstider hentes fra ét felt og vises ens overalt.
- **Kilde på tal.** »312 % ROI« og lignende vises kun med kilde og forudsætninger.
- **Brandnavne staves ens:** CEPELO, Autel, MaxiSys, EVDiag Box 2, Zmartgear, ISOtunes.
- **Links begge veje.** Produkt ↔ guide ↔ løsning styres af metafelter, som SEO Engine udfylder.

## Menu og kategorier
- **Menuen ligger i HTML.** Mega-menuen renderes som almindelige `<a href>`-links ved sideindlæsning. Den åbnes visuelt med JavaScript, men links må ikke først hentes ved klik.
- **Ti produktgrupper med egne sider.** Hver gruppe bliver en kollektion med H1, kort intro, underkategorier, produkter, SEO-tekst og FAQ. De fem løsningsgrupper linker til løsningssiden og omvendt.
- **Footeren gentager hovedstrukturen.** Løsninger, ti shop-grupper og viden/service skaber intern linkstyrke til alle hovedsider.
- **Brødkrummer på alle undersider.** Synlige og markeret med BreadcrumbList.
- **URL'er er korte og beskrivende,** fx `/collections/diagnose-og-programmering` og `/pages/elbil-service-og-reparation`. Gamle URL'er får 301-redirects. Kræver beslutning om navngivning.
- **Ingen tynde sider.** Filtre (lager, brand, type) får `noindex` eller canonical til hovedkollektionen.

## Structured data pr. sidetype
Alt JSON-LD genereres af temaet ud fra felter. Intet skrives manuelt i teksten.

| Sidetype | Schema | Felter / kilde |
| --- | --- | --- |
| Alle sider | Organization, WebSite + SearchAction | Navn, logo, CVR, adresse, telefon, sameAs (LinkedIn, YouTube, Facebook) |
| Alle undersider | BreadcrumbList | Menustruktur |
| Forside, showroom | LocalBusiness × 2 (Aalborg, Kolding) | Adresse, åbningstider, telefon, geo, »parentOrganization« |
| Løsningsside | Service + FAQPage | Kort svar, ydelser, områder (DK/NO), FAQ-metafelt |
| Kollektion | CollectionPage + ItemList | Produkter i rækkefølge, intro |
| Produktside | Product + Offer + Brand (+ AggregateRating/Review når der er rigtige anmeldelser) | Titel, SKU, GTIN, billeder, brand, pris ekskl. moms, lagerstatus |
| Produktvideo | VideoObject | YouTube-ID, titel, beskrivelse, thumbnail, varighed, uploadDate |
| Produkt-FAQ / SEO-blok | FAQPage | FAQ-felt |
| Guides og nyheder | BlogPosting (Article) | Forfatter, dato, opdateringsdato, billede, emne-tag |
| Supportguide | BlogPosting (evt. HowTo) | Trin fra guiden |
| Academy | Course + CourseInstance | Navn, beskrivelse, udbyder (CEPELO A/S), sted (Tradium, Randers), varighed (P2D), pris, datoer |
| Kundehistorie | BlogPosting + omtalt virksomhed | Værkstedets navn, by, løsning |

Bemærk:
- **Anmeldelser** på produkter må kun markeres, når de er indsamlet fra rigtige kunder og vises på siden. Anmeldelser af CEPELO selv på forsiden giver ikke stjerner i Google, men hjælper troværdighed og AI-svar.
- **FAQPage** giver i dag sjældent udvidede resultater i Google, men strukturen bruges af AI-tjenester og Bing. Behold det.
- **Priser** angives ekskl. moms med `priceSpecification` og `valueAddedTaxIncluded: false`. Forhandlerpriser bag login markeres ikke.

## Produktsiden – rækkefølge
1. Galleri, titel, kort intro, stjerner, nøglepunkter, pris og CTA
2. Blå bjælke: »Indgår i løsningen …«
3. Video (kun hvis produktet har en video)
4. Feature-blokke med billede og tekst (skiftevis højre og venstre)
5. Accordions: Beskrivelse, Tekniske specifikationer, Downloads
6. Anmeldelser og kundehistorie
7. Guides om produktet og »Passer til«
8. SEO/GEO-blok: »Om [produkt]« med 4 spørgsmål og svar plus uddybende tekst fra SEO Engine

## Måling
- Google Search Console og Bing Webmaster Tools for alle domæner (DK og NO)
- SEO Engine måler, hvor ofte CEPELO nævnes i AI-svar
- AI-trafik som egen kanal i analytics
