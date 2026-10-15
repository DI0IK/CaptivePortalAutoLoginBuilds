# Captive Portal Auto Login — Builds

Automated nightly builds of [binarynoise/CaptivePortalAutoLogin](https://github.com/binarynoise/CaptivePortalAutoLogin),
published as GitHub pre-releases of this repository.

- Runs nightly at 02:23 UTC and on manual `workflow_dispatch`
- Skips when there are no upstream changes (state = release tag `nightly-<commit sha>`)
- Each release contains `CaptivePortalAutoLogin-<versionName>-arm64.apk`
- Release notes link to the upstream commit and diff since the previous nightly

## Secrets

Set under *Settings → Secrets and variables → Actions*:

| Key | Value |
| --- | --- |
| `KEYSTORE_BASE64` | `base64 -w0 /path/to/keystore.jks` |
| `KEYSTORE_STORE_PASSWORD` | keystore store password |
| `KEYSTORE_KEY_ALIAS` | key alias |
| `KEYSTORE_KEY_PASSWORD` | key password |

Without these secrets the workflow still runs but produces debug-signed APKs
(useful for a dry run via *Actions → Nightly Release → Run workflow*).
