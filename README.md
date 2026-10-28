# Renovate: BellSoft Liberica Java ids in mise/asdf

Minimal reproduction for a Renovate pull request adding Liberica support to the
`mise` and `asdf` managers (see renovatebot/renovate#19183).

| File | Pin | Shape |
|---|---|---|
| `jdk/mise.toml` | `liberica-27.0.0+36` | plain JDK |
| `javafx/mise.toml` | `liberica-javafx-25.0.4.1+1` | JavaFX flavour, 5-part hotfix version |
| `nik/mise.toml` | `liberica-nik-openjdk25-25.0.3+2` | Native Image Kit |
| `java8/.tool-versions` | `liberica-jre-8u492+9` | Java 8 `8uN+N` id |
| `crac/.tool-versions` | `liberica-musl-crac-21.0.13.0.2+6` | CRaC on musl, asdf-java spelling |

**Today:** every pin is extracted with `skipReason: "unsupported-datasource"`, so
Renovate never proposes an update.

**With the PR:** each pin resolves against `github-releases` on `bell-sw/Liberica`
(or `bell-sw/LibericaNIK` for NIK) with `loose` versioning, and Renovate proposes
the newer release of the same flavour (e.g. `liberica-27.0.1.0.3+5`). Early-access
tags such as `26+29-ea` are not offered.

Check locally:

```bash
LOG_LEVEL=debug npx renovate --platform=local --dry-run=lookup
```
