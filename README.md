# TeslaSphere

TeslaSphere affiche l'état de charge d'une Tesla avec l'API Tessie, dans un écran TRMNL optimisé pour l'e-ink.

## Installation avec TRMNL (français)

1. Téléchargez [`dist/teslasphere-import.zip`](dist/teslasphere-import.zip).
2. Dans TRMNL, ouvrez **Plugins → Private Plugin → Import new**.
3. Sélectionnez `teslasphere-import.zip`.
4. Renseignez le VIN et le token Tessie (créé depuis [my.tessie.com/settings/api](https://my.tessie.com/settings/api)).

L'archive d'import est volontairement plate et contient exactement les cinq fichiers attendus par TRMNL.

## Installation avec trmnlp (français)

Pour les utilisateurs de l'édition **Developer**, configurez votre clé API utilisateur commençant par `user_`, puis lancez :

```sh
TRMNL_API_KEY=user_... trmnlp push --force
```

Le fichier `.trmnlp.yml` contient les données de prévisualisation locales. Ne commitez jamais un token Tessie réel.

## Déploiement GitHub (français)

Ajoutez `TRMNL_API_KEY` comme secret du dépôt GitHub (**Settings → Secrets and variables → Actions**). Le workflow `.github/workflows/trmnl.yml` lance le lint puis déploie automatiquement sur chaque push vers `main`.

## English

TeslaSphere displays Tesla charging data from the Tessie API in an e-ink-friendly TRMNL plugin.

### Install through TRMNL

1. Download [`dist/teslasphere-import.zip`](dist/teslasphere-import.zip).
2. In TRMNL, open **Plugins → Private Plugin → Import new**.
3. Select `teslasphere-import.zip`.
4. Enter the vehicle VIN and a Tessie token from [my.tessie.com/settings/api](https://my.tessie.com/settings/api).

The import archive is intentionally flat and contains only the five files TRMNL expects.

### Install with trmnlp

For the **Developer edition**, use a user API key beginning with `user_`:

```sh
TRMNL_API_KEY=user_... trmnlp push --force
```

### Automatic GitHub deployment

Add `TRMNL_API_KEY` as a GitHub repository secret. The workflow in `.github/workflows/trmnl.yml` lints the plugin and auto-deploys on pushes to `main`.

Source and issue tracker: [github.com/bobdivx/trmnl-teslasphere](https://github.com/bobdivx/trmnl-teslasphere).
