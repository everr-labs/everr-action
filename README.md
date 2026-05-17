# Everr Action

Everr CI helpers. Capabilities are toggled via inputs.

> Built from `everr-labs/everr` at version `0.2.0`. Do not edit
> this repository directly; changes are overwritten on each release.

## Usage

```yaml
permissions:
  contents: read
  actions: read

steps:
  - uses: everr-labs/everr-action@v0
```

> The action needs `actions: read` so it can look up its own job via
> the GitHub Jobs API to derive a `check_run_id`. The default
> `github-token` input uses the workflow's GITHUB_TOKEN.
>
> Resource usage collection is on by default. To opt out, pass
> `resource-usage: "false"`.

## Inputs

| Name | Required | Default | Description |
| --- | --- | --- | --- |
| `resource-usage` | no | `true` | Collect per-job machine resource usage and upload a best-effort artifact. Set to "false" to opt out. |
| `github-token` | no | `${{ github.token }}` | Token used to look up the current job's check_run_id via the GitHub API when resource-usage is enabled. The default uses the workflow-provided GITHUB_TOKEN; the calling workflow must grant `actions: read`. |
