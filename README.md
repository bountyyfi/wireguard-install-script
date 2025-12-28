# WireGuard Install Script

A simple, interactive WireGuard VPN installer for Debian 13 (Trixie) and other Linux distributions.

## Supported Operating Systems

- **Debian 11, 12, 13 (Trixie)**
- Ubuntu 22.04+
- AlmaLinux/Rocky Linux 9+
- CentOS 9+
- Fedora

## Debian 13 (Trixie) Support

This script fully supports Debian 13 Trixie, including the testing release. The installer automatically detects Trixie by codename and configures WireGuard appropriately.

## Requirements

- Root privileges (run with `sudo` or as root)
- Bash shell (not `sh`)
- A supported Linux distribution
- WireGuard kernel module support

## Quick Start

```bash
# Download and run the installer
sudo bash install.sh
```

## Features

- **Interactive setup**: Guided installation with prompts for configuration
- **Client management**: Add and remove VPN clients easily
- **DNS options**: Choose from popular DNS providers or specify custom resolvers
- **IPv6 support**: Automatic dual-stack configuration when available
- **QR code generation**: Scan to configure mobile clients
- **Firewall integration**: Works with iptables and firewalld

## Usage

### Initial Installation

Run the script for the first time to set up the WireGuard server:

```bash
sudo bash install.sh
```

You will be prompted to configure:
1. Server IP address (auto-detected)
2. Public IP/hostname (if behind NAT)
3. Listening port (default: 51820)
4. First client name
5. DNS server for clients

### Managing Clients

Run the script again after installation to:
1. Add a new client
2. Remove an existing client
3. Uninstall WireGuard
4. Exit

```bash
sudo bash install.sh
```

## Client Configuration

After creating a client, the configuration file is saved in the same directory as the script (e.g., `client.conf`). You can:
- Import the `.conf` file into the WireGuard app
- Scan the QR code displayed in the terminal

## DNS Options

The installer offers several DNS choices:
- System default resolvers
- Google (8.8.8.8)
- Cloudflare (1.1.1.1)
- OpenDNS
- Quad9
- AdGuard
- Custom DNS servers

## Notes

- The script requires the WireGuard kernel module (no userspace fallback)
- For containers, ensure the host has the WireGuard module loaded
- Maximum of 253 clients per server

## License

This project is open source.