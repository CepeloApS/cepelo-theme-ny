# Udkast v3: Løsningsside »ADAS og hjuludmåling«

Følger det nye designs løsningsskabelon (`docs/ny-cepelo/design/Losning.dc.html`) og designreglerne
fra 27. oktober i `docs/ny-cepelo/CLAUDE.md`. Siden er én post i metaobjektet `loesning`
og vises med `templates/metaobject/loesning.json` (byggerækkefølgens punkt 7).
Indholdet lægges i felterne fra `docs/ny-cepelo/metafelter.md`, ikke i Liquid.

Kilde: »Produktsammenligning ADAS-kalibrering V2« og resuméet. Kun oplysninger om egne produkter.

## Ændret i forhold til v2 (for at følge det nye design)

- Ingen label over H1 (»ADAS-KALIBRERING · HJULJUSTERING« er fjernet).
- Ingen navy-boks med hvid tekst. Al tekst er sort; kun knaptekst er hvid.
- Ingen runde »CEPELO«-badges på produktkortene. Kortene bruger skabelonens grå `tag` (fx »Ramme«, »Tilbehør«).
- Ingen dekorative cirkler eller streger. Afsnit skifter mellem hvid og `#F0F0F0`.
- Nøgletal-kortene og sektionen »Sådan hjælper løsningen« er erstattet af skabelonens **Arbejdsgang** (3 trin).
- IA900 vs. IA1000 og tilbehørspakkerne vises som **Udstyr**-kort, der linker til produktsiderne. Specifikationerne hører til produktsiderne (`cepelo.specifikationer`), ikke løsningssiden.
- Priser vises ikke på løsningssiden. På produktsiderne vises de ekskl. moms efter sitets prisregler.

---

## Felter i `loesning`-posten

| Felt | Indhold |
|---|---|
| `navn` | ADAS og hjuludmåling |
| URL / handle | `/pages/adas-og-hjuludmaaling` (metaobject-URL; endelig sti afhænger af beslutningen om URL-struktur) |
| `kort_svar` *(SEO Engine)* | Se nedenfor |
| `intro` | Se nedenfor |
| `hero_billede` | [BILLEDE: IA1000 eller IA900 i et værksted, lyst og sløret miljø] |
| `arbejdsgang` | 3 trin, se nedenfor |
| `produktgruppe` | Kollektionen »ADAS og hjuludmåling« |
| `udvalgte_produkter` | IA900, IA1000 Full Kit Digital Targets, IA900 Basis-pakke, IA900 Plus-pakke [PRODUKT-HANDLES] |
| `faq` *(SEO Engine)* | Forslag nedenfor |
| `pdf_guide` | [PDF-GUIDE »ADAS og hjuludmåling« – skal produceres] |
| `kundehistorie` | [KUNDEHISTORIE – mangler] |
| `kursus` | [KURSUS – findes der et ADAS-kursus i Academy?] |

SEO (SEO Engine ejer feltet, dette er forslaget):
- Meta-titel: ADAS og hjuludmåling i én ramme | CEPELO
- Metabeskrivelse: Kalibrér ADAS og justér hjul i samme ramme med Autel IA900 og IA1000. Gulvkompensation, rapporter før og efter og lokal support fra CEPELO.

---

## Siden, sektion for sektion (rækkefølge som i skabelonen)

### 1 · Intro (hvid)
Brødkrumme: Forside › Løsninger og viden › ADAS og hjuludmåling

**H1:** ADAS og hjuludmåling

**Kort svar:** Efter hjuljustering, rudeskift eller skader skal bilens [ADAS](/pages/ordliste#adas) (førerassistentsystemer) kalibreres mod producentens krav. Med Autel IA900 og IA1000 måler, justerer og kalibrerer I i samme ramme, uden at flytte udstyr, og hver kalibrering dokumenteres med rapporter før og efter. CEPELO leverer udstyret, introduktionen og supporten.

Knapper: [Book demo] [Se udstyret]

### 2 · Ankernavigation
Arbejdsgang · Udstyr · Kundehistorie · Guides og manualer · Kursus · Spørgsmål og svar
(Punkter uden indhold skjules automatisk: tomme felter viser intet.)

### 3 · Arbejdsgang (`#F0F0F0`)
**H2:** Sådan kalibrerer I ADAS i én ramme

1. **Mål og justér hjulene**
   Bilen måles med 6 HD-kameraer og 4 hjulklemmer. I justerer [camber](/pages/ordliste#camber) (styrtvinkel), [caster](/pages/ordliste#caster) (efterløbsvinkel) og [toe](/pages/ordliste#toe) (sporing) med aflæsning ned til 0,02°. Rammen kompenserer for ujævnt gulv.
2. **Placér målene og kalibrér**
   Kalibrér kamera og radar ud fra bilens [thrust angle](/pages/ordliste#thrust-angle) (køreretningsvinkel). På IA1000 placeres målene robotstyret, og [Go/No-Go](/pages/ordliste#go-no-go) (automatisk godkendt/afvist-kontrol) stopper kalibreringen, hvis placeringen er uden for tolerance.
3. **Dokumentér og afslut**
   Gem rapporter før og efter til kunden eller forsikringsselskabet, og fortsæt med kodning og tilpasninger i samme Autel-tablet.

PDF-linje: **Få PDF-guiden »ADAS og hjuludmåling«** – vi sender den til din mail. [Send guiden]
*(Formularen afventer intranettet, jf. CLAUDE.md. Vises først, når `pdf_guide` er udfyldt.)*

> 0,02° er aflæsningens opløsning, ikke en dokumenteret målenøjagtighed. Skriv »aflæsning ned til 0,02°«, aldrig »nøjagtighed«.

### 4 · Udstyr (hvid)
**H2:** Udstyret til løsningen · link: Se alt i shoppen →

| Tag (`role`) | Produkt | Hvorfor (`why`, kort tekst på kortet) |
|---|---|---|
| Ramme | Autel IA900 | Hjuljustering og ADAS-kalibrering i én ramme med fysiske tavler. |
| Automatiseret ramme | Autel IA1000 Full Kit Digital Targets | Robotstyret placering, Go/No-Go og digitale mål på 3 × 27"-skærme. |
| Tilbehør | IA900 Basis-pakke | Inclinometer, rideheight targets og ratvaterpas, der sparer tid ved sporing. |
| Tilbehør | IA900 Plus-pakke | Bakkamera-tavler til VAG-koncernen og radarkalibrering på asiatiske biler. |

*Afklaring: Skabelonen har ikke et felt til `role`/`why` pr. produkt. Forslag: `role` = produkttype, `why` = første linje af `cepelo.kort_intro`. Ellers skal der et nyt felt til.*

### 5 · Kundehistorie (`#F0F0F0`)
[KUNDEHISTORIE: værksted, kort resumé, citat, navn og titel] – sektionen skjules, til feltet er udfyldt.

### 6 · Guides og manualer (hvid)
Guides: [ARTIKLER med `cepelo.loesning` = ADAS og hjuludmåling – fra SEO Engine]
Vejledninger og manualer: [IA900/IA1000 brugervejledning, datablad – PDF'er fra produkternes `cepelo.downloads`]

### 7 · Kursus (`#F0F0F0`)
[Kun hvis der er et ADAS-kursus. Ellers skjules sektionen.]

### 8 · Spørgsmål og svar (hvid, `<details>` + FAQPage)
**H2:** Spørgsmål om ADAS og hjuludmåling

**Kan vi både spore og kalibrere ADAS i samme ramme?**
Ja. IA900 og IA1000 måler og justerer hjulene og kalibrerer ADAS i samme ramme, uden at I skal flytte udstyr.

**Hvad er forskellen på IA900 og IA1000?**
IA900 bruger fysiske tavler og placeres optisk via kameraer og klemmer. IA1000 placerer målene robotstyret, starter kalibreringen med én knap, har Go/No-Go og kan bruge digitale mål på 3 × 27"-skærme.

**Kan rammen bruges på ujævnt gulv eller en lift?**
Ja. Begge modeller kompenserer for ujævnt gulv, og IA1000 kan bruges på plant gulv, ujævnt gulv eller lift.

**Hvilke ADAS-systemer kan kalibreres?**
Blandt andet [LDW](/pages/ordliste#ldw) (vognbaneadvarsel), [ACC](/pages/ordliste#acc) (adaptiv fartpilot), [BSD](/pages/ordliste#bsd) (blindvinkelassistent) og [AVM](/pages/ordliste#avm) (360°-kamera). [Radar](/pages/ordliste#radar), [lidar](/pages/ordliste#lidar) (laserbaseret afstandsmåling) og nattesyn dækkes med tilbehørspakker. [BEKRÆFT FOR DE DANSKE PAKKER]

**Hvilken tablet skal vi bruge?**
IA900 styres fra MaxiSys MS909 S2 eller Ultra. IA1000 styres fra MaxiSys Ultra S2 med Topology 3.0, kodning og Remote Expert. [BEKRÆFT: indgår tablet og aktiveringskort i pakkerne?]

**Kan vi dokumentere kalibreringen over for kunden?**
Ja. Begge modeller laver rapporter før og efter scanning. IA1000 dokumenterer også den validerede målposition.

**Kan udstyret leases?**
[SVAR FRA FÆLLES LEASINGFELT]

### 9 · Demo (`#F0F0F0`)
**H2:** Se udstyret i praksis
Book en demo i Aalborg eller Kolding, eller få en specialist ud til jer.
[Book demo] [98 18 09 00]

---

## Stadig åbent

1. ~~Hvor det nye theme bygges~~ – besluttet: `CepeloApS/cepelo-theme-ny`.
2. Løsningsskabelonen er punkt 7 i byggerækkefølgen og forudsætter punkt 1–3 (grundstruktur, header/footer, structured data).
3. Ordlisten (`/pages/ordliste`) findes ikke i design-canvasset. Den skal designes i samme udtryk, se `ordliste.md`.
4. Norsk: CLAUDE.md siger, at `nb.json` afventer ledelsens beslutning. Den norske tekst er klar, men publiceres først efter den beslutning.
5. Bekræft for de danske pakker: kameraer/klemmer, ADAS-funktioner og om tablet og aktiveringskort indgår.
6. Felter til produktkortenes `role`/`why` (se sektion 4).
7. Produkt-handles, heltebillede, PDF-guide, kundehistorie, ADAS-kursus, leasingtekst.
8. Godkendelse af indhold fra »INTERN BRUG«-dokumenterne (efter go-live, efter jeres beslutning).
