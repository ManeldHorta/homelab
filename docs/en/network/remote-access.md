# Remote Access

## Current state

Tailscale is currently used to provide remote access to internal homelab services.

Tailscale allows access to services without directly exposing their ports to the Internet.

## Current architecture

Remote access is provided through the Tailscale network of authorized devices.

Detailed configuration, node information and access policies are kept outside the public documentation.

## Future architecture

Tailscale is considered a temporary solution.

When the dedicated router/firewall is deployed, it is planned to replace Tailscale with a remote access system managed by the router itself, using VPN.

This future architecture will be part of the network firewall, VLAN and access-control design.

## Security

The following information is not published:

- Tailscale keys or tokens;
- node identifiers;
- ACL configuration;
- internal addresses;
- configurations that could reproduce the remote access setup.
