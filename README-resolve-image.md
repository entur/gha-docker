# `gha-docker/resolve-image`

Resolves the Docker image that was built during a PR by looking up git tags created by the [push](README-push.md) workflow. Intended for use in CD workflows that run after a PR is merged to `main`.

> [!TIP]
> This is useful for only building the docker image once in the CI/CD pipelines.

When the push workflow builds and pushes a Docker image, it also creates a git tag with the image tag value (e.g. `my-branch.20260409-SHA1234567`). This workflow finds the merged PR for the current commit, reconstructs the sanitised branch name, and looks up the most recent matching git tag to resolve the exact image that was built.

> [!NOTE]
> If no matching tag is found (e.g. docs-only changes), the workflow succeeds with empty `image` and `image_tag` outputs. Downstream deploy jobs can use this to skip deployment.

## Usage

Add the following step to your CD workflow:

```yml
jobs:
  resolve-image:
    if: github.event_name == 'push'
    uses: entur/gha-docker/.github/workflows/resolve-image.yml@v1

  deploy:
    needs: [resolve-image]
    if: needs.resolve-image.outputs.image != ''
    uses: entur/gha-helm/.github/workflows/deploy.yml@v1
    with:
      image: ${{ needs.resolve-image.outputs.image }}
```

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

| INPUT                                                          | TYPE   | REQUIRED | DEFAULT       | DESCRIPTION                                                 |
| -------------------------------------------------------------- | ------ | -------- | ------------- | ----------------------------------------------------------- |
| <a name="input_image_name"></a>[image_name](#input_image_name) | string | false    | `"repo_name"` | Image name to resolve. Defaults <br>to the repository name. |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->

| OUTPUT                                                        | VALUE                                           | DESCRIPTION                                                                             |
| ------------------------------------------------------------- | ----------------------------------------------- | --------------------------------------------------------------------------------------- |
| <a name="output_image"></a>[image](#output_image)             | `"${{ jobs.resolve-image.outputs.image }}"`     | Resolved image name and tag <br>(image_name:image_tag), empty if no <br>image was built |
| <a name="output_image_tag"></a>[image_tag](#output_image_tag) | `"${{ jobs.resolve-image.outputs.image_tag }}"` | Resolved image tag, empty if <br>no image was built for <br>the PR                      |
| <a name="output_pr_number"></a>[pr_number](#output_pr_number) | `"${{ jobs.resolve-image.outputs.pr_number }}"` | The PR number that was <br>merged at the current commit                                 |

<!-- AUTO-DOC-OUTPUT:END -->
