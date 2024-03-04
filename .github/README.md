<h1 align="center">
      <img src="logo.png" width="96px" height="96px" />
      <br>entur/gha-docker<br>
</h1>

[![CI](https://github.com/entur/gha-docker/actions/workflows/ci.yaml/badge.svg?branch=main&event=pull_request)](https://github.com/entur/gha-docker/actions/workflows/ci.yaml)

GitHub Actions for working with Docker

## `gha-docker/lint`

### Usage

Add the following step to your workflow configuration:

```yml
jobs:
  docker-lint:
    name: Docker Lint
    uses: entur/gha-docker/.github/workflows/lint.yaml@main
```

### Inputs

| Name         | Description                                                           | Default        |
| ------------ | --------------------------------------------------------------------- | -------------- |
| `dockerfile` | The path to the Dockerfile to be tested, default `Dockerfile` in root | `./Dockerfile` |
| `ignores`    | A comma separated list of Hadolint ignores, ex `DL3000,DL3001`        | ``             |

## `gha-docker/build`

### Usage

Add the following step to your workflow configuration:

```yml
jobs:
  docker-build:
    name: Docker Build
    uses: entur/gha-docker/.github/workflows/build.yaml@main
```

### Inputs

| Name         | Description                                                           | Default                               |
| ------------ | --------------------------------------------------------------------- | ------------------------------------- |
| `dockerfile` | The path to the Dockerfile to be tested, default `Dockerfile` in root | `./Dockerfile`                        |
| `image_name` | Name of the image, default is repo name                               | `${{ github.event.repository.name }}` |

### Outputs

The Action will provide ouputs that can be used in other steps in a workflow.

| Name    | Description                           | Example                                                           |
| ------- | ------------------------------------- | ----------------------------------------------------------------- |
| `uri`   | The canonical full name of your image | `eu.gcr.io/entur-system-1287/my-awesome-app:main.2024-01-01T1200` |
| `image` | The name of your image                | `eu.gcr.io/entur-system-1287/my-awesome-app`                      |
| `tag`   | The tag of your image                 | `main.2024-01-01T1200`                                            |

Example to create a comment in a PR with image name:

```
- name: Show Image Tag
  uses: actions/github-script@v6
  if: github.event_name == 'pull_request'
  needs: docker-build
  with:
    script: |
      const output = `
      #### Docker Build: \`${{ needs.docker-build.outcome }}\`
      \`\`\`
      ${{ needs.docker-build.ouputs.uri }}
      \`\`\`
      `;

      github.rest.issues.createComment({
        issue_number: context.issue.number,
        owner: context.repo.owner,
        repo: context.repo.repo,
        body: output
      })
```

## `gha-docker/push`

### Usage

Add the following step to your workflow configuration:

```yml
jobs:
  docker-push:
    name: Docker Push
    uses: entur/gha-docker/.github/workflows/push.yaml@main
```

### Inputs

| Name         | Description       | Default           |
| ------------ | ----------------- | ----------------- |
| `image_name` | Name of the image | `$ENT_DOCKER_URI` |
