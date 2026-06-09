# MontuDB 2.30 — Release Notes

- **Product:** MontuDB 2.30
- **Based on:** PostgreSQL 17.2
- **Version string:** `PostgreSQL 17.2 (MontuDB 2.30)`
- **Install prefix:** `/opt/montudb/2.30` (coexists with the system PostgreSQL)
- **Suggested port:** `55432`

## Highlights

- Drop-in PostgreSQL 17.2 fork; the server identifies itself as
  `PostgreSQL 17.2 (MontuDB 2.30)`.
- Installs side-by-side with an existing PostgreSQL and never replaces the
  system `psql` or the `postgresql` service.
- Installation places files only — it does not initialize a cluster and does
  not start the server automatically.

## Available formats

- `.deb` packages for Debian / Ubuntu / Raspberry Pi OS 64-bit (amd64, arm64)
- `.rpm` packages for RHEL / Rocky / Alma / Oracle Linux (x86_64, aarch64)
- Portable binary tarballs for amd64 and arm64
- Docker image archives for amd64 and arm64

Raspberry Pi 64-bit uses the `arm64` artifacts.
