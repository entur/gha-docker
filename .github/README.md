<h1 align="center">
      <img src="logo.png" width="96px" height="96px" />
      <br>entur/gha-docker<br>
</h1>

[![CI](https://github.com/entur/gha-docker/actions/workflows/ci.yml/badge.svg)](https://github.com/entur/gha-docker/actions/workflows/ci.yml)

GitHub Actions for working with Docker

- [Docker lint](../README-lint.md)
- [Docker build](../README-build.md)
- [Docker push](../README-push.md)

## Golden Path

- `./Dockerfile` at the root of your repository
- No ignores for [hadolint](https://hadolint.github.io/hadolint/)
- Image name is equal to repository name
- Docker build needs no artifacts (it builds its own)

### Example

Let's look at an example, assume our repo is called `amazing-app`:

```sh
λ amazing-app ❯ tree
.
├── README.md
├── Dockerfile
└── .github
    └── workflows
        └── ci.yml
```

```yaml
# ci.yml
name: CI

on:
  pull_request:

jobs:
  docker-lint:
    uses: entur/gha-docker/.github/workflows/lint.yml@main

  docker-build:
    uses: entur/gha-docker/.github/workflows/build.yml@main

  docker-push:
    uses: entur/gha-docker/.github/workflows/push.yml@main
    secrets: inherit
```

