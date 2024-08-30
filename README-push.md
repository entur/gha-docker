# `gha-docker/push`

## Usage

Add the following step to your workflow configuration:

```yml
jobs:
  docker-push:
    if: ${{ github.event_name != 'pull_request' }} # Don't push on PR
    name: Docker Push
    uses: entur/gha-docker/.github/workflows/push.yml@v1
```

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                                     INPUT                                     |  TYPE   | REQUIRED |    DEFAULT     |                                                               DESCRIPTION                                                               |
|-------------------------------------------------------------------------------|---------|----------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------|
|  <a name="input_cloud_provider"></a>[cloud_provider](#input_cloud_provider)   | string  |  false   |    `"gcp"`     |                            Which cloud service provider to <br>use - Google Cloud: 'gcp' <br>or Azure: 'az'                             |
|             <a name="input_context"></a>[context](#input_context)             | string  |  false   |     `"."`      |                                             Build context, default root of <br>repository                                               |
|        <a name="input_dockerfile"></a>[dockerfile](#input_dockerfile)         | string  |  false   | `"Dockerfile"` |                                                  Dockerfile name to use for <br>build                                                   |
|       <a name="input_environment"></a>[environment](#input_environment)       | string  |  false   |    `"prd"`     | [ Deprecated - do not <br>use ] - GitHub environment <br>to use Google Cloud: (dev, tst, prd) <br>or Azure: (az-dev, az-test, az-prod)  |
|             <a name="input_git_tag"></a>[git_tag](#input_git_tag)             | boolean |  false   |     `true`     |   Tag the repository default branch <br>with the image_tag? Used by <br>Harness CD to deploy the <br>exact same helm/terraform code     |
|        <a name="input_image_name"></a>[image_name](#input_image_name)         | string  |  false   | `"repo_name"`  |                                                    GitHub artifact with Docker image                                                    |
|          <a name="input_image_tag"></a>[image_tag](#input_image_tag)          | string  |  false   | `"image_tag"`  |                                Docker tag. If not set, <br>it will be set to <br>'branch_name.date-SHA'                                 |
| <a name="input_timeout_minutes"></a>[timeout_minutes](#input_timeout_minutes) | number  |  false   |      `10`      |                                                           Timeout in minutes                                                            |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->

|                                  OUTPUT                                   |                                   VALUE                                    | DESCRIPTION |
|---------------------------------------------------------------------------|----------------------------------------------------------------------------|-------------|
| <a name="output_image_and_tag"></a>[image_and_tag](#output_image_and_tag) | `"${{ jobs.push.outputs.image_name }}:${{ jobs.push.outputs.image_tag }}"` |             |
|     <a name="output_image_name"></a>[image_name](#output_image_name)      |                  `"${{ jobs.push.outputs.image_name }}"`                   |             |
|       <a name="output_image_tag"></a>[image_tag](#output_image_tag)       |                   `"${{ jobs.push.outputs.image_tag }}"`                   |             |

<!-- AUTO-DOC-OUTPUT:END -->
