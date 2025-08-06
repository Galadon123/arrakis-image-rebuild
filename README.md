# Arrakis Self-Contained Release

A complete, self-contained release of the Arrakis system.

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

4. **Connect with client** (in another terminal)
   ```bash
   ./arrakis-client
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

## Directory Structure

```
arrakis-release/
├── arrakis-restserver      # Server binary
├── arrakis-client          # Client binary
├── install.sh              # Setup script
├── config.yaml             # Configuration
├── README.md               # This file
├── resources/
│   └── bin/
│       ├── cloud-hypervisor  # Hypervisor binary
│       └── vmlinux.bin       # Linux kernel
└── out/
    ├── arrakis-guestrootfs-ext4.img  # Root filesystem
    └── initramfs.cpio.gz             # Initramfs
```

## Network Setup (Optional)

For full functionality including networking, set up a bridge interface:

```bash
# Create bridge
sudo ip link add br0 type bridge
sudo ip addr add 10.20.1.1/24 dev br0
sudo ip link set br0 up

# Add your network interface to the bridge
sudo ip link set <your-interface> master br0
```

## Troubleshooting

### KVM Not Available
- Enable virtualization in your BIOS/UEFI settings
- Check if KVM is loaded: `lsmod | grep kvm`

### Permission Denied
- Run the setup script: `./install.sh`
- Ensure you have sudo privileges

### Network Issues
- The system works without networking for basic functionality
- For full features, set up the bridge as described above

## Support

For issues or questions, please refer to the main Arrakis documentation.

## Version Information

- **Release Date**: August 6, 2025
- **Cloud Hypervisor**: v47.0
- **Linux Kernel**: v6.12.8
- **Total Size**: ~4.5GB (compressed) 
