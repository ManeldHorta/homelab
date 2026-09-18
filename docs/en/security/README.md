# Security

## Overview

Homelab security is based on separation of functions, controlled service operation, and orderly infrastructure management.

The current architecture is a home infrastructure that is still evolving. Advanced network segmentation and centralized traffic control are part of the future architecture.

## Network and segmentation

The current network infrastructure uses a home gateway and UniFi equipment for local network connectivity.

There are currently no 802.1Q VLANs implemented. The `PCVR`, `Dispositius`, and `IoT` Wi-Fi networks are separate SSIDs and do not constitute real VLANs.

The future architecture will introduce a dedicated router/firewall with VLANs and access-control rules to separate different types of devices and services.

## Services and Docker

Homelab services are mainly run with Docker and distributed across different Compose projects according to their function.

Portainer is used to administer the containers.

Service configurations and persistent data are kept separate from media data where required by the service configuration.

## Secrets and credentials

The public repository must not contain:

- passwords;
- tokens;
- authentication keys;
- API secrets;
- service credentials;
- sensitive identifiers related to remote access.

Credentials and tokens for external services are not part of the public documentation.

Sensitive operational information required for recovery will be kept in the private repository or in secure storage.

## Updates

Updates to services and infrastructure components should be performed in a controlled manner.

Before updating:

1. Check the service status.
2. Identify the expected changes.
3. Ensure a recovery path is available when necessary.

After updating:

1. Check that the service is running.
2. Validate the main functionality.
3. Review logs if unexpected behaviour occurs.

## Recovery

Public documentation describes the architecture and operational principles, but does not contain all details required to fully reproduce or recover the infrastructure.

Detailed recovery procedures, internal configurations, and other sensitive operational data will be kept in private documentation.

Secrets should remain outside Git whenever possible, including the private repository.

## Future architecture

The future security architecture is planned around:

- a dedicated router/firewall;
- real VLANs to separate different types of devices and services;
- firewall rules and inter-VLAN traffic control;
- remote access through a VPN managed by the router;
- progressive migration of the current remote-access architecture.

This design will be defined when the dedicated router is deployed.

## Sensitive information

Public documentation avoids publishing information that is not necessary to understand the architecture, such as:

- complete internal addresses;
- firewall configurations;
- detailed remote-access configurations;
- keys and tokens;
- credentials;
- detailed information about authorized devices;
- data that would facilitate reproducing the internal configuration.

Private documentation will act as the recovery reference and may contain the operational details required for recovery, while keeping secrets outside Git whenever possible.
