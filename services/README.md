# Services

This directory contains service-specific deployment and configuration material.

The public documentation for each service is located under:

- `docs/ca/services/`
- `docs/en/services/`

Currently documented services include the Media Stack components, media services, Tdarr, Portainer, Dashy, Zabbix, and the local AI stack.

This directory is intended for implementation material rather than descriptive documentation.

Examples of material that may be stored here:

- service-specific Compose definitions;
- configuration templates;
- deployment manifests;
- integration definitions;
- non-sensitive service settings.

Secrets and credentials must not be committed.

## Relationship with `infrastructure/`

Use `infrastructure/` for infrastructure-level deployment definitions and shared platform configuration.

Use `services/` for material specific to an individual service or service group.

Avoid duplicating the same configuration in both locations.
