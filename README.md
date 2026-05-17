# Everr Action

Everr CI helpers. Capabilities are opt-in via inputs.

> Built from `everr-labs/everr` at version `0.1.0`. Do not edit
> this repository directly; changes are overwritten on each release.

## Usage

```yaml
- uses: everr-labs/everr-action@v0
  with:
    resource-usage: "true"
    check-run-id: ${{ job.check_run_id }}
```

## Inputs

| Name | Required | Default | Description |
| --- | --- | --- | --- |
| `resource-usage` | no | `false` | Collect per-job machine resource usage and upload a best-effort artifact |
| `github-token` | no | `${{ github.token }}` | Token used to look up the current job's check_run_id via the GitHub API when resource-usage is enabled. The default uses the workflow-provided GITHUB_TOKEN; the calling workflow must grant `actions: read`. |
