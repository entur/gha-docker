# `gha-docker/lint`

## Usage

Add the following step to your workflow configuration:

```yml
jobs:
  docker-lint:
    name: Docker Lint
    uses: entur/gha-docker/.github/workflows/lint.yml@v1
```

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                                     INPUT                                     |  TYPE  | REQUIRED |    DEFAULT     |                   DESCRIPTION                   |
|-------------------------------------------------------------------------------|--------|----------|----------------|-------------------------------------------------|
|        <a name="input_dockerfile"></a>[dockerfile](#input_dockerfile)         | string |  false   | `"Dockerfile"` |             Which dockerfile to run             |
|              <a name="input_ignore"></a>[ignore](#input_ignore)               | string |  false   |                | A comma separated list of <br>Hadolint Ignores  |
| <a name="input_timeout_minutes"></a>[timeout_minutes](#input_timeout_minutes) | number |  false   |      `2`       |               Timeout in minutes                |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->
No outputs.
<!-- AUTO-DOC-OUTPUT:END -->

## Secrets

<!-- AUTO-DOC-SECRETS:START - Do not remove or modify this section -->
No secrets.
<!-- AUTO-DOC-SECRETS:END -->
