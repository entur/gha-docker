# `gha-docker/push`

## Usage

Add the following step to your workflow configuration:

```yml
jobs:
  docker-push:
    if: ${{ github.event_name != 'pull_request' }} # Don't push on PR
    name: Docker Push
    uses: entur/gha-docker/.github/workflows/push.yml@main
```

## Inputs

## Outputs
