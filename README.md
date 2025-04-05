<h1 align="center" style="border-bottom: none">
  <img src="https://github.com/user-attachments/assets/bcd43211-d818-43a5-95fd-0b12b9c0123b"/><br>

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
- clean
- renew CMOS Battery (CR2032), requires unscrewing of the HDD bracket
- optionally update RAM (supports up to 32GB, currently using Kingston Fury Impact 2x 16GB [KF432S20IBK2/32](https://www.kingston.com/datasheets/KF432S20IBK2_32.pdf)
- put in a SATA drive 2.5"

### Shortcuts:
- F10 BIOS

### BIOS Update to rev 2.63
- [Download](https://ftp.hp.com/pub/softpaq/sp152001-152500/sp152286.exe) / from the product page, select OS Windows / Windows, extract driver to USB stick, follow instructions in the readme file.
- plug in USB stick
- start PC, spam F10
- Main -> Update System BIOS, follow instructions

## Proxmox
[Proxmox Virtual Environment](https://www.proxmox.com/en/products/proxmox-virtual-environment/overview), currently version 8.3. Provides a hypervisor to run VMs. 

### Installation
- download [ISO](https://www.proxmox.com/en/downloads) from Proxmox
- download [Balena Etcher](https://etcher.balena.io/) to copy the iso to a bootable usb stick
- plug it in and run it
- ⚠️ make sure you use your final IP Range when installing. Changing it, especially after clustering your proxmox hosts is a pain and usually requires reinstalling
- repeat for all machines

### Cluster configuration
- connect to one of your machines, if you named them in order (like pve01, pve02, etc) to the first one, through the web ui: https://your-ip:8006
- click on the top node in the treeview (Datacenter) then on Cluster in the main view
- create a cluster (give it an appropriate name, leave everything else as is) 
- once it is created, copy the Join Information
- connect to the next machine, repeat until you are in the cluster menu
- click "Join Cluster" and paste the copied join information
- ⚠️ don't do this last step to fast on multiple machines as it seems to mess up the joining and ends with machines not being able to join

The result is a cluster; you can now connect to any of the machines and administer them all from there, migrate vms and a lot more.

[Official Docs](https://pve.proxmox.com/wiki/Cluster_Manager)

### Extra Ressource links
- Proxmox Must Haves (configs) https://www.youtube.com/watch?v=VAJWUZ3sTSI
## K3s

## Longhorn

## Running Applications

### Gitea
### Harbor
### dotnet
### bitwarden

## Ansible
