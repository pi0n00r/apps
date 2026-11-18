# Nextcloud 34 Community catalog

This branch is a deliberately narrow TrueNAS Community catalog for Nextcloud
34.0.6. It keeps the upstream Community deployment model, including separately
managed HaRP, notify-push, Talk, recording, Imaginary, PostgreSQL, Valkey and
Nginx services.

## Fleet contract

- Nextcloud and every companion image are pinned by immutable digest.
- The custom Nextcloud image is built publicly from `pi0n00r/containers` with
  provenance and an SBOM.
- Persistent data and secret inputs remain outside container images.
- No floating `latest` tag is used.
- HaRP remains a distinct health-checked service inside the application; it is
  not hidden in the Nextcloud image.
- Only `linux/amd64` is published because the intended TrueNAS and Debian hosts
  are amd64.

Catalog URL: `https://github.com/pi0n00r/apps.git`

Catalog branch: `fleet-nextcloud-34.0.6`

The catalog is suitable for a fresh install or a separately controlled
migration. It does not authorize replacing an existing Nextcloud application
without a verified database, data, configuration and app-state backup.

