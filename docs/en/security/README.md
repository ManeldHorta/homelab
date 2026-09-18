# Security

## Principles

The homelab follows a local-first approach.

The main objectives are:

- Minimize unnecessary Internet exposure.
- Keep sensitive data out of the public repository.
- Separate public configuration from private information.
- Apply network segmentation where appropriate.
- Monitor infrastructure status.

## Credentials

Credentials must never be published in the public repository.

This includes:

- Passwords
- Tokens
- API keys
- SSH keys
- Private certificates
- Database credentials

## Telegram

Telegram notifications are part of the homelab operations.

The bot token and chat ID are private information and must not be included in public documentation.

## Git

The public repository contains infrastructure documentation without operational secrets.

Configuration files containing credentials, secrets or private data must remain outside the public repository.

## Network

Network segmentation, VLANs and firewall rules are used to limit communication between different types of devices and services.

Details that could expose sensitive network information should be reviewed before publication.

## Local services

Local AI services remain inside the local infrastructure.

The objective is to avoid sending data used by these services to the Internet.

## Minimum exposure

Only services that are actually required should be exposed.

Ports, credentials and detailed configuration should only be documented when necessary and must never include secrets.
