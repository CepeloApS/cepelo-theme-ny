# cepelo.dk – designforslag: struktur og sider

Opdateret 27. oktober 2026. Design-canvas: »Ny cepelo.dk – forslag«. Mockups ligger i `docs/ny-cepelo/design/`.

## Mål med den nye struktur
- Færre klik til guides, support og viden.
- To tydelige indgange: **Løsninger og viden** og **Shop**.
- Missionen »Vi sikrer fremtidens værksted« står tydeligt (H1 på forsiden).
- Fokus på SEO/GEO/AIO på tværs af sitet – se `03-seo-geo-structured-data.md`.

## Designregler (fra 27. oktober)
- Ingen cirkler eller halvcirkler – hverken som dekoration, badges, ikoner eller knapper. Knapper og kort har små hjørner (4–8 px).
- Al tekst er sort. Kun tekst på blå knapper og »Nyhed«/»Kampagne«-mærker er hvid.
- Ingen små overskrifter over de store (fx »01 · ARBEJDSGANG«).
- Ingen dekorative streger. Afsnit adskilles med lys grå baggrund (#F0F0F0) i stedet for linjer.
- Samme header og footer på alle sider (fælles komponenter).
- Den blå bjælke på produktsiden er lys blå (#35B6EA) med sort tekst.

## Sider
1. Forside – `Main.dc.html`
2. Løsninger og viden (hub) – `Viden.dc.html`
3. Løsningsside (eksempel: Elbil service og reparation) – `Losning.dc.html`
4. Support – `Support.dc.html`
5. Academy – `Academy.dc.html`
6. Shop: alle produktkategorier – `Kategorier.dc.html`
7. Shop-kategori (eksempel: Diagnose og programmering) – `Kategori.dc.html`
8. Produktside (eksempel: Autel EVDiag Box 2) – `Produkt.dc.html`
9. Mobil: forside og Viden-hub – `MobilForside.dc.html`, `MobilViden.dc.html`
10. Fælles header med mega-menu og fælles footer – `Header.dc.html`, `Footer.dc.html`

## Seks løsninger (besluttet)
Elbil service og reparation · SOH-batteritest · ADAS og hjuludmåling · Autodiagnose · A/C-service · Opladning

## Header og mega-menu
Topbar: rådgivning 98 18 09 00 · teknisk support 98 18 02 03 · showrooms · forhandler-login · DK/NO.
Hovedlinje: [Løsninger og viden ▾ | Shop ▾] · Brands ▾ · Support · Academy · Showroom · søg · log ind · kurv · Book demo.

- **Løsninger og viden ▾:** de seks løsninger med billede, kort svar og genveje + Viden og service.
- **Shop ▾:** 10 produktgrupper; grupper der matcher en løsning har »Løsning«-mærke og link til løsningen. Underkategorier, fremhævet produkt, brand-logoer.
- **Brands ▾:** egne brands (CEPELO, Zmartgear) og partnerbrands med logo, kort beskrivelse og antal produkter.

Produktgrupper: Diagnose og programmering · ADAS og hjuludmåling · Elbil: service og reparation · Opladning · A/C-service · Batteri og start · Dæk og TPMS · Lifte og løfteudstyr · Værkstedsudstyr og værktøj · Pro-shop.

## Footer
Nyhedsbrev · CEPELO A/S (adresse, CVR, salg, support, mail) · Løsninger · Shop (10 grupper) · Viden og service · Showrooms (Aalborg, Kolding) · Om CEPELO, karriere, handelsbetingelser, privatliv, sociale medier.

## Forsiden – rækkefølge
1. Løsninger med H1 »Vi sikrer fremtidens værksted« på lyst, sløret værkstedsbillede
2. Trust-linje
3. Anmeldelser (stjerner, gennemsnit, 3 citater fra Google/Trustpilot)
4. Kundehistorier (én stor + to mindre)
5. Kampagne
6. Nyt i sortimentet
7. SOH med foto
8. Brands
9. Afkastberegner
10. Guides og nyheder
11. Showroom med foto
12. FAQ

## Kundecases og anmeldelser
- Forsiden: anmeldelser og kundehistorier ligger lige efter løsningerne.
- Løsningssiden: kundehistorie med citat.
- Produktsiden: produktanmeldelser og en kundehistorie.
- Viden-hubben: egen række med kundehistorier.
- Academy: deltagercitat.

## Academy
Kort svar, kurset i tal (2 dage, Tradium Randers, 218 kr./dag som AMU, fuld pris 3.800 kr., VEU 1.017 kr./dag), program dag 1 og 2, kommende hold, tilmelding, tilskud (VEU, befordring 1,14 kr./km over 24 km, overnatning op til 550 kr. over 60 km), kurser på vej med e-mail-tilmelding, deltagercitat og FAQ. Kilde: cepelo.dk/pages/kurser.

## Produktside
Galleri og købsboks → blå bjælke »Indgår i løsningen« → video (kun hvis produktet har en video) → feature-blokke → accordions (Beskrivelse, Tekniske specifikationer, Downloads) → anmeldelser og kundehistorie → guides og »Passer til« → SEO/GEO-blok »Om [produkt]« med spørgsmål og svar.

## Support
Teknisk support, Remote Expert og reklamation øverst; guides efter emne med e-mail til PDF-guide pr. emne; serviceaftaler; softwarepriser; kontakt.

## PDF-guides
- Supportsiden: én PDF pr. emne.
- Løsningssider: én linje med e-mailfelt efter arbejdsgangen.
- Formular med skjult felt for emne/løsning; den rigtige PDF sendes automatisk. (Oprindeligt planlagt i HubSpot – afventer intranettet.)

## Åbne punkter
- Anmeldelser: vælg kilde (Google eller Trustpilot) og indsaml
- Videoer: YouTube-ID skal tilføjes pr. produkt
- Program for Academy dag 1 og 2, kursusdatoer og kommende kurser
- PDF-guiderne skal produceres
- Logoer til Beissbarth og Fastlign; beskrivelser til Govoni og HubiTools
- Shopify: URL-struktur og redirects for de 10 grupper
- Pladsholdere: kampagnepris, leasingpriser, kilde til 312 % ROI, adresse og åbningstider i Kolding, resuméer og citater til kundehistorier
- Mega-menu på mobil
