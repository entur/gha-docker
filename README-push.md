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

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                                   INPUT                                    |  TYPE  | REQUIRED |    DEFAULT     |            DESCRIPTION             |
|----------------------------------------------------------------------------|--------|----------|----------------|------------------------------------|
| <a name="input_cloud_provider"></a>[cloud_provider](#input_cloud_provider) | string |  false   |    `"GCP"`     | Which repository to use. GCP/Azure |
|       <a name="input_dockerfile"></a>[dockerfile](#input_dockerfile)       | string |  false   | `"Dockerfile"` |    Dockerfile to use for build     |
|     <a name="input_environment"></a>[environment](#input_environment)      | string |  false   |    `"prd"`     |     GitHub environment to use      |
|       <a name="input_image_name"></a>[image_name](#input_image_name)       | string |  false   | `"repo_name"`  | GitHub artifact with Docker image  |
|        <a name="input_image_tag"></a>[image_tag](#input_image_tag)         | string |  false   | `"image_tag"`  |             Docker tag             |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->

|                              OUTPUT                              |                  VALUE                  | DESCRIPTION |
|------------------------------------------------------------------|-----------------------------------------|-------------|
| <a name="output_image_name"></a>[image_name](#output_image_name) | `"${{ jobs.push.outputs.image_name }}"` |             |
|  <a name="output_image_tag"></a>[image_tag](#output_image_tag)   | `"${{ jobs.push.outputs.image_tag }}"`  |             |

<!-- AUTO-DOC-OUTPUT:END -->
