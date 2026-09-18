
Security
Principles

The homelab follows a local-first security model.

The main objectives are:

Minimise unnecessary Internet exposure
Keep sensitive data local
Separate public documentation from private configuration
Use network segmentation where appropriate
Monitor infrastructure health
Maintain recoverable configurations
Credentials

Credentials must never be committed to the public repository.

Examples include:

Passwords
API keys
Telegram bot tokens
SSH keys
Private certificates
Database credentials
Public and Private Repositories

The public repository contains documentation and sanitised configuration examples.

Sensitive information is maintained in the separate private repository:

homelab-private
Secrets Management

Public examples should use placeholders instead of real credentials.

Example:

TELEGRAM_BOT_TOKEN=
TELEGRAM_CHAT_ID=
RADARR_API_KEY=
SONARR_API_KEY=
LIDARR_API_KEY=
Network Security

Network segmentation, firewall rules and restricted service exposure form part of the security architecture.

Detailed network security configuration will be documented after the network inventory.
