# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) preset. Use it from a repository's `renovate.json`:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>mtaku3/renovate-config"]
}
```

`default.json` extends `config:recommended` and `customManagers:dockerfileVersions`, so `# renovate:` comments above `ARG`/`ENV *_VERSION` lines in Dockerfiles are tracked. It also turns on lock file maintenance and turns off the devbox manager, since devbox.json only holds local development tools.
