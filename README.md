# Everr Action

Everr CI helpers. Capabilities are toggled via inputs.

> Built from `everr-labs/everr` at version `0.3.0`. Do not edit
> this repository directly; changes are overwritten on each release.

## Usage

```yaml
steps:
  - uses: everr-labs/everr-action@v0
    with:
      check-run-id: ${{ job.check_run_id }}
```

> Resource usage collection is on by default. To opt out, pass
> `resource-usage: "false"`.

## Inputs

| Name | Required | Default | Description |
| --- | --- | --- | --- |
| `resource-usage` | no | `true` | Collect per-job machine resource usage and upload a best-effort artifact. Set to "false" to opt out. |
| `check-run-id` | no | `` | Check run id for the current workflow job. Pass the workflow expression `job.check_run_id` from the calling workflow. Required when resource-usage is enabled; the action no-ops with a warning if it is missing. |
