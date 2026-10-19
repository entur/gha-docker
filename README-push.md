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

### Downloading the image artifact from another repository

By default the image artifact is fetched from the current workflow run. To fetch it from another repository, set `artifact_repository` and `artifact_run_id`, and pass a token with `actions:read` on that repository:

```yml
jobs:
  docker-push:
    uses: entur/gha-docker/.github/workflows/push.yml@v1
    with:
      artifact_repository: my-org/other-repo
      artifact_run_id: ${{ needs.build.outputs.run_id }}
    secrets:
      artifact_github_token: ${{ secrets.OTHER_REPO_TOKEN }}
```

> [!NOTE]
> `artifact_github_token` is required when `artifact_repository` is another repository, including internal ones. If it is omitted, the workflow falls back to the default `GITHUB_TOKEN`, which can only access the current repository. The download step will then fail with a "Not Found" / "Artifact not found" error.

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                                           INPUT                                           |  TYPE   | REQUIRED |    DEFAULT     |                                                                                 DESCRIPTION                                                                                  |
|-------------------------------------------------------------------------------------------|---------|----------|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <a name="input_artifact_repository"></a>[artifact_repository](#input_artifact_repository) | string  |  false   |                |                               Repository (owner/name) to download the <br>Docker image artifact from. Defaults <br>to the current repository                                 |
|       <a name="input_artifact_run_id"></a>[artifact_run_id](#input_artifact_run_id)       | string  |  false   |                |      Workflow run ID to download <br>the Docker image artifact from. <br>Defaults to the current run. <br>Required when artifact_repository is another <br>repository        |
|        <a name="input_cloud_provider"></a>[cloud_provider](#input_cloud_provider)         | string  |  false   |    `"gcp"`     |                                              Which cloud service provider to <br>use - Google Cloud: 'gcp' <br>or Azure: 'az'                                                |
|                   <a name="input_context"></a>[context](#input_context)                   | string  |  false   |     `"."`      |                                                                Build context, default root of <br>repository                                                                 |
|              <a name="input_dockerfile"></a>[dockerfile](#input_dockerfile)               | string  |  false   | `"Dockerfile"` |                                                                    Dockerfile name to use for <br>build                                                                      |
|     <a name="input_extra_image_tags"></a>[extra_image_tags](#input_extra_image_tags)      | string  |  false   |                | Extra Docker tags (comma separated) to <br>apply and push - Requires <br>Harness project-level setting 'Execute Triggers <br>With All Collected Artifacts or <br>Manifests'  |
|                   <a name="input_git_ref"></a>[git_ref](#input_git_ref)                   | string  |  false   |                |                               Option to override git reference <br>to checkout before push, will <br>replace the SHA in default <br>image_tag                                |
|                   <a name="input_git_tag"></a>[git_tag](#input_git_tag)                   | boolean |  false   |     `true`     |                      Tag the repository default branch <br>with the image_tag? Used by <br>Harness CD to deploy the <br>exact same helm/terraform code                       |
|              <a name="input_image_name"></a>[image_name](#input_image_name)               | string  |  false   | `"repo_name"`  |                                                                      GitHub artifact with Docker image                                                                       |
|                <a name="input_image_tag"></a>[image_tag](#input_image_tag)                | string  |  false   | `"image_tag"`  |                                                  Docker tag. If not set, <br>it will be set to <br>'branch_name.date-SHA'                                                    |
|       <a name="input_timeout_minutes"></a>[timeout_minutes](#input_timeout_minutes)       | number  |  false   |      `10`      |                                                                              Timeout in minutes                                                                              |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->

|                                    OUTPUT                                    |                                   VALUE                                    |                         DESCRIPTION                         |
|------------------------------------------------------------------------------|----------------------------------------------------------------------------|-------------------------------------------------------------|
| <a name="output_all_image_tags"></a>[all_image_tags](#output_all_image_tags) |                `"${{ jobs.push.outputs.all_image_tags }}"`                 | All image tags pushed to <br>the registry, comma separated  |
|  <a name="output_image_and_tag"></a>[image_and_tag](#output_image_and_tag)   | `"${{ jobs.push.outputs.image_name }}:${{ jobs.push.outputs.image_tag }}"` |                  Full image name with tag                   |
|       <a name="output_image_name"></a>[image_name](#output_image_name)       |                  `"${{ jobs.push.outputs.image_name }}"`                   |                  Name of the Docker image                   |
|        <a name="output_image_tag"></a>[image_tag](#output_image_tag)         |                   `"${{ jobs.push.outputs.image_tag }}"`                   |                   Tag of the Docker image                   |

<!-- AUTO-DOC-OUTPUT:END -->
