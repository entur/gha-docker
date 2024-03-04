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

### Outputs

### Examples
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