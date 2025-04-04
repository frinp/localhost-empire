<h1 align="center" style="border-bottom: none">
  <img src="https://github.com/user-attachments/assets/95fc6a5c-3941-43b1-8e0e-5a7dede97407"/><br>

<p align="center">A <a href="https://github.com/frinp">frinp</a> home cluster project.</p>
</h1>
<h3></h3>

---

# Localhost Empire

The goal of this project is to have an entrypoint to all topics around setting up and runnning your own home cluster.

# Topics

## HP EliteDesk 800 35W G2 mini 
The baseline for running your own localhost empire. Well documented on the official manufacturer page, with drivers, manuals, etc.
- [Product Page](https://support.hp.com/us-en/product/details/hp-elitedesk-800-35w-g2-desktop-mini-pc/7633266)
- [Hardware reference guide](https://h10032.www1.hp.com/ctg/Manual/c04830607.pdf)
- Interesting overview with lots of picture: [ServeTheHome](https://www.servethehome.com/hp-elitedesk-800-g2-mini-project-tinyminimicro-ce-review/)

### Initial setup:
- Clean
- renew CMOS Battery (CR2032), requires unscrewing of the HDD bracket
- optionally update RAM (supports up to 32GB, currently using Kingston Fury Impact 2x 16GB [KF432S20IBK2/32](https://www.kingston.com/datasheets/KF432S20IBK2_32.pdf)
- put in a SATA drive 2.5"

### Shortcuts:
- F10 BIOS

### BIOS Update to rev 2.63
- [Download](https://ftp.hp.com/pub/softpaq/sp152001-152500/sp152286.exe) / from the product page, select OS Windows / Windows, extract driver to USB stick, follow instructions in the readme file.
- plug in USB stick
- Start PC, spam F10
- Main -> Update System BIOS, follow instructions

## Proxmox
[Proxmox Virtual Environment](https://www.proxmox.com/en/products/proxmox-virtual-environment/overview), currently version 8.3. Provides a hypervisor to run VMs. 

### Installation
- Download [ISO](https://www.proxmox.com/en/downloads) from Proxmox
- Download [Balena Etcher](https://etcher.balena.io/) to copy the iso to a bootable usb stick
- plug it in and run it
- ⚠️ make sure you use your final IP Range when installing. Changing it, especially after clustering your proxmox hosts is a pain and usually requires reinstalling

## K3s

## Longhorn

## Running Applications

### Gitea
### Harbor
### dotnet
### bitwarden

## Ansible
