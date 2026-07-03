# Proxmox Homelab

This project summarizes my personal Proxmox homelab work for the IT-Support-Labs portfolio. It is based on documentation from my HaaS-platformV2 repository and is meant to give employers a concise overview of the infrastructure skills I practiced.

This is personal homelab and portfolio documentation. It does not represent paid production administration experience.

## Lab Purpose

The purpose of this lab is to practice building, documenting, and operating a small virtualization and service-hosting platform. The lab focuses on Proxmox VE, Debian-based VM templates, Docker service hosting, storage planning, reverse proxy access, security hardening, and backup/restore workflows.

## Source Repository

Detailed build notes, standards, and runbooks are documented in the source repository:

- [HaaS-platformV2](https://github.com/antonio708763/HaaS-platformV2)

This portfolio page is a summary only. It does not duplicate the full HaaS-platformV2 documentation.

## Environment Overview

The homelab is documented as a Proxmox VE-based platform with:

- Proxmox VE host documented in HaaS-platformV2
- Debian 12 Golden VM Template, VM100
- Cloned workload VMs, including VM200 as a Docker host
- ZFS-backed VM storage
- Docker and Docker Compose service hosting
- Traefik reverse proxy for DNS and HTTPS-based service access
- Immich documented as one service example
- Backup and restore workflows for important VMs

Some exact hardware and network details are still tracked in the source repo or remain to be documented here.

## Proxmox Host

The source repo documents a Proxmox VE host used for virtualization practice and platform build documentation.

Documented host details include:

- Proxmox VE host installed from the official ISO
- Proxmox VE version documented as `pve-manager 9.1.1`
- Kernel documented as `6.17.2-1-pve`
- Local SSD installation
- Legacy BIOS boot mode
- Proxmox storage configuration tracked through `/etc/pve/storage.cfg`

Placeholder details to document later:

- Host hardware model: To be documented
- CPU and RAM: To be documented
- Physical disk layout after remediation: To be documented

## Storage Design

The lab uses ZFS-backed VM storage for Proxmox virtual machines.

Documented storage concepts include:

- `local` directory storage for ISO images, container templates, backups, and imports
- `local-zfs` backed by `rpool/data` for VM disk images and container root filesystems
- VM disks implemented as ZFS zvols
- Snapshot behavior documented as disk-only when appropriate
- Backup storage standards documented separately from primary VM storage

A storage issue was documented honestly in the source repo: the ZFS pool was reported as degraded with a disk-health concern. This makes the environment suitable for research and learning, but not suitable for production or client use until the disk health and storage design are fixed.

## Network Design

The HaaS-platformV2 documentation uses a DNS and reverse proxy model for clean service access.

Documented network and access concepts include:

- VM200 as the Docker host and reverse proxy entry point
- Traefik as the reverse proxy
- Services accessed through DNS names and HTTPS instead of raw IP addresses and ports
- `home.ar` used as the internal DNS naming standard in the source repo
- Example service access such as `https://photos.home.ar`
- Future DNS VM planning, such as VM210 for dedicated DNS

Exact IP addressing for the current homelab should be confirmed before being reused in this portfolio summary.

## VM Template Design

The lab uses a Debian 12 Golden VM Template documented as VM100.

VM100 is documented with:

- Debian 12 Bookworm baseline
- VMID `100`
- OVMF/UEFI boot design
- q35 machine type
- Secure Boot disabled for repeatable boot behavior
- QEMU Guest Agent integration
- SSH access baseline
- Fail2Ban protection for SSH
- Serial console access for recovery
- Backup and restore testing before using the template as a source for clones

Workload VMs are cloned from VM100. One documented example is VM200, a Debian 12 Docker host cloned from the Golden Template.

## Docker Host / Services

VM200 is documented as the main Docker host for service stacks.

Documented VM200 practices include:

- VMID `200`
- Name documented as `docker-host-01`
- Debian 12 workload VM cloned from VM100
- Docker Engine and Docker Compose validation
- Service stack configuration under `/srv/stacks/`
- Persistent application data under `/srv/data/`
- Shared Docker `proxy` network for services routed through Traefik
- Traefik reverse proxy deployed before service stacks
- Service access through DNS and HTTPS
- Secrets kept out of GitHub by using safe examples and local `.env` files

Immich is one documented service example. In the source repo, Immich is deployed as a Docker Compose stack on VM200 and accessed through Traefik using a DNS name such as `https://photos.home.ar`.

## Skills Demonstrated

This homelab documents practice with:

- Proxmox VE host installation and configuration
- Virtual machine templates and cloning workflows
- Debian 12 server administration basics
- ZFS-backed VM storage concepts
- Docker and Docker Compose service hosting
- Reverse proxy design with Traefik
- DNS and HTTPS-based service access patterns
- SSH hardening and Fail2Ban basics
- QEMU Guest Agent setup and validation
- Serial console recovery planning
- Backup, restore, and retention workflow documentation
- Safe public documentation habits, including not committing secrets
- Honest troubleshooting and risk documentation

## Troubleshooting / Lessons Learned

Documented lessons from the HaaS-platformV2 source material include:

- A degraded ZFS pool or disk-health concern should be documented clearly instead of hidden.
- A lab can be useful for research while still being unsuitable for production until storage health is fixed.
- VM templates should be validated before cloning workload systems.
- SSH, Fail2Ban, QEMU Guest Agent, and serial console access improve manageability and recovery options.
- Docker services are easier to operate when stack files and persistent data are separated into `/srv/stacks` and `/srv/data`.
- Reverse proxy and DNS standards make services easier to access and troubleshoot.
- Backups should be restore-tested after major changes, not just created.

## Screenshot Plan

Screenshots will be added later after review and redaction.

Planned screenshots:

- Proxmox host summary page
- VM100 Golden Template configuration
- VM200 Docker host configuration
- ZFS storage view
- Backup job or restore workflow example
- `/srv/stacks` and `/srv/data` layout example
- Traefik dashboard or routing status, with sensitive details removed
- Immich service access through DNS/HTTPS, with sensitive details removed

Screenshots must be reviewed before publishing so no secrets, tokens, private keys, personal data, or unnecessary system identifiers are exposed.

## Future Improvements

- Add redacted screenshots from the Proxmox homelab
- Add a simple architecture diagram
- Document final hardware specifications after storage remediation
- Document updated ZFS pool health after the disk issue is fixed
- Add a concise VM inventory table
- Add a short backup and restore validation summary
- Add links to selected HaaS-platformV2 runbooks instead of duplicating them
- Add a brief change log as the homelab evolves
