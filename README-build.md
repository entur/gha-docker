# `gha-docker/build`

## Usage

Add the following step to your workflow configuration:

```yml
jobs:
  docker-build:
    name: Docker Build
    uses: entur/gha-docker/.github/workflows/build.yml@v1
```

---

### Advanced inputs examples

#### Secrets

If you need to pass secrets to your Dockerfile, you can use this recipe:

```yml
jobs:
  docker-build:
    uses: entur/gha-docker/.github/workflows/build.yml@v1
    secrets:
      BUILD_SECRETS: |
        "ARTIFACTORY_AUTH_USER=${{ secrets.ARTIFACTORY_AUTH_USER }}"
        "ARTIFACTORY_AUTH_TOKEN=${{ secrets.ARTIFACTORY_AUTH_TOKEN }}"
```

You can now mount and use these secrets in your Dockerfile:

```Dockerfile
RUN --mount=type=secret,id=ARTIFACTORY_AUTH_USER,env=ARTIFACTORY_AUTH_USER  \
    --mount=type=secret,id=ARTIFACTORY_AUTH_TOKEN,env=ARTIFACTORY_AUTH_TOKEN  ./gradlew build
```

#### Additional artifacts
If you need additional files generated inside your Docker image to be saved to the Github artifact storage, you can use this recipe:

```yml
jobs:
  docker-build:
    uses: entur/gha-docker/.github/workflows/build.yml@v1
    with:
      additional_artifacts_name: my-artifact-name
      additional_artifacts_paths: |
        /absolute/path/to/test.txt
        /absolute/path/to/an/openapi.json
```

This will result in a flat directory structure inside the artifact, i.e. the files will be accessible at the root level of the artifact:

```shell
├── my-artifact-name
│   ├── test.txt
│   ├── openapi.json
```

You can now download the Github artifact and use it in subsequent jobs in your workflow, or reference the artifact in reusable workflow supporting that.

## Inputs

<!-- AUTO-DOC-INPUT:START - Do not remove or modify this section -->

|                                                     INPUT                                                      |  TYPE  | REQUIRED |       DEFAULT        |                                                                                                                DESCRIPTION                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------|--------|----------|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <a name="input_additional_artifacts_name"></a>[additional_artifacts_name](#input_additional_artifacts_name)   | string |  false   |                      |                                                                                       Name of GitHub artifact to <br>contain additional artifacts.                                                                                         |
| <a name="input_additional_artifacts_paths"></a>[additional_artifacts_paths](#input_additional_artifacts_paths) | string |  false   |                      |                                                                           List of paths to additional <br>artifacts to be saved to <br>Github artifact storage.                                                                            |
|                         <a name="input_build_args"></a>[build_args](#input_build_args)                         | string |  false   |                      |                                                                  List of build args to <br>pass to docker build. Warning! <br>Do not pass secrets into <br>docker args.                                                                    |
|           <a name="input_build_artifact_name"></a>[build_artifact_name](#input_build_artifact_name)            | string |  false   |                      |                                                                                                Name of GitHub artifact to <br>add to build                                                                                                 |
|           <a name="input_build_artifact_path"></a>[build_artifact_path](#input_build_artifact_path)            | string |  false   |    `"build/libs"`    |                                                                                                            Path to the artifact                                                                                                            |
|                   <a name="input_cloud_provider"></a>[cloud_provider](#input_cloud_provider)                   | string |  false   |       `"gcp"`        |                                                                             Which cloud service provider to <br>use - Google Cloud: 'gcp' <br>or Azure: 'az'                                                                               |
|                             <a name="input_context"></a>[context](#input_context)                              | string |  false   |        `"."`         |                                                                                               Build context, default root of <br>repository                                                                                                |
|                         <a name="input_dockerfile"></a>[dockerfile](#input_dockerfile)                         | string |  false   |    `"Dockerfile"`    |                                                                                                        Dockerfile to use for build                                                                                                         |
|                             <a name="input_git_ref"></a>[git_ref](#input_git_ref)                              | string |  false   |                      |                                                                                       Option to override git reference <br>to checkout before build                                                                                        |
|                         <a name="input_image_name"></a>[image_name](#input_image_name)                         | string |  false   |    `"repo_name"`     |                                                                                                    Image name to use for <br>the build                                                                                                     |
|                               <a name="input_runner"></a>[runner](#input_runner)                               | string |  false   | `"['ubuntu-24.04']"` | Runner to use for the <br>build. To use a runner <br>group, use the format "{'group': <br>'group_name'}". See https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idruns-on for more <br>information.  |
|                 <a name="input_timeout_minutes"></a>[timeout_minutes](#input_timeout_minutes)                  | number |  false   |         `40`         |                                                                                                             Timeout in minutes                                                                                                             |

<!-- AUTO-DOC-INPUT:END -->

## Outputs

<!-- AUTO-DOC-OUTPUT:START - Do not remove or modify this section -->

|                                             OUTPUT                                             |                       VALUE                        | DESCRIPTION |
|------------------------------------------------------------------------------------------------|----------------------------------------------------|-------------|
| <a name="output_additional_artifacts"></a>[additional_artifacts](#output_additional_artifacts) | `"${{ jobs.build.outputs.additional_artifacts }}"` |             |
|          <a name="output_image_artifact"></a>[image_artifact](#output_image_artifact)          |    `"${{ jobs.build.outputs.image_artifact }}"`    |             |

<!-- AUTO-DOC-OUTPUT:END -->
