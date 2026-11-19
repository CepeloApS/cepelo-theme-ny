# cepelo-theme-ny

Nyt Shopify-theme til cepelo.dk (`cepelotools.myshopify.com`), bygget fra bunden.
Det nuværende live-theme ligger i `hplorentzen/cepelo-theme` og røres ikke herfra.

Start med `docs/ny-cepelo/overdragelse-til-claude-code.md`, `docs/ny-cepelo/CLAUDE.md`
og `docs/ny-cepelo/README.md` (byggerækkefølge og åbne beslutninger).

Theme-filerne ligger i roden (`assets/`, `config/`, `layout/`, `locales/`, `sections/`,
`snippets/`, `templates/`), som Shopifys GitHub-integration kræver.

## Grene

| Gren | Rolle |
|---|---|
| `main` | Den godkendte version af det nye theme. Push ikke direkte hertil. |
| `kladde` | Forbindes til et upubliceret theme i Shopify. Push ikke direkte hertil. |

## Sådan arbejder du

1. Lav din egen gren ud fra `kladde`:
   ```bash
   git checkout kladde && git pull
   git checkout -b <dit-navn>/<emne>
   ```
2. Forhåndsvis dine ændringer lokalt (rører ikke noget theme i butikken):
   ```bash
   shopify theme dev --store cepelotools
   ```
3. Kør Theme Check:
   ```bash
   shopify theme check
   ```
4. Opret en pull request til `kladde`. Peter godkender og fletter.

## Regler

- **Push aldrig direkte til `main` eller `kladde`.** Alt går gennem en pull request.
- **Publicér ingen themes** – hverken i Shopify Admin eller med `shopify theme push --publish`.
- **Push ikke med `shopify theme push`.** Integrationen synkroniserer `kladde` automatisk.
- **Ingen nøgler i repoet.** Tokens og adgangskoder hører hjemme i `.env.local` lokalt, som `.gitignore` holder ude.
- Theme-editoren i Shopify skriver ændringer tilbage til `kladde`. Kør `git pull` før du retter `config/settings_data.json` eller `templates/*.json`.
