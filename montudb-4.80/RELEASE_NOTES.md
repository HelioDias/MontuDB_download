# MontuDB 4.80 — Release Notes

- **Product:** MontuDB 4.80
- **Based on:** PostgreSQL 17.2
- **Version string:** `PostgreSQL 17.2 (MontuDB 4.8)`
- **Install prefix:** `/opt/montudb/4.80` (coexists with the system PostgreSQL)
- **Suggested port:** `55432`
- **Build:** production — optimized `-O2`, assertions off, stripped

## Highlights

- The "V4 Compose" Montu Optimizer release on the PostgreSQL 17.2 base; the
  server identifies itself as `PostgreSQL 17.2 (MontuDB 4.8)`.
- All Montu optimizer behavior is **default-OFF** (no GUC, no hint): with no
  Montu options set, the server is bit-for-bit stock PostgreSQL 17.2 behavior.
  `server_version_num` stays `170002` and the on-disk / wire format is
  unchanged — a stock PostgreSQL 17.2 and MontuDB 4.80 are interchangeable on
  the same data directory.
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

## Validation

Every artifact was built and functionally validated on its own native
architecture (no emulation): `postgres`/`psql --version`, `initdb`, server
start, `SHOW server_version` = `17.2 (MontuDB 4.8)`, `server_version_num` =
`170002`, `debug_assertions` = `off`, and `SELECT version()`.
