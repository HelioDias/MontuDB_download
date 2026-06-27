# MontuDB 4.80

**MontuDB 4.80 is based on PostgreSQL 17.2.** Every binary reports its version
as:

```
PostgreSQL 17.2 (MontuDB 4.8)
```

> **Version naming:** the compiled-in brand is `(MontuDB 4.8)` (the Montu
> Optimizer "V4 Compose" release), while the packages, install path and file
> names use `4.80`. They refer to the same release.

It installs under **`/opt/montudb/4.80`**, does **not** replace the system
PostgreSQL, and does **not** initialize or start a cluster automatically. The
suggested listening port is **`55432`** so it never clashes with a PostgreSQL
running on the default `5432`.

## Choose your package

| Platform | File |
|---|---|
| Debian / Ubuntu / Raspberry Pi OS 64-bit (arm64) | `montudb_4.80-1_arm64.deb` |
| Debian / Ubuntu (amd64) | `montudb_4.80-1_amd64.deb` |
| RHEL / Rocky / Alma / Oracle Linux (x86_64) | `montudb-4.80-1.x86_64.rpm` |
| RHEL / Rocky / Alma / Oracle Linux (aarch64) | `montudb-4.80-1.aarch64.rpm` |
| Portable tarball (amd64) | `montudb-4.80-pg17.2-linux-amd64.tar.gz` |
| Portable tarball (arm64) | `montudb-4.80-pg17.2-linux-arm64.tar.gz` |
| Docker (amd64) | `montudb-4.80-docker-amd64.tar` |
| Docker (arm64) | `montudb-4.80-docker-arm64.tar` |

**Raspberry Pi 64-bit uses the `arm64` artifacts.**

## Notes

- **Debian/Ubuntu/Raspberry Pi OS:** install the matching `.deb`.
- **RHEL/Rocky/Alma/Oracle Linux:** install the matching `.rpm`.
- **Portable use:** extract the tarball; the binaries are relocatable.
- **Docker:** load the matching `montudb-4.80-docker-<arch>.tar` archive.
- After installing, the cluster is initialized and started **manually** — the
  package only places files. Use the suggested port `55432`.

## Confirm the version

```bash
/opt/montudb/4.80/bin/postgres --version    # postgres (PostgreSQL) 17.2 (MontuDB 4.8)
/opt/montudb/4.80/bin/psql --version        # psql (PostgreSQL) 17.2 (MontuDB 4.8)
```

```sql
SHOW server_version;       -- 17.2 (MontuDB 4.8)
SHOW server_version_num;   -- 170002
SELECT version();          -- PostgreSQL 17.2 (MontuDB 4.8) on ...
```

## Integrity

`SHA256SUMS` contains the SHA-256 checksum of every package in this folder.
`release-manifest.json` lists each artifact with its architecture, format, size
and checksum.

Every artifact in this release was **built and functionally validated on its
own native architecture** (arm64 on a Raspberry Pi, amd64 on an x86_64 host):
`initdb` + start + `SHOW server_version` / `server_version_num` /
`debug_assertions=off` + `SELECT version()`.

MontuDB is based on PostgreSQL 17.2 and is distributed under the PostgreSQL
License.
