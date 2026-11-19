# GitHub-opsætning – CEPELO

Status 17. november 2026. Beskriver hvor repoerne ligger, hvem der har adgang, og hvad der mangler, før Claude Code kan arbejde i dem.

## Repoer

| Repo | Indhold | Ejer | Status |
| --- | --- | --- | --- |
| `cepelo/cepelo-seo` | SEO Engine | Organisationen `cepelo` | Sendt til Nuno som zip-fil. Nuno opretter repoet som privat i `cepelo`. Git-historikken følger ikke med. |
| `CepeloApS/cepelo-seo` | SEO Engine (gammel placering) | Jonas (CepeloApS) | Gjort privat. Arkiveres, når `cepelo/cepelo-seo` virker. |
| `hplorentzen/cepelo-theme` | Kopi af det live Shopify-theme pr. 12.11.2026 | Peter (hplorentzen) | Jonas er collaborator. Bruges i dag til kladdetemaet. |
| `CepeloApS/cepelo-theme-ny` | Nyt cepelo.dk-theme bygget fra bunden | Jonas (CepeloApS) | Oprettet 19.11.2026. Claude-appen har adgang. Kan senere overføres til `hplorentzen`. |

## Brugere og roller

| Person | GitHub-bruger | Rolle |
| --- | --- | --- |
| Jonas Lind-Bendixen | `CepeloApS` | Marketing, ejer af webshop-projektet. Arbejder med Claude Code. |
| Peter Lorentzen | `hplorentzen` | Ejer af `cepelo-theme`. Godkender og fletter PR'er. |
| Nuno Franco | – | Står for teknikken og organisationen `cepelo`. |

## Sådan får Claude Code adgang til et repo

To ting skal være på plads for hvert repo:

1. **Brugeradgang:** `CepeloApS` har skriveadgang til repoet (collaborator eller medlem af organisationen).
2. **Claude GitHub-appen:** Appen er installeret på den konto eller organisation, der ejer repoet, med adgang til netop det repo. Det kan kun ejeren gøre:
   - Organisationen `cepelo`: en owner (Nuno) installerer appen og vælger repoerne.
   - Personlig konto `hplorentzen`: Peter installerer appen under github.com/settings/installations.

Collaborator-adgang alene er ikke nok til Claude Code i skyen.

## Overførsel af repoer til `cepelo`

En overførsel til en organisation kræver, at den der overfører, har ret til at oprette repoer i organisationen. `CepeloApS` har ikke den ret i `cepelo`, så overførslen blev afvist. Derfor er SEO Engine sendt som zip-fil.

Alternativer ved næste overførsel:
- Nuno giver `CepeloApS` ret til at oprette repoer (Settings › Member privileges), eventuelt midlertidigt.
- Repoet overføres til Nunos personlige bruger, som overfører det videre til `cepelo`.

## Regler for arbejdet (fra README i `cepelo-theme`)

- Ingen direkte push til `main` eller `kladde`.
- Egen branch ud fra `kladde`, fx `jonas/<emne>`.
- Pull request til `kladde`. Peter godkender og fletter.
- Publicér aldrig et theme, og push ikke med `shopify theme push`. `kladde` synkroniseres automatisk med et upubliceret theme i Shopify.
- Ingen nøgler, tokens eller adgangskoder i repoet.

## Åbne punkter

- [ ] Nuno opretter `cepelo/cepelo-seo` og uploader filerne fra zip-filen.
- [ ] Nuno giver `CepeloApS` skriveadgang til `cepelo/cepelo-seo`.
- [ ] Nuno installerer Claude GitHub-appen på `cepelo` med adgang til `cepelo-seo`.
- [ ] Opdatér alt, der peger på `CepeloApS/cepelo-seo` (fx SEO Engine-deploy), til den nye adresse. Arkivér derefter det gamle repo.
- [x] Det nye theme bygges i `CepeloApS/cepelo-theme-ny` (besluttet 19.11.2026).
- [x] Claude-appen har adgang til `cepelo-theme-ny` (installeret på CepeloApS).
- [x] Startpakken lægges ind i `cepelo-theme-ny` som første PR.
- [ ] Invitér `hplorentzen` som collaborator på `cepelo-theme-ny`, så Peter kan godkende og flette.
- [ ] Forbind `kladde` til et nyt, upubliceret theme i Shopify (Themes › Add theme › Connect from GitHub, logget ind som CepeloApS). Vent, til grundstrukturen er flettet.

## Senere overførsel til `hplorentzen`

Repoet kan overføres under Settings › Transfer ownership. Branches, PR'er og historik følger med. Bagefter:
- Peter giver Claude-appen adgang på sin konto (github.com/settings/installations).
- Shopify-forbindelsen holder op med at virke og skal kobles til igen fra Peters GitHub-konto.
- Opdatér repo-navnet i `docs/ny-cepelo/CLAUDE.md`.
