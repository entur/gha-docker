# `gha-docker/lint`

## Usage

Add the following step to your workflow configuration:

```yml
jobs:
  docker-lint:
    name: Docker Lint
    uses: entur/gha-docker/.github/workflows/lint.yaml@main
```

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                             INPUT                              |  TYPE  | REQUIRED | DEFAULT |                   DESCRIPTION                    |
|----------------------------------------------------------------|--------|----------|---------|--------------------------------------------------|
| <a name="input_dockerfile"></a>[dockerfile](#input_dockerfile) | string |  false   |         | Which dockerfile to run, default <br>Dockerfile  |
|       <a name="input_ignore"></a>[ignore](#input_ignore)       | string |  false   |         | A comma separated list of <br>Hadolint Ignores   |

<!-- AUTO-DOC-INPUT:END -->


## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->
No outputs.
<!-- AUTO-DOC-OUTPUT:END -->

## Secrets

<!-- AUTO-DOC-SECRETS:START - Do not remove or modify this section -->
No secrets.
<!-- AUTO-DOC-SECRETS:END -->

<!-- AUTO-DOC-SECRET:START - Do not remove or modify this section -->
<!-- AUTO-DOC-SECRET:END -->
