# Udkast: Ordliste over fagtermer og forkortelser

| Felt | Dansk | Norsk |
|---|---|---|
| URL | `/pages/ordliste` | `/no/pages/ordliste` |
| Sidetitel | Ordliste: fagtermer og forkortelser på værkstedet \| CEPELO | Ordliste: fagtermer og forkortelser på verkstedet \| CEPELO |
| Metabeskrivelse | Hvad betyder ADAS, LDW, ACC og camber? Kort forklaring af de fagtermer og forkortelser, vi bruger om ADAS-kalibrering og hjuljustering. | Hva betyr ADAS, LDW, ACC og camber? Kort forklaring av fagtermene og forkortelsene vi bruker om ADAS-kalibrering og hjulstilling. |
| H1 | ORDLISTE | ORDLISTE |

**Byggeregler**
- Hver term får et anker (`id`) i små bogstaver uden mellemrum, fx `#ldw`, `#toe-out-on-turns`, så andre sider kan linke direkte.
- Grupperet alfabetisk med springlinks A–Z øverst. Termerne vedligeholdes som metaobjekter
  (type `ordliste_term`: term, forkortelse står for, forklaring DA, forklaring NO), så nye termer kan
  tilføjes i Shopify-admin uden kodeændring. *Forslag, afhænger af startpakkens regler.*
- `DefinedTermSet`-schema til SEO.

**Intro (DA):** Her forklarer vi de fagtermer og forkortelser, du møder på vores sider om ADAS-kalibrering, hjuljustering og diagnose.
**Intro (NO):** Her forklarer vi fagtermene og forkortelsene du møter på sidene våre om ADAS-kalibrering, hjulstilling og diagnose.

---

## ADAS og sensorer

| Anker | Term | Står for | Dansk forklaring | Norsk forklaring |
|---|---|---|---|---|
| `adas` | ADAS | Advanced Driver Assistance Systems | Førerassistentsystemer, der bruger kameraer, radar og andre sensorer til fx at holde afstand, advare om fare og hjælpe med at parkere. Sensorerne skal kalibreres efter fx rudeskift, hjuljustering eller skader. | Førerassistansesystemer som bruker kameraer, radar og andre sensorer til f.eks. å holde avstand, varsle om fare og hjelpe med parkering. Sensorene må kalibreres etter f.eks. rutebytte, hjulstilling eller skader. |
| `acc` | ACC | Adaptive Cruise Control | Adaptiv fartpilot, der holder en fast afstand til bilen foran ved hjælp af radar. | Adaptiv cruisekontroll som holder fast avstand til bilen foran ved hjelp av radar. |
| `avm` | AVM | Around View Monitor | 360°-kamera, der samler billeder fra flere kameraer til ét overblik rundt om bilen. | 360°-kamera som setter sammen bilder fra flere kameraer til ett overblikk rundt bilen. |
| `bsd` | BSD | Blind Spot Detection | Blindvinkelassistent, der advarer om køretøjer i den døde vinkel. | Blindsoneassistent som varsler om kjøretøy i blindsonen. |
| `ldw` | LDW | Lane Departure Warning | Vognbaneadvarsel, der advarer, hvis bilen utilsigtet forlader vognbanen. Bruger typisk frontkameraet. | Filskiftevarsling som varsler hvis bilen utilsiktet forlater kjørefeltet. Bruker vanligvis frontkameraet. |
| `nvs` | NVS | Night Vision System | Nattesynssystem, der bruger et infrarødt kamera til at vise fodgængere og dyr i mørke. | Nattsynssystem som bruker infrarødt kamera til å vise fotgjengere og dyr i mørket. |
| `rcw` | RCW | Rear Collision Warning **(bekræft)** | Advarsel om risiko for kollision bagfra. | Varsling om fare for kollisjon bakfra. |
| `radar` | Radar | Radio Detection and Ranging | Sensor, der måler afstand og hastighed med radiobølger. Bruges bl.a. til ACC og nødbremse. | Sensor som måler avstand og hastighet med radiobølger. Brukes bl.a. til ACC og nødbrems. |
| `lidar` | Lidar | Light Detection and Ranging | Sensor, der måler afstand med laserlys. | Sensor som måler avstand med laserlys. |
| `nightvision` | Nightvision | – | Se NVS. | Se NVS. |

## Hjuljustering

| Anker | Term | Dansk betegnelse | Dansk forklaring | Norsk forklaring |
|---|---|---|---|---|
| `toe` | Toe | Sporing | Hjulenes vinkel indad eller udad set ovenfra. Forkert sporing giver skævt dækslid og en bil, der trækker. | Hjulenes vinkel innover eller utover sett ovenfra. Feil spissing gir skjev dekkslitasje og en bil som trekker. |
| `camber` | Camber | Styrtvinkel | Hjulets hældning indad eller udad set forfra. | Hjulets helning innover eller utover sett forfra. |
| `caster` | Caster | Efterløbsvinkel | Styreaksens hældning frem eller tilbage set fra siden. Påvirker retningsstabilitet og rattets tilbageføring. | Styreaksens helning forover eller bakover sett fra siden. Påvirker retningsstabilitet og rattets tilbakeføring. |
| `thrust-angle` | Thrust angle | Køreretningsvinkel | Vinklen mellem bilens midterlinje og den retning, baghjulene skubber bilen i. Er udgangspunkt for ADAS-kalibrering. | Vinkelen mellom bilens senterlinje og retningen bakhjulene skyver bilen i. Er utgangspunkt for ADAS-kalibrering. |
| `sai` | SAI | Spindelhældning (Steering Axis Inclination) | Styreaksens hældning indad set forfra. | Styreaksens helning innover sett forfra. |
| `toe-out-on-turns` | Toe-out on turns | Sporingsdifferens i sving | Forskellen i styrevinkel mellem inder- og yderhjul, når der drejes. | Forskjellen i styrevinkel mellom indre og ytre hjul når man svinger. |
| `rideheight` | Rideheight | Kørehøjde | Karrosseriets højde over gulvet. Bruges som reference ved hjuljustering og ADAS-kalibrering. | Karosseriets høyde over gulvet. Brukes som referanse ved hjulstilling og ADAS-kalibrering. |
| `inclinometer` | Inclinometer | Vinkelmåler | Måler vinkler, fx på bærearme. Krævet ved hjuljustering på bl.a. Mercedes. | Måler vinkler, f.eks. på bærearmer. Påkrevd ved hjulstilling på bl.a. Mercedes. |
| `gulvkompensation` | Gulvkompensation | – | Udstyret måler og korrigerer for, at gulvet eller liften ikke er helt plan. | Utstyret måler og korrigerer for at gulvet eller løfteren ikke er helt plan. |

## Kalibrering og diagnose

| Anker | Term | Dansk forklaring | Norsk forklaring |
|---|---|---|---|
| `kalibrering` | Kalibrering | Justering af en sensor, så den ser og måler korrekt i forhold til bilen. | Justering av en sensor slik at den ser og måler riktig i forhold til bilen. |
| `targets` | Targets / tavler | Mål med et mønster, som bilens kamera eller radar kalibreres mod. Kan være fysiske tavler eller digitale. | Mål med et mønster som bilens kamera eller radar kalibreres mot. Kan være fysiske tavler eller digitale. |
| `digitale-targets` | Digitale targets | Kalibreringsmål vist på en skærm, så der skal opbevares færre fysiske tavler. | Kalibreringsmål vist på en skjerm, slik at færre fysiske tavler må oppbevares. |
| `go-no-go` | Go/No-Go | Automatisk kontrol, der kun starter kalibreringen, når målene er placeret inden for tolerancen. | Automatisk kontroll som bare starter kalibreringen når målene står innenfor toleransen. |
| `oem` | OEM | Original Equipment Manufacturer: bilproducenten. OEM-specifikationer er producentens egne krav. | Original Equipment Manufacturer: bilprodusenten. OEM-spesifikasjoner er produsentens egne krav. |
| `kodning` | Kodning | Indstilling af en styreenhed, så den passer til bilens udstyr, fx efter udskiftning. | Innstilling av en styreenhet slik at den passer til bilens utstyr, f.eks. etter bytte. |
| `tilpasning` | Tilpasning | Indlæring af værdier i en styreenhed efter reparation eller udskiftning. | Innlæring av verdier i en styreenhet etter reparasjon eller bytte. |
| `topology` | Topology | Autels grafiske oversigt over bilens styreenheder og deres status. | Autels grafiske oversikt over bilens styreenheter og deres status. |
| `remote-expert` | Remote Expert | Autels funktion til fjernhjælp fra en specialist direkte i tabletten. | Autels funksjon for fjernhjelp fra en spesialist direkte i nettbrettet. |
| `vci` | VCI | Vehicle Communication Interface: enheden, der forbinder tabletten med bilens diagnosestik. | Vehicle Communication Interface: enheten som kobler nettbrettet til bilens diagnosekontakt. |

> RCW er markeret **(bekræft)**: forkortelsen bruges forskelligt hos producenterne. Tjek Autels danske
> materiale for IA900, før den publiceres.
