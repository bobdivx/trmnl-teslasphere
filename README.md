# TeslaSphere

TeslaSphere displays Tesla charging data from your TeslaSphere account in an e-ink-friendly TRMNL plugin. The plugin uses TeslaSphere OAuth Connect, so the vehicle is linked once in TeslaSphere and no vehicle token is entered in TRMNL.

## Install with TRMNL

1. Zip the files inside [`import/`](import/) so that `settings.yml` is at the archive root, or use the provided `dist/teslasphere-import.zip` when available.
2. In TRMNL, open **Plugins → Private Plugin → Import new** and select the ZIP.
3. Choose **Connect with TeslaSphere**, authorize the requested `vehicle:read` scope, and optionally enter a VIN override. Leaving VIN empty uses your first TeslaSphere vehicle.

### TeslaSphere server setup

Configure these environment variables on the TeslaSphere server before using OAuth Connect:

- `TRMNL_OAUTH_CLIENT_ID`
- `TRMNL_OAUTH_CLIENT_SECRET`
- `TRMNL_OAUTH_REDIRECT_URIS`

For production OAuth URLs, merge the required OAuth support to `main` in [bobdivx/tesla](https://github.com/bobdivx/tesla) first. This plugin repository does not modify that repository.

## Install with trmnlp

For the **Developer edition**, configure a user API key beginning with `user_`, then run:

```sh
TRMNL_API_KEY=user_... trmnlp push --force
```

The `.trmnlp.yml` file contains static flattened preview data; OAuth is not needed for local preview.

## Automatic GitHub deployment

Add `TRMNL_API_KEY` as a GitHub repository secret. The workflow in `.github/workflows/trmnl.yml` lints the plugin and deploys it on pushes to `main`.

Source and issue tracker: [github.com/bobdivx/trmnl-teslasphere](https://github.com/bobdivx/trmnl-teslasphere).
