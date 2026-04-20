# `gha-docker/resolve-image`

Resolves the Docker image that was built during a PR by looking up git tags created by the [push](../../../README-push.md) workflow. Intended for use in CD workflows that run after a PR is merged to `main`.

> [!TIP]
> This is useful for only building the docker image once in the CI/CD pipelines.

When the push workflow builds and pushes a Docker image, it also creates a git tag with the image tag value (e.g. `my-branch.20260409-SHA1234567`). This action finds the merged PR for the current commit, reconstructs the sanitised branch name, and looks up the most recent matching git tag to resolve the exact image that was built.

> [!NOTE]
> If no matching tag is found (e.g. docs-only changes), the action succeeds with empty `image` and `image_tag` outputs. Downstream deploy steps can use this to skip deployment.

## Usage

Add the action as a step in your CD workflow. Requires checkout with full history and tags.

```yml
jobs:
  deploy:
    if: github.event_name == 'push'
    runs-on: ubuntu-24.04
    permissions:
      contents: read
      pull-requests: read
    steps:
      - uses: actions/checkout@v6
        with:
          fetch-depth: 0
          fetch-tags: true

      - uses: entur/gha-docker/.github/actions/resolve-image@v1
        id: resolve-image

      - if: steps.resolve-image.outputs.image != ''
        run: echo "Deploying ${{ steps.resolve-image.outputs.image }}"
```

## Inputs

| INPUT        | TYPE   | REQUIRED | DEFAULT       | DESCRIPTION                                             |
| ------------ | ------ | -------- | ------------- | ------------------------------------------------------- |
| `image_name` | string | false    | `"repo_name"` | Image name to resolve. Defaults to the repository name. |

## Outputs

| OUTPUT      | DESCRIPTION                                                                                  |
| ----------- | -------------------------------------------------------------------------------------------- |
| `image`     | Resolved image name and tag (`image_name:image_tag`), empty if no image was built for the PR |
| `image_tag` | Resolved image tag, empty if no image was built for the PR                                   |
| `pr_number` | The PR number that was merged at the current commit                                          |
