# `gha-docker/sanitize-ref`

Sanitizes a git ref name for use in Docker image tags. Used internally by the [push](../../../README-push.md) workflow and [resolve-image](../resolve-image/README.md) action to ensure consistent branch name handling.

## Sanitization rules

1. Truncate to 43 characters (reserves space for `.YYYYMMDD-SHA1234567` suffix)
2. Remove trailing `-`
3. Lowercase and remove Norwegian characters (`ÆØÅæøå`)
4. Replace `/`, `.`, `!` with `-`

## Inputs

| INPUT | TYPE   | REQUIRED | DESCRIPTION              |
| ----- | ------ | -------- | ------------------------ |
| `ref` | string | true     | Git ref name to sanitize |

## Outputs

| OUTPUT | DESCRIPTION        |
| ------ | ------------------ |
| `ref`  | Sanitized ref name |
