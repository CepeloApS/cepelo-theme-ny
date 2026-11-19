# Feltkontrakt – theme, Shopify Admin og SEO Engine

Udkast 10. november 2026. Temaet læser **kun** fra Shopify-felter og metafelter. Hvilket system der fylder felterne (CEPELOs intranet, Shopify Admin eller SEO Engine), er temaet ligeglad med – men hvert felt har én ejer, så systemerne ikke overskriver hinanden.

Namespace for alle metafelter: `cepelo`. Typer angives som Shopifys metafelttyper og skal bekræftes i Admin, før de oprettes.

## Produkter

| Felt | Type | Ejer | Bruges til |
| --- | --- | --- | --- |
| `title`, `body_html`, billeder, `vendor`, SKU, pris, lager | Standardfelter | Intranet | Købsboks, galleri, Product-schema |
| `cepelo.kort_intro` | multi_line_text_field | Intranet | Intro under titlen |
| `cepelo.noglepunkter` | list.single_line_text_field | Intranet | Punktliste i købsboksen |
| `cepelo.feature_blokke` | list.metaobject_reference → `feature_blok` | Intranet | Feature-blokke (billede + tekst) |
| `cepelo.specifikationer` | list.metaobject_reference → `specifikation` | Intranet | Accordion »Tekniske specifikationer« |
| `cepelo.video_youtube_id` | single_line_text_field | Intranet | Video + VideoObject. Tomt felt = intet videoafsnit |
| `cepelo.downloads` | list.file_reference | Intranet | Accordion »Downloads« |
| `cepelo.passer_til` | list.product_reference | Intranet | »Passer til« |
| `cepelo.loesning` | metaobject_reference → `loesning` | Intranet | Blå bjælke »Indgår i løsningen« |
| `cepelo.faq` | list.metaobject_reference → `faq_punkt` | SEO Engine | SEO/GEO-blok + FAQPage |
| `cepelo.seo_tekst` | rich_text_field | SEO Engine | Uddybende tekst i bunden |
| `cepelo.relaterede_guides` | list.article_reference (alternativt list.url) | SEO Engine | »Guides om produktet« – links begge veje |
| `cepelo.leasing_maaned` | number_decimal | Intranet | »Leasing fra … kr./md.« |

## Metaobjekter

**`loesning`** (6 poster, med egen URL via `templates/metaobject/loesning.json`)
`navn`, `kort_svar` (SEO Engine), `intro`, `hero_billede`, `arbejdsgang` (list → `trin`: nummer, titel, tekst), `produktgruppe` (collection_reference), `udvalgte_produkter` (list.product_reference), `faq` (list → `faq_punkt`, SEO Engine), `pdf_guide` (file_reference), `kundehistorie` (article_reference), `kursus` (metaobject_reference → `kursus`)

**`faq_punkt`**: `spoergsmaal`, `svar` (rich_text)

**`feature_blok`**: `titel`, `tekst` (rich_text), `billede` (file_reference)

**`specifikation`**: `navn`, `vaerdi`

**`kursus`** (Academy): `navn`, `kort_svar`, `beskrivelse`, `varighed_dage`, `sted_navn`, `sted_adresse`, `pris_amu_dag`, `pris_fuld`, `program` (rich_text), `hold` (list → `kursushold`: `dato`, `sted`, `ledige_pladser`), `tilmeldingslink` (url)

**`faelles_fakta`** (én post – fakta der vises flere steder)
`aabningstider_support`, `aabningstider_aalborg`, `adresse_kolding`, `aabningstider_kolding`, `soh_pris`, `leasing_tekst`, `roi_tal`, `roi_kilde`, `anmeldelser_gennemsnit`, `anmeldelser_antal`, `anmeldelser_kilde`

## Kollektioner (de 10 produktgrupper)

| Felt | Type | Ejer |
| --- | --- | --- |
| `cepelo.kort_svar` | multi_line_text_field | SEO Engine |
| `cepelo.seo_tekst` | rich_text_field | SEO Engine |
| `cepelo.faq` | list.metaobject_reference → `faq_punkt` | SEO Engine |
| `cepelo.loesning` | metaobject_reference → `loesning` | Shopify Admin |
| `cepelo.gruppe_billede` | file_reference | Shopify Admin |
| `cepelo.underkategorier` | list.collection_reference | Shopify Admin |

## Artikler (én Viden-blog)

| Felt | Type | Ejer |
| --- | --- | --- |
| Tag: `type:guide`, `type:nyhed`, `type:kundehistorie`, `type:support` | Tags | SEO Engine |
| `cepelo.loesning` | metaobject_reference → `loesning` | SEO Engine |
| `cepelo.relaterede_produkter` | list.product_reference | SEO Engine |
| `cepelo.kort_svar` | multi_line_text_field | SEO Engine |

## Regler
- Felter, som SEO Engine ejer, må ikke overskrives af intranettets sync.
- Tomme felter viser intet – temaet viser aldrig opdigtet indhold.
- Ændres en type eller et navn, opdateres denne fil i samme PR.
