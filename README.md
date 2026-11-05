# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) preset. Use it from a repository's `renovate.json`:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>mtaku3/renovate-config"]
}
```

`default.json` extends `config:recommended` and `customManagers:dockerfileVersions`, so `# renovate:` comments above `ARG`/`ENV *_VERSION` lines in Dockerfiles are tracked. It also turns on lock file maintenance and turns off the devbox manager, since devbox.json only holds local development tools.

`osvVulnerabilityAlerts` checks direct dependencies against [OSV](https://osv.dev/) (Go, PyPI, npm, crates and other language package datasources; not Docker images or Nix). A dependency with a known vulnerability gets an immediate PR to the lowest fixed version, titled with a `[SECURITY]` suffix.
