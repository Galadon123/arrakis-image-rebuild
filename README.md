# Arrakis Self-Contained Release

A complete, self-contained release of the Arrakis system.

## Download the latest release
   ```
   wget https://github.com/Galadon123/arrakis-image-rebuild/releases/download/v0.2/arrakis-release.tar.gz
   ```

## Quick Start

1. **Extract the archive**
   ```bash
   tar -xzf arrakis-release.tar.gz
   cd arrakis-release
   ```

2. **Run the setup script**
   ```bash
   ./install.sh
   ```

3. **Start the server**
   ```bash
   ./arrakis-restserver
   ```

4. **Connect with client** 
   ```bash
   ./arrakis-client start -n agent-sandbox
   ```

## System Requirements

- **OS**: Linux with KVM support
- **Architecture**: x86_64
- **Virtualization**: KVM must be enabled in BIOS
- **Dependencies**: `sudo` (usually pre-installed)

## What's Included

This release contains all necessary components:

- **arrakis-restserver**: The main server binary
- **arrakis-client**: Client binary for connecting to the server
- **cloud-hypervisor**: Virtualization hypervisor (v47.0)
- **Linux kernel**: Custom kernel for the VM (v6.12.8)
- **Root filesystem**: Complete guest OS image (4GB)
- **Initramfs**: Initial RAM filesystem for boot
- **Configuration**: Pre-configured `config.yaml`

## Version Information

- **Release Date**: August 6, 2025
- **Cloud Hypervisor**: v47.0
- **Linux Kernel**: v6.12.8
- **Total Size**: ~4.5GB (compressed) 
