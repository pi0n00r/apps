# Nextcloud 34.0.6 Community deployment handoff

## Status

Source, image and catalog packaging are complete. No TrueNAS, Deepkeyp,
RAIDio, Seedpod or other production deployment was performed.

## Install source

Add `https://github.com/pi0n00r/apps.git` as a custom TrueNAS catalog using
branch `fleet-nextcloud-34.0.6`, then select Nextcloud from the Community train.
The catalog contains the current `1.2.0` package and retained `1.1.3` rollback
package.

## Required preflight

1. Record the current application version, image digests, settings and storage
   mappings.
2. Verify database, Nextcloud data, configuration and app-state backups.
3. Preserve existing host paths or datasets; do not overlap a second instance.
4. Confirm the published image resolves to index digest
   `sha256:8c76f0f120abcdc1215eb5018fc14b26ac7efab16b72221e1217494b32feac92`.
5. Keep HaRP enabled in this application only after retiring any separate HaRP
   deployment that would conflict with its ports, keys or certificates.

## Acceptance

After installation, require healthy Nextcloud, Nginx, PostgreSQL, Valkey and
enabled companion services. Verify login, file read/write/delete, background
jobs, notify-push, and HaRP app deployment/readiness before promotion. Talk,
recording and Imaginary are accepted only when enabled and exercised.

## Rebuild

The image is built by the `pi0n00r/containers` workflow from revision
`1a432ca295543242ecc17c37192c58dc7bd52118`. The build passed Hadolint and
ShellCheck and published an SBOM and maximum provenance. The catalog's basic
and HTTPS profiles both passed the native TrueNAS renderer and Docker Compose
validation.

