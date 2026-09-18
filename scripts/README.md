# Scripts

This directory contains administration and automation scripts used by the homelab.

Known operational scripts currently used on PCVR1 include:

- `start-mediastack.ps1` — starts the Media Stack and related Tdarr containers;
- `stop-mediastack.ps1` — stops the Media Stack and related Tdarr containers;
- `watch-tdarr-node.ps1` — checks Tdarr Node logs and performs the configured recovery action when the monitored error condition is detected.

The scripts are integrated with Windows Task Scheduler where applicable.

## Security

Scripts committed to the public repository must not contain:

- passwords;
- API tokens;
- authentication keys;
- private identifiers;
- other secrets.

Secrets should be supplied through a secure mechanism rather than embedded directly in scripts.

## Documentation

Operational behaviour and scheduling are documented under:

`docs/ca/operations/`

and

`docs/en/operations/`
