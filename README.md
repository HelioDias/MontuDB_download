# MontuDB 2.30

**MontuDB 2.30 is based on PostgreSQL 17.2.** It reports its version as:

```
PostgreSQL 17.2 (MontuDB 2.30)
```

It installs under **`/opt/montudb/2.30`**, does **not** replace the system
PostgreSQL, and does **not** initialize or start a cluster automatically. The
suggested listening port is **`55432`** so it never clashes with a PostgreSQL
running on the default `5432`.

## Choose your package

| Platform | File |
|---|---|
| Debian / Ubuntu / Raspberry Pi OS 64-bit (arm64) | `montudb_2.30-1_arm64.deb` |
| Debian / Ubuntu (amd64) | `montudb_2.30-1_amd64.deb` |
| RHEL / Rocky / Alma / Oracle Linux (x86_64) | `montudb-2.30-1.x86_64.rpm` |
| RHEL / Rocky / Alma / Oracle Linux (aarch64) | `montudb-2.30-1.aarch64.rpm` |
| Portable tarball (amd64) | `montudb-2.30-pg17.2-linux-amd64.tar.gz` |
| Portable tarball (arm64) | `montudb-2.30-pg17.2-linux-arm64.tar.gz` |
| Docker (amd64) | `montudb-2.30-docker-amd64.tar` |
| Docker (arm64) | `montudb-2.30-docker-arm64.tar` |

**Raspberry Pi 64-bit uses the `arm64` artifacts.**

## Notes

- **Debian/Ubuntu/Raspberry Pi OS:** install the matching `.deb`.
- **RHEL/Rocky/Alma/Oracle Linux:** install the matching `.rpm`.
- **Portable use:** extract the tarball; the binaries are relocatable.
- **Docker:** load the matching `montudb-2.30-docker-<arch>.tar` archive.
- After installing, the cluster is initialized and started **manually** — the
  package only places files. Use the suggested port `55432`.

## Integrity

`SHA256SUMS` contains the SHA-256 checksum of every package in this folder.
`release-manifest.json` lists each artifact with its architecture, format, size
and checksum.

MontuDB is based on PostgreSQL 17.2 and is distributed under the PostgreSQL
License.
