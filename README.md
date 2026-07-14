# Runner Internal Logs Action

Capture the internal `Runner_*.log` and `Worker_*.log` files from Linux, macOS,
and Windows GitHub Actions runners and upload them as an artifact.

```yaml
- name: Capture runner internal logs
  if: always()
  uses: austenstone/runner-internal-logs-action@v3
```

The artifact is named `runner-internal-logs` and retained for one day by
default:

```yaml
- name: Capture runner internal logs
  if: always()
  uses: austenstone/runner-internal-logs-action@v3
  with:
    artifact-name: my-runner-logs
    retention-days: 3
```

The action discovers the runner installation from the live `Runner.Worker`
process instead of hardcoding a runner version or installation path.

## Demo

Run the [Demo workflow](.github/workflows/demo.yml), then download the
`demo-runner-internal-logs` artifact from the workflow run.

## Security

Runner diagnostic logs contain the complete internal job message, execution
details, context values, and runner metadata. Keep artifacts private, use short
retention periods, and review them before sharing.

## Support

Linux, macOS, and Windows runners are supported.
