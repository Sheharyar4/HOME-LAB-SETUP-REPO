# Cybersecurity Home Lab Setup — VMware Workstation

## Objective
Documentation of a self-built cybersecurity home lab used as the foundation for hands-on offensive and defensive practice. The lab was built in **VMware Workstation** with four virtual machines networked together: a Windows 10 victim/target, a Kali Linux attack machine, a Metasploitable2 intentionally-vulnerable target, and a Parrot Security OS machine. This lab is the environment behind the [Network Reconnaissance](../Network-Reconnaissance-Wireshark-Nmap) and other project work in this portfolio.

## Environment
- **Hypervisor:** VMware Workstation
- **Virtual Machines:**
  - Windows 10 x64 — target/victim machine
  - Kali Linux — penetration testing / attacker machine
  - Metasploitable2 — intentionally vulnerable Linux target
  - Parrot Security OS (Debian-based) — additional security-focused distribution

## Setup Summary

1. **Virtualization platform** — VMware Workstation configured with all four VMs visible and manageable from the Library panel.
2. **OS installation** — each machine installed and booted independently, confirming a working, isolated lab.
3. **Networking** — Metasploitable2 verified reachable at `192.168.120.129` on the lab's virtual network via `ifconfig`, and its vulnerable web services (TWiki, phpMyAdmin, Mutillidae, DVWA, WebDAV) confirmed accessible from another VM in the lab.

## Verified Boots

| Machine | Confirmed |
|---|---|
| Windows 10 x64 | Desktop reachable, with Notepad++, Process Hacker 2, and Procmon pre-installed |
| Kali Linux | GRUB boot menu → login screen → desktop, full chain confirmed |
| Metasploitable2 | Boot sequence with background services (atd, cron, Tomcat, Apache) reaching login prompt |
| Parrot Security OS | Live desktop environment with application menu and terminal accessible |

## Network Configuration
Metasploitable2's network interface was verified with `ifconfig`, confirming the machine sits at `192.168.120.129` on the lab's virtual network and that its vulnerable services are reachable from other VMs — the same target machine used for reconnaissance and vulnerability practice elsewhere in this portfolio.

## Screenshots

| # | Description |
|---|---|
| [`01-vmware-library-windows10.png`](./screenshots/01-vmware-library-windows10.png) | VMware Workstation Library panel showing all VMs, with Windows 10 running |
| [`02-kali-grub-boot.png`](./screenshots/02-kali-grub-boot.png) | Kali Linux GRUB boot menu |
| [`03-kali-login-screen.png`](./screenshots/03-kali-login-screen.png) | Kali Linux login screen |
| [`04-kali-desktop.png`](./screenshots/04-kali-desktop.png) | Kali Linux desktop after successful login |
| [`05-metasploitable2-boot.png`](./screenshots/05-metasploitable2-boot.png) | Metasploitable2 boot sequence and login prompt |
| [`06-parrot-security-desktop.png`](./screenshots/06-parrot-security-desktop.png) | Parrot Security OS desktop |
| [`07-parrot-security-terminal.png`](./screenshots/07-parrot-security-terminal.png) | Parrot Security OS application menu and terminal |
| [`08-metasploitable2-network-config.png`](./screenshots/08-metasploitable2-network-config.png) | Metasploitable2 network interface configuration and lab reachability check |

## Key Takeaway
A properly networked, multi-OS lab — attacker, defender, and intentionally vulnerable targets on the same virtual network — is the prerequisite for any realistic offensive/defensive practice. This environment is what made the Network Reconnaissance and Vulnerability Assessment projects in this portfolio possible.

## Repository Structure
```
├── README.md
└── screenshots/
    ├── 01-vmware-library-windows10.png
    ├── 02-kali-grub-boot.png
    ├── 03-kali-login-screen.png
    ├── 04-kali-desktop.png
    ├── 05-metasploitable2-boot.png
    ├── 06-parrot-security-desktop.png
    ├── 07-parrot-security-terminal.png
    └── 08-metasploitable2-network-config.png
```

---
**Tools:** VMware Workstation, Windows 10, Kali Linux, Metasploitable2, Parrot Security OS
**Skills demonstrated:** Virtualization, multi-VM networking, lab environment design, OS administration across Windows/Linux
